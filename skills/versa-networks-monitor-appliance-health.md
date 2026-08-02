---
name: Monitor Versa appliance health
description: Check live status, config-sync state and network health (IKE/interface/path) for a Versa-managed appliance via the Versa API MCP server.
api: mcp/versa-networks-mcp.yml
operations: [get_appliance_live_status, get_appliance_sync_status, get_health_ike, get_health_interface, get_health_path, get_appliance_services, get_appliance_violations]
---

# Monitor Versa appliance health

Assess the operational health of a single Versa VOS appliance.

## Prerequisites
- Versa API MCP server running and authenticated (OAuth2 password grant to `/auth/token`; bearer token used on every call).
- You know the appliance name (from the inventory skill) and/or its UUID.

## Steps
1. `get_appliance_live_status` — pull live status for the appliance (supports `command`, `filters`, `decode`, `fetch`, `uuid`).
2. `get_appliance_sync_status` — confirm the appliance configuration is in sync with the Director (pass `applianceUUID`).
3. Network health, one call each: `get_health_ike` (tunnels), `get_health_interface` (interfaces), `get_health_path` (SD-WAN paths) — each takes `deviceName`.
4. `get_appliance_services` — verify the expected services are running.
5. `get_appliance_violations` — surface any policy/compliance violations.

## Conventions & error handling
- Read-only; safe to poll.
- Error envelope `{error, code, message, more_info}`; treat `401` as an expired token (server re-auths), `404` as an unknown device.
- Prefer name-or-UUID consistently across calls to avoid `404`s.
