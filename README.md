# Versa Networks

Versa Networks is a SASE / SD-WAN / SSE vendor. Its VersaONE platform unifies networking and security (Secure SD-WAN, ZTNA, CASB, SWG, DLP, NGFW, ATP) on-prem, as private/sovereign SASE, or cloud-managed via Versa Concerto.

## API surface

- **Versa Director REST API** — appliance-hosted management/orchestration API (OAuth2 password-grant or HTTP Basic, offset/limit pagination, Swagger-documented per release on port 9182/9183). [Docs](https://docs.versa-networks.com/Management_and_Orchestration/Versa_Director/Director_REST_APIs/Versa_Director_REST_API_Overview)
- **Versa Analytics REST API** — analytics/reporting/alarm queries. [Docs](https://docs.versa-networks.com/Management_and_Orchestration/Versa_Analytics/Analytics_REST_APIs/Versa_Analytics_REST_API_Overview)
- **Versa API MCP Server** (`vnmcpserver`) — first-party Model Context Protocol server ("Zero Trust MCP Server") exposing 67 read-only Director/Concerto query tools. [Repo](https://github.com/versa-networks/vnmcpserver)
- **Terraform provider** (`versa-networks/versadirector`) — partner-tier IaC provider on the Terraform Registry.

Enriched by the API Evangelist enrichment pipeline (local-v1, 2026-07-21). The OpenAPI/Swagger spec is exported from a running Director and is not published for public download.

Backed by: mayfield — https://versa-networks.com
