---
name: Inventory Versa appliances
description: Enumerate and detail the SD-WAN/SASE appliances (VOS devices) managed by a Versa Director using the Versa API MCP server.
api: mcp/versa-networks-mcp.yml
operations: [get_all_appliance_names, get_all_appliances_lite, search_appliance_by_name, get_appliance_details_by_uuid, get_appliance_hardware, get_appliances_summary]
---

# Inventory Versa appliances

Use the first-party Versa API MCP server (`vnmcpserver`) to build an inventory of the
appliances a Versa Director manages.

## Prerequisites
- The MCP server is running (STDIO via `uv run mcp install main.py`, or SSE via `main_sse.py` / `main_concerto_sse.py`).
- Auth is configured: `VN_CLIENT_ID` / `VN_CLIENT_SECRET` plus Director URL + username/password. The server exchanges these for a bearer token at `/auth/token` (OAuth2 password grant).

## Steps
1. Call `get_all_appliance_names` to list every appliance name, or `get_appliances_summary` for a rollup.
2. For a broad list with metadata, call `get_all_appliances_lite` with `limit` and `offset` (pagination is offset/limit; start `offset=0&limit=25`). Page by advancing `offset`.
3. To locate a specific device, call `search_appliance_by_name` with `name`.
4. For deep detail, resolve the appliance UUID then call `get_appliance_details_by_uuid` and `get_appliance_hardware`.

## Conventions & error handling
- Pagination: `offset` + `limit`; keep paging until fewer than `limit` rows return.
- Errors: JSON envelope `{error, code, message, more_info}`; a `401` means the bearer token expired — the server re-authenticates against `/auth/token`. `404` means the appliance/name does not exist.
- All tools are read-only.
