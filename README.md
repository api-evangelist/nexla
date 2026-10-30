# Nexla

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Nexla is an enterprise data integration and AI-data platform, founded in 2016 and headquartered in San Mateo, California. Its core abstraction is the Nexset — a logical, schema-aware, bi-directionally usable data product that Nexla generates automatically from any connected system. The platform spans ETL/ELT, streaming and CDC, API ingestion and delivery, RAG pipelines and, since 2026, an MCP Tools layer (MCP Studio, MCP Gateway, Agentic Probe) that turns governed Nexsets into task-scoped MCP servers for AI agents. Nexla exposes two public machine-readable contracts: a 274-operation OpenAPI 3.1 REST API covering flows, sources, Nexsets, sinks, credentials, transforms, projects, teams, organizations, access control, notifications, audit logs and metrics; and a 131-operation OpenAPI 3.1 GenAI (RAG + MCPaaS) API covering agentic RAG, nexset filters, skills, tools, toolsets, MCP gateway and audit receipts. First-party clients ship as a Python SDK, a TypeScript/JS SDK, a React embedding SDK and a Python CLI. Nexla is SOC 2 Type II, HIPAA, GDPR and CCPA compliant.

**Areas:** Company · Data Integration · Data Engineering · ETL · ELT · Data Products · Streaming · Change Data Capture · Data Governance · Artificial Intelligence · RAG · MCP

## Nexla on APIs.io

