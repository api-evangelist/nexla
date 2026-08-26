---
name: nexla-monitor-and-triage-a-flow
description: >-
  Watch a running Nexla flow and work out what went wrong — read run metrics, pull flow logs for a run,
  read the audit log for who changed what, and check notifications for the alert that fired. Use when a
  pipeline stopped delivering, volume dropped, or a schema changed underneath a consumer.
api: Nexla REST API
base_url: https://dataops.nexla.io/nexla-api
operations:
  - get_flows
  - get_flow_by_id
  - get_resource_metrics_daily
  - get_resource_metrics_by_run
  - get_flow_metrics
  - get_flow_logs_for_run_id
  - user_24_hour_flow_stats
  - get_notifications
  - get_notification_count
  - get_notification_types
  - get_data_source_audit_log
  - get_nexset_audit_log
  - get_data_sink_audit_log
  - pause_source
generated: '2026-08-26'
method: generated
source: openapi/nexla-rest-api-openapi.yml
---

# Monitor and triage a Nexla flow

## Orient

- `get_flows` (`GET /flows`) lists flows you can see; `get_flow_by_id` (`GET /flows/{flow_id}`) returns
  the node graph (`FlowOriginNode` / `FlowChildNode`, linked by `origin_node_id` and `parent_node_id`).
- `user_24_hour_flow_stats` (`GET /users/{user_id}/flows/dashboard`) is the fastest one-call answer to
  "is anything broken right now".

## Measure

- `get_resource_metrics_daily` (`GET /{resource_type}/{resource_id}/metrics`) — daily volume for a
  source, Nexset or sink. A volume cliff here is usually the real symptom.
- `get_resource_metrics_by_run` (`GET /{resource_type}/{resource_id}/metrics/run_summary`) — per-run
  breakdown. Use it to find WHICH run went wrong.
- `get_flow_metrics` (`GET /data_flows/{resource_type}/{resource_id}/metrics`) — flow-level rollup.

## Read the logs

`get_flow_logs_for_run_id` (`GET /data_flows/{resource_type}/{resource_id}/logs`) returns the logs for a
run id you got from the run summary. Go metrics → run summary → logs, in that order; jumping straight to
logs without a run id gives you noise.

## Check what alerted

`get_notification_count` (`GET /notifications/count`) then `get_notifications` (`GET /notifications`),
filtered by `resource_type`, `resource_id` and `level`. `get_notification_types`
(`GET /notification_types`) enumerates the catalog. The types that matter in triage are
**Source Data Read Error**, **Destination Data Write Error**, **Dataset Transform Error**,
**Destination Transform Error**, **Source Data Delayed**, **Source Data Volume Change**,
**Source Empty File** and **Schema Change** — Schema Change is the one that silently breaks downstream
consumers without erroring.

## Check what changed

Every major resource keeps an audit log: `get_data_source_audit_log`, `get_nexset_audit_log`,
`get_data_sink_audit_log` (`GET /{resource}/{id}/audit_log`). When metrics fell off a cliff at a
timestamp, look here for a configuration change at the same timestamp before blaming the upstream system.

## Stop the bleeding

If a flow is writing bad data, `pause_source` (`PUT /data_sources/{source_id}/pause`) — reversible with
`activate_source`. **Do not delete anything.** Deletion is terminal in this API and there is no restore.
