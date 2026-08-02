---
name: Triage Versa alarms
description: Summarize and drill into fault alarms across the Versa estate (appliance, Director, Analytics) via the Versa API MCP server.
api: mcp/versa-networks-mcp.yml
operations: [get_alarm_summary, get_alarm_summary_per_org, get_all_filtered_alarms, filter_paginate_alarm, get_alarm_types, get_director_alarms, get_analytics_alarms, get_status_change]
---

# Triage Versa alarms

Move from an estate-wide alarm summary to the specific faults that need attention.

## Prerequisites
- Versa API MCP server running and authenticated (bearer token from `/auth/token`).

## Steps
1. Start broad: `get_alarm_summary` (overall) or `get_alarm_summary_per_org` (per organization) for counts by severity.
2. Enumerate the fault taxonomy with `get_alarm_types` so you can filter meaningfully.
3. Pull the matching alarms with `get_all_filtered_alarms` or `filter_paginate_alarm` (offset/limit pagination + filter string).
4. Narrow by source when needed: `get_director_alarms` / `get_director_ha_alarms` / `get_director_fail_over_alarms` (control plane), `get_analytics_alarms` (analytics), `get_imp_alarms` (important-only).
5. Correlate with `get_status_change` to see what recently transitioned state.

## Conventions & error handling
- Pagination: `offset` + `limit`; page until the result set is exhausted.
- Error envelope `{error, code, message, more_info}`; `401` = expired token (auto re-auth), `4xx` app codes in the `4001-5000` range carry the specific fault reason.
- Read-only triage; remediation is performed through the Director UI/config APIs, not these query tools.
