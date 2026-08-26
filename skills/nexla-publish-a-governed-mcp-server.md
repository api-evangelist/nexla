---
name: nexla-publish-a-governed-mcp-server
description: >-
  Turn a governed Nexla Nexset into an MCP server other agents can call — mint tools from Nexsets, group
  them into a toolset, map credentials, activate an export, read back the MCP client config, and audit
  every call through receipts. Use when the job is to give an agent scoped, governed access to enterprise
  data rather than to move the data.
api: Nexla GenAI API (RAG + MCPaaS)
base_url: https://api-genai.nexla.io
operations:
  - create_tool_from_nexset_v1_tools_from_nexset_post
  - list_tools_v1_tools_get
  - get_tool_definition_v1_tools__tool_id__definition_get
  - activate_tool_v1_tools__tool_id__activate_post
  - create_toolset_v1_toolsets_post
  - add_tools_to_toolset_v1_toolsets__tool_set_id__tools_post
  - put_credential_mapping_v1_toolsets__tool_set_id__tools__tool_id__credential_mapping_put
  - create_export_v1_toolsets__tool_set_id__exports_post
  - activate_export_v1_toolsets__tool_set_id__exports__export_id__activate_post
  - get_mcp_config_by_export_id_v1_toolsets__tool_set_id__exports__export_id__mcp_config_get
  - get_mcp_config_by_server_key_v1_mcp__server_key__config_get
  - query_receipts_v1_receipts_get
  - get_receipt_v1_receipts__receipt_id__get
  - pause_export_v1_toolsets__tool_set_id__exports__export_id__pause_post
generated: '2026-08-26'
method: generated
source: openapi/nexla-genai-mcpaas-openapi.json
---

# Publish a governed MCP server from Nexla

Nexla's MCP surface is minted, not fixed. The chain is:
**Nexset → Tool → Toolset → Export → MCP server URL.**

## Before you start

- Base URL: `https://api-genai.nexla.io`. The published spec declares no `servers[]` and no
  `securitySchemes` — see `overlays/nexla-genai-mcpaas-overlay.yaml`, which supplies both.
- Auth: `Authorization: Bearer <NEXLA_SERVICE_KEY>`.
- This is the **administrative control plane**. It is deliberately not exposed as MCP tools — an operator
  authorises these actions, an agent does not call them on its own behalf. Respect that boundary.

## Steps

1. **Mint a tool from a Nexset** — `create_tool_from_nexset_v1_tools_from_nexset_post`
   (`POST /v1/tools:from_nexset`). The tool's name and input schema are generated from the Nexset, which
   is why there is no static Nexla tool catalog to read.

2. **Read back what you actually made** — `get_tool_definition_v1_tools__tool_id__definition_get`
   (`GET /v1/tools/{tool_id}/definition`). Confirm the generated input schema before anyone can call it.
   `list_tools_v1_tools_get` (`GET /v1/tools`) lists the rest.

3. **Activate the tool** — `activate_tool_v1_tools__tool_id__activate_post`
   (`POST /v1/tools/{tool_id}:activate`). Reversible with `:pause`.

4. **Group into a toolset** — `create_toolset_v1_toolsets_post` (`POST /v1/toolsets`), then
   `add_tools_to_toolset_v1_toolsets__tool_set_id__tools_post`
   (`POST /v1/toolsets/{tool_set_id}/tools`). The toolset is the governance unit: it decides which tools
   travel together to one agent.

5. **Map credentials** — `put_credential_mapping_v1_toolsets__tool_set_id__tools__tool_id__credential_mapping_put`
   (`PUT /v1/toolsets/{tool_set_id}/tools/{tool_id}/credential-mapping`). This binds which stored
   credential a tool executes under. Get this wrong and an agent runs with the wrong identity — check it
   twice.

6. **Export it** — `create_export_v1_toolsets__tool_set_id__exports_post`
   (`POST /v1/toolsets/{tool_set_id}/exports`) then
   `activate_export_v1_toolsets__tool_set_id__exports__export_id__activate_post`. Activating the export
   is what materialises a reachable MCP server.

7. **Get the client config** — `get_mcp_config_by_export_id_...` or
   `get_mcp_config_by_server_key_v1_mcp__server_key__config_get` (`GET /v1/mcp/{server_key}/config`).
   The resulting endpoint is:

   ```json
   {
     "url": "https://api-genai.nexla.io/mcp/service_key/{server_key}",
     "transport": "streamable-http",
     "headers": { "Authorization": "Bearer YOUR_NEXLA_SERVICE_KEY" }
   }
   ```

   Clients that cannot set a custom header (ChatGPT) use OAuth instead; the metadata is served at
   `https://api-genai.nexla.io/.well-known/oauth-protected-resource`.

## What the agent sees on the other end

Five stable gateway meta-tools — `search_tools`, `describe_tool`, `call_tool`,
`list_nexla_vendors_with_available_credentials`, `create_nexla_credential` — plus the tools you minted.
The mapping from each meta-tool back to its REST operation is in `mcp/nexla-tool-crosswalk.yml`.

## Audit

Every MCP tool call writes a receipt. `query_receipts_v1_receipts_get` (`GET /v1/receipts`) and
`get_receipt_v1_receipts__receipt_id__get` (`GET /v1/receipts/{receipt_id}`) are the read side. Check
receipts before widening a toolset's scope, not after.

## Rolling back

`pause_export_...` (`POST /v1/toolsets/{tool_set_id}/exports/{export_id}:pause`) takes the server offline
reversibly. `:retire` is **terminal** — prefer pause unless you mean it.
