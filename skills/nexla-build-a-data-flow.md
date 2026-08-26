---
name: nexla-build-a-data-flow
description: >-
  Stand up a complete Nexla data flow over the REST API — create a credential, probe it to see what is
  really there, create a source, let Nexla detect the Nexset, attach a destination, then activate. Use
  when an agent must move data from a system into a warehouse, lake, vector DB or another API without
  touching the Nexla UI.
api: Nexla REST API
base_url: https://dataops.nexla.io/nexla-api
operations:
  - create_data_credential
  - preview_storage_structure
  - preview_connector_content
  - create_data_source
  - get_nexsets
  - get_nexset
  - get_nexset_samples
  - create_data_sink
  - activate_source
  - get_flow_by_resource_id
  - flow_activate_with_flow_id
generated: '2026-08-26'
method: generated
source: openapi/nexla-rest-api-openapi.yml
---

# Build a Nexla data flow

A Nexla flow is a graph: **credential → source → Nexset(s) → sink(s)**. Build it in that order. Every
operationId below is verified present in `openapi/nexla-rest-api-openapi.yml`.

## Before you start

- Base URL: `https://dataops.nexla.io/nexla-api`. Self-hosted and private-VPC customers run their own
  host; the spec's `servers[]` is templated on `{nexla-api-host}` for exactly that reason.
- Auth: `Authorization: Bearer <session-token>` plus `Accept: application/vnd.nexla.api.v1+json`.
  Session tokens last about an hour. If you hold a permanent service key, exchange it for a session
  token rather than sending it on every call.
- **There is no idempotency key.** A retried POST creates a second resource. Before every create, list
  first and match on name. See `conventions/nexla-conventions.yml`.

## Steps

1. **Create the credential** — `create_data_credential` (`POST /data_credentials`). The body shape is
   polymorphic: pick the concrete credential schema for the connector family you are connecting
   (`postgres_data_credential`, `s3_data_credential`, `snowflake_data_credential`,
   `kafka_data_credential`, `pinecone_data_credential`, `rest_data_credential`, and 50 more in
   `components.schemas`). Do not send a generic body — the discriminator is the connector type.

2. **Probe before you trust it** — `preview_storage_structure`
   (`POST /data_credentials/{credential_id}/probe/tree`) returns the browsable tree for a file, database
   or NoSQL connector; `preview_connector_content`
   (`POST /data_credentials/{credential_id}/probe/sample`) returns sample records. Both can return an
   async handle (`*_with_async` response variants) — if you get one, poll rather than assuming a result.
   This step is what stops you building a flow against a path that does not exist.

3. **Create the source** — `create_data_source` (`POST /data_sources`), referencing the credential via
   `data_credentials_id` and the location you confirmed in step 2.

4. **Let Nexla detect the Nexset** — do NOT create one by hand for a detected source. List with
   `get_nexsets` (`GET /data_sets`) filtered to your `data_source_id`, then read one with `get_nexset`
   and inspect real records with `get_nexset_samples` (`GET /data_sets/{set_id}/samples`). Confirm the
   detected schema matches what you expect before wiring a destination.

5. **Create the destination** — `create_data_sink` (`POST /data_sinks`) with the `data_set_id` from step
   4 and a `data_credentials_id` for the target system.

6. **Activate** — `activate_source` (`PUT /data_sources/{source_id}/activate`) starts ingestion. To act
   on the whole graph instead, resolve it with `get_flow_by_resource_id`
   (`GET /{resource_type}/{resource_id}/flow`) and then `flow_activate_with_flow_id`
   (`PUT /flows/{flow_id}/activate`).

## Pagination

Every listing endpoint takes `page` and `per_page`, and returns `Link` (`rel="Previous"` / `rel="Next"`),
`X-Total-Count`, `X-Current-Page` and `X-Page-Count`. Page until `Next` is absent. The response headers
are NOT declared in the OpenAPI — read them anyway.

## Errors

Nexla returns a custom JSON envelope, not RFC 9457:
`{ error, error_description, error_code, timestamp, request_id, details }`.
`AUTH_003` means the session token expired — refresh and retry. `VAL_001` carries the offending fields in
`details`. A duplicate create surfaces as `409 Conflict`. Retry `429/502/503/504` with exponential
backoff; do not retry `400` or `403`. Full catalog: `errors/nexla-problem-types.yml`.

## Safety

`activate_source` and `pause_source` are a reversible pair — either direction is safe. **`delete_*` is
not.** There are 44 DELETE operations in this contract and no restore, undelete or trash endpoint
anywhere. Never delete to "clean up" a failed build; pause instead, and leave the resource for a human.
