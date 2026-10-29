# Coasty

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

Coasty is a computer-use AI agent platform (Y Combinator S26) that operates a full desktop, browser, and terminal like a human — reading the screen with vision, clicking, typing, filling forms, running commands, and verifying its own work across sandboxed virtual machines. It exposes a public REST API at coasty.ai/v1 with a published OpenAPI 3.1 spec (72 operations), a first-party MCP server (npx @coasty/mcp, 26 tools), free sandbox keys, HMAC-SHA256 webhook triggers, an Idempotency-Key contract, per-credit metered billing, and 1,000+ OAuth app integrations via Composio. Core API surfaces are Predict, Sessions, Ground, Parse, Machines, Schedules, Runs, and Workflows. Founded 2025-2026 by Prateek Jannu and Nitish Kovuru; #1 on the OSWorld benchmark among production computer-use agents.

**Areas:** Company · Computer Use · AI Agents · Automation · RPA · Desktop Automation · Browser Automation · MCP · Virtual Machines · Developer Tools

## Coasty on APIs.io

Everything profiled for Coasty is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/coasty/](https://apis.io/providers/coasty/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Coasty Keys API](https://apis.io/apis/coasty/coasty-keys-api/) — API key management and usage reporting.
- [Coasty Machines API](https://apis.io/apis/coasty/coasty-machines-api/) — Provision and control managed VMs.
- [Coasty Predict API](https://apis.io/apis/coasty/coasty-predict-api/) — Stateless CUA action prediction and grounding.
- [Coasty Runs API](https://apis.io/apis/coasty/coasty-runs-api/) — Autonomous task runs — the agent drives a task to completion on a machine.
- [Coasty Schedules API](https://apis.io/apis/coasty/coasty-schedules-api/) — Cron and one-shot scheduled CUA jobs.
- [Coasty Sessions API](https://apis.io/apis/coasty/coasty-sessions-api/) — Stateful CUA sessions with persistent trajectory.
- [Coasty Triggers API](https://apis.io/apis/coasty/coasty-triggers-api/) — Webhook and chain triggers for schedules.
- [Coasty Workflows API](https://apis.io/apis/coasty/coasty-workflows-api/) — Versioned, branching multi-step automations (DSL) and their runs.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Coasty Webhooks](https://apis.io/asyncapis/coasty/coasty-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Coasty Computer-Use](https://apis.io/servers/coasty/coasty-mcp/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Coasty Agentic Access](https://apis.io/agentic-access/coasty/coasty-agentic-access/)

#### Collections (16)

Postman and Open Collection request collections.

- [Coasty Public keys API](https://apis.io/collections/coasty/open-coasty-keys-api/)
- [Coasty Public keys machines API](https://apis.io/collections/coasty/open-coasty-machines-api/)
- [Coasty Public keys predict API](https://apis.io/collections/coasty/open-coasty-predict-api/)
- [Coasty Public keys runs API](https://apis.io/collections/coasty/open-coasty-runs-api/)
- [Coasty Public keys schedules API](https://apis.io/collections/coasty/open-coasty-schedules-api/)
- [Coasty Public keys sessions API](https://apis.io/collections/coasty/open-coasty-sessions-api/)
- [Coasty Public keys triggers API](https://apis.io/collections/coasty/open-coasty-triggers-api/)
- [Coasty Public keys workflows API](https://apis.io/collections/coasty/open-coasty-workflows-api/)
- [Coasty Public keys API](https://apis.io/collections/coasty/postman-coasty-keys-api/)
- [Coasty Public keys machines API](https://apis.io/collections/coasty/postman-coasty-machines-api/)
- [Coasty Public keys predict API](https://apis.io/collections/coasty/postman-coasty-predict-api/)
- [Coasty Public keys runs API](https://apis.io/collections/coasty/postman-coasty-runs-api/)
- [Coasty Public keys schedules API](https://apis.io/collections/coasty/postman-coasty-schedules-api/)
- [Coasty Public keys sessions API](https://apis.io/collections/coasty/postman-coasty-sessions-api/)
- [Coasty Public keys triggers API](https://apis.io/collections/coasty/postman-coasty-triggers-api/)
- [Coasty Public keys workflows API](https://apis.io/collections/coasty/postman-coasty-workflows-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Coasty Openapi Overlay](https://apis.io/overlays/coasty/coasty-openapi-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Coasty Authentication](https://apis.io/security/coasty/coasty-authentication/)
- [Coasty Domain Security](https://apis.io/security/coasty/coasty-domain-security/)
- [Coasty Vulnerability Disclosure](https://apis.io/security/coasty/coasty-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Coasty Plans](https://apis.io/plans/coasty/coasty-plans/)

#### Rate limits (1)

Published request limits.

- [Coasty Rate Limits](https://apis.io/rate-limits/coasty/coasty-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://coasty.ai)
- [Documentation](https://coasty.ai/docs)
- [Getting started](https://coasty.ai/guide?tab=api)
- [API reference](https://coasty.ai/api-docs)
- [Pricing](https://coasty.ai/pricing)
- [Sign up](https://coasty.ai/auth)
- [Blog](https://coasty.ai/blog)
- [Security](https://coasty.ai/.well-known/security.txt)
- [Terms of service](https://coasty.ai/terms)
- [Privacy policy](https://coasty.ai/privacy)
- [GitHub](https://github.com/coasty-ai)
- [Status](https://status.coasty.ai)

## API Evangelist rating

**Kin Score 59.6** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 62.5 |
| Contract governance | 4.5 |
| Operational transparency | 52.6 |
| Developer ergonomics | 55.4 |
| Access clarity | 76.3 |

**Agent readiness 47.0** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | verified |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 30.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/coasty/](https://apis.io/providers/coasty/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Coasty: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/coasty/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