Everything profiled for Nexla is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/nexla/](https://apis.io/providers/nexla/)** — or go straight to one of the APIs or properties below.

### APIs (72)

- [Nexla Access Control API](https://apis.io/apis/nexla/nexla-access-control-api/) — Operations for managing access control to resources
- [Nexla Approval Requests API](https://apis.io/apis/nexla/nexla-approval-requests-api/) — Operations for managing all requests made by users without permissions.
- [Nexla Async Tasks API](https://apis.io/apis/nexla/nexla-async-tasks-api/) — Operations for managing asynchronous tasks.
- [Nexla Audit Logs API](https://apis.io/apis/nexla/nexla-audit-logs-api/) — Operations for reviewing the change history of resources.
- [Nexla Bulk Evaluation API](https://apis.io/apis/nexla/nexla-bulk-evaluation-api/) — The Bulk Evaluation API from Nexla — 1 operation(s) for bulk evaluation.
- [Nexla Bulk Query API](https://apis.io/apis/nexla/nexla-bulk-query-api/) — The Bulk Query API from Nexla — 1 operation(s) for bulk query.
- [Nexla Clear Dataset Cache API](https://apis.io/apis/nexla/nexla-clear-dataset-cache-api/) — The Clear Dataset Cache API from Nexla — 1 operation(s) for clear dataset cache.
- [Nexla Clear Token Cache API](https://apis.io/apis/nexla/nexla-clear-token-cache-api/) — The Clear Token Cache API from Nexla — 1 operation(s) for clear token cache.
- [Nexla Code API](https://apis.io/apis/nexla/nexla-code-api/) — The Code API from Nexla — 2 operation(s) for code.
- [Nexla Code Containers API](https://apis.io/apis/nexla/nexla-code-containers-api/) — Code containers are a general-purpose resource in the platform for storing user-defined functions that can be referenced by different modules for different…
- [Nexla Credential Mappings API](https://apis.io/apis/nexla/nexla-credential-mappings-api/) — The credential-mappings API from Nexla — 2 operation(s) for credential-mappings.
- [Nexla Credentials API](https://apis.io/apis/nexla/nexla-credentials-api/) — Operations for managing data credentials.
- [Nexla Custom Runtimes API](https://apis.io/apis/nexla/nexla-custom-runtimes-api/) — Operations for managing custom runtimes.
- [Nexla Data Maps API](https://apis.io/apis/nexla/nexla-data-maps-api/) — The Data Maps API from Nexla — 4 operation(s) for data maps.
- [Nexla Destinations (Data Sinks) API](https://apis.io/apis/nexla/nexla-destinations-data-sinks-api/) — Operations for managing data sinks. Note that Destinations on the Nexla UI are aliased as `data_sinks` in the Nexla API reference model, so all endpoints…
- [Nexla Docs API](https://apis.io/apis/nexla/nexla-docs-api/) — The Docs API from Nexla — 1 operation(s) for docs.
- [Nexla Flow API](https://apis.io/apis/nexla/nexla-flow-api/) — The Flow API from Nexla — 2 operation(s) for flow.
- [Nexla Flows API](https://apis.io/apis/nexla/nexla-flows-api/) — Operations for managing flows.
- [Nexla Gateway API](https://apis.io/apis/nexla/nexla-gateway-api/) — The gateway API from Nexla — 11 operation(s) for gateway.
- [Nexla Gen AI Recommendations API](https://apis.io/apis/nexla/nexla-gen-ai-recommendations-api/) — Operations for requesting AI recommendations for documentation.
- [Nexla Genai Codegen API](https://apis.io/apis/nexla/nexla-genai-codegen-api/) — The Genai Codegen API from Nexla — 1 operation(s) for genai codegen.
- [Nexla GenAI Configs API](https://apis.io/apis/nexla/nexla-genai-configs-api/) — The GenAI Configs API from Nexla — 1 operation(s) for genai configs.
- [Nexla GenAI Configuration API](https://apis.io/apis/nexla/nexla-genai-configuration-api/) — The GenAI Configuration API from Nexla — 1 operation(s) for genai configuration.
- [Nexla GenAI Configurations API](https://apis.io/apis/nexla/nexla-genai-configurations-api/) — Operations for managing GenAI configurations.
- [Nexla Genai Dsl Transform API](https://apis.io/apis/nexla/nexla-genai-dsl-transform-api/) — The Genai Dsl Transform API from Nexla — 1 operation(s) for genai dsl transform.
- [Nexla Genai Transform API](https://apis.io/apis/nexla/nexla-genai-transform-api/) — The Genai Transform API from Nexla — 1 operation(s) for genai transform.
- [Nexla Generate Document API](https://apis.io/apis/nexla/nexla-generate-document-api/) — The Generate Document API from Nexla — 2 operation(s) for generate document.
- [Nexla Health API](https://apis.io/apis/nexla/nexla-health-api/) — The health API from Nexla — 5 operation(s) for health.
- [Nexla Health Check API](https://apis.io/apis/nexla/nexla-health-check-api/) — The Health Check API from Nexla — 2 operation(s) for health check.
- [Nexla Initialize API](https://apis.io/apis/nexla/nexla-initialize-api/) — The Initialize API from Nexla — 1 operation(s) for initialize.
- [Nexla Limits API](https://apis.io/apis/nexla/nexla-limits-api/) — Rate limit endpoints
- [Nexla List Dataset Cache API](https://apis.io/apis/nexla/nexla-list-dataset-cache-api/) — The List Dataset Cache API from Nexla — 1 operation(s) for list dataset cache.
- [Nexla List Models API](https://apis.io/apis/nexla/nexla-list-models-api/) — The List Models API from Nexla — 1 operation(s) for list models.
- [Nexla Lookup Enrich API](https://apis.io/apis/nexla/nexla-lookup-enrich-api/) — The Lookup Enrich API from Nexla — 1 operation(s) for lookup enrich.
- [Nexla Marketing Chat API](https://apis.io/apis/nexla/nexla-marketing-chat-api/) — The Marketing Chat API from Nexla — 1 operation(s) for marketing chat.
- [Nexla Marketplace API](https://apis.io/apis/nexla/nexla-marketplace-api/) — Operations for managing the marketplace domains and items.
- [Nexla MCP API](https://apis.io/apis/nexla/nexla-mcp-api/) — The Mcp API from Nexla — 2 operation(s) for mcp.
- [Nexla MCP Config API](https://apis.io/apis/nexla/nexla-mcp-config-api/) — The mcp-config API from Nexla — 3 operation(s) for mcp-config.
- [Nexla Mcp Query API](https://apis.io/apis/nexla/nexla-mcp-query-api/) — The Mcp Query API from Nexla — 1 operation(s) for mcp query.
- [Nexla MCP Tools API](https://apis.io/apis/nexla/nexla-mcp-tools-api/) — The MCP Tools API from Nexla — 6 operation(s) for mcp tools.
- [Nexla Metrics API](https://apis.io/apis/nexla/nexla-metrics-api/) — Operations for retrieving metrics.
- [Nexla Admin API](https://apis.io/apis/nexla/nexla-nexla-admin-api-api/) — The Nexla Admin Api API from Nexla — 1 operation(s) for nexla admin api.
- [Nexla Nexsets (Data Sets) API](https://apis.io/apis/nexla/nexla-nexsets-data-sets-api/) — Operations for managing Nexsets. Note that Nexsets on the Nexla UI are aliased as `data_sets` in the Nexla API reference model, so all endpoints and…
- [Nexla Notifications API](https://apis.io/apis/nexla/nexla-notifications-api/) — Operations for managing notifications.
- [Nexla Org authentication configs API](https://apis.io/apis/nexla/nexla-org-authentication-configs-api/) — Operations for managing organization authentication configurations.
- [Nexla Organizations API](https://apis.io/apis/nexla/nexla-organizations-api/) — Operations for managing the user's organization.
- [Nexla Private Query API](https://apis.io/apis/nexla/nexla-private-query-api/) — The Private Query API from Nexla — 1 operation(s) for private query.
- [Nexla Projects API](https://apis.io/apis/nexla/nexla-projects-api/) — Operations for managing projects.
- [Nexla Quarantine Settings API](https://apis.io/apis/nexla/nexla-quarantine-settings-api/) — Operations for managing quarantine settings.
- [Nexla Query API](https://apis.io/apis/nexla/nexla-query-api/) — The Query API from Nexla — 1 operation(s) for query.
- [Nexla Receipts API](https://apis.io/apis/nexla/nexla-receipts-api/) — The receipts API from Nexla — 2 operation(s) for receipts.
- [Nexla Search Nexsets API](https://apis.io/apis/nexla/nexla-search-nexsets-api/) — The Search Nexsets API from Nexla — 1 operation(s) for search nexsets.
- [Nexla Self Sign-Up Admin API](https://apis.io/apis/nexla/nexla-self-sign-up-admin-api/) — Operations for approving self-signup requests.
- [Nexla Self Sign-Up API](https://apis.io/apis/nexla/nexla-self-sign-up-api/) — Operations for self-signup and verification.
- [Nexla Session Management API](https://apis.io/apis/nexla/nexla-session-management-api/) — Operations for managing your Nexla session programmatically. > Note: Unless unavoidable, we recommend starting your session from the Nexla UI and using the…
- [Nexla Sessions API](https://apis.io/apis/nexla/nexla-sessions-api/) — The sessions API from Nexla — 5 operation(s) for sessions.
- [Nexla Sources API](https://apis.io/apis/nexla/nexla-sources-api/) — Operations for managing data sources.
- [Nexla Struct Extraction API](https://apis.io/apis/nexla/nexla-struct-extraction-api/) — The Struct Extraction API from Nexla — 1 operation(s) for struct extraction.
- [Nexla Teams API](https://apis.io/apis/nexla/nexla-teams-api/) — Operations for managing teams.
- [Nexla Tools API](https://apis.io/apis/nexla/nexla-tools-api/) — The tools API from Nexla — 10 operation(s) for tools.
- [Nexla Transforms API](https://apis.io/apis/nexla/nexla-transforms-api/) — Operations for managing reusable attribute and record transforms.
- [Nexla Usage API](https://apis.io/apis/nexla/nexla-usage-api/) — The usage API from Nexla — 4 operation(s) for usage.
- [Nexla User Settings API](https://apis.io/apis/nexla/nexla-user-settings-api/) — The User Settings API from Nexla — 1 operation(s) for user settings.
- [Nexla Users API](https://apis.io/apis/nexla/nexla-users-api/) — Operations for managing user settings.
- [Nexla V2 Filters API](https://apis.io/apis/nexla/nexla-v2-filters-api/) — The v2-filters API from Nexla — 3 operation(s) for v2-filters.
- [Nexla V2 Nexset Info API](https://apis.io/apis/nexla/nexla-v2-nexset-info-api/) — The v2-nexset-info API from Nexla — 2 operation(s) for v2-nexset-info.
- [Nexla V2 Query API](https://apis.io/apis/nexla/nexla-v2-query-api/) — The v2-query API from Nexla — 3 operation(s) for v2-query.
- [Nexla V2 Skills API](https://apis.io/apis/nexla/nexla-v2-skills-api/) — The v2-skills API from Nexla — 3 operation(s) for v2-skills.
- [Nexla Webhooks API](https://apis.io/apis/nexla/nexla-webhooks-api/) — Operations for sending events to the Nexla `webhook` connector.
- [Nexla .well Known API](https://apis.io/apis/nexla/nexla-well-known-api/) — The .well Known API from Nexla — 2 operation(s) for .well known.
- [Nexla Datasets API](https://apis.io/apis/nexla/nexla-datasets-api/) — The Datasets API from Nexla — 1 operation(s) for datasets.
- [Nexla Tool Sets API](https://apis.io/apis/nexla/nexla-tool-sets-api/) — The Tool Sets API from Nexla — 19 operation(s) for tool sets.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Nexla Webhooks](https://apis.io/asyncapis/nexla/nexla-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Nexla MCP Server (MCP Tools / MCPaaS)](https://apis.io/servers/nexla/nexla-mcp-server-mcp-tools-mcpaas/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Nexla Genai Mcpaas Overlay](https://apis.io/overlays/nexla/nexla-genai-mcpaas-overlay/)
- [Nexla Rest Api Overlay](https://apis.io/overlays/nexla/nexla-rest-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Nexla Authentication](https://apis.io/security/nexla/nexla-authentication/)
- [Nexla Domain Security](https://apis.io/security/nexla/nexla-domain-security/)
- [Nexla Trust Center](https://apis.io/security/nexla/nexla-trust-center/)
- [Nexla Vulnerability Disclosure](https://apis.io/security/nexla/nexla-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Nexla Plans Pricing](https://apis.io/plans/nexla/nexla-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Nexla Rate Limits](https://apis.io/rate-limits/nexla/nexla-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://nexla.com/)
- [Documentation](https://docs.nexla.com/)
- [Getting started](https://docs.nexla.com/user-guides/get-started/quick-start-guide)
- [API reference](https://docs.nexla.com/reference/nexla-api)
- [Pricing](https://nexla.com/pricing/)
- [Sign up](https://dataops.nexla.io/signup)
- [Support](https://nexla.com/contact-us/)
- [Blog](https://nexla.com/blog/)
- [Compliance](https://nexla.com/data-security/)
- [Terms of service](https://nexla.com/terms-of-service/)
- [Privacy policy](https://nexla.com/privacy-policy/)
- [GitHub](https://github.com/nexla-opensource)

## API Evangelist rating

**Kin Score 64.3** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 54.5 |
| Contract governance | 18.2 |
| Operational transparency | 57.9 |
| Developer ergonomics | 73.2 |
| Access clarity | 71.1 |

**Agent readiness 41.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | templated |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 32.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/nexla/](https://apis.io/providers/nexla/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Nexla: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/nexla/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
