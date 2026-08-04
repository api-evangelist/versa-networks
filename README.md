# Versa Networks

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Versa Networks is a SASE / SD-WAN / SSE vendor. Its VersaONE platform unifies networking and security (Secure SD-WAN, ZTNA, CASB, SWG, DLP, NGFW, ATP) on-prem, as private/sovereign SASE, or cloud-managed via Versa Concerto.

## API surface

- **Versa Director REST API** — appliance-hosted management/orchestration API (OAuth2 password-grant or HTTP Basic, offset/limit pagination, Swagger-documented per release on port 9182/9183). [Docs](https://docs.versa-networks.com/Management_and_Orchestration/Versa_Director/Director_REST_APIs/Versa_Director_REST_API_Overview)
- **Versa Analytics REST API** — analytics/reporting/alarm queries. [Docs](https://docs.versa-networks.com/Management_and_Orchestration/Versa_Analytics/Analytics_REST_APIs/Versa_Analytics_REST_API_Overview)
- **Versa API MCP Server** (`vnmcpserver`) — first-party Model Context Protocol server ("Zero Trust MCP Server") exposing 67 read-only Director/Concerto query tools. [Repo](https://github.com/versa-networks/vnmcpserver)
- **Terraform provider** (`versa-networks/versadirector`) — partner-tier IaC provider on the Terraform Registry.

Enriched by the API Evangelist enrichment pipeline (local-v1, 2026-07-21). The OpenAPI/Swagger spec is exported from a running Director and is not published for public download.

Backed by: mayfield — https://versa-networks.com
