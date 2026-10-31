# CMS Open Payments

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

CMS Open Payments is the U.S. federal transparency program (run by the Centers for Medicare and Medicaid Services) that publishes payments and transfers of value made by drug and medical device manufacturers and group purchasing organizations to physicians, non-physician practitioners, and teaching hospitals. The public data site at openpaymentsdata.cms.gov exposes a free, open, no-authentication REST API (a DKAN-style data catalog under /api/1) that lets developers query general payments, research payments, and ownership and investment records by program year. The API offers a structured datastore query interface (filter, select, sort, paginate), a SQL query endpoint, CSV and JSON downloads, and a metastore catalog for dataset discovery and metadata. Reads are completely free and require no API key. Program Year 2025 alone contains roughly 17 million published records totaling about 14.67 billion dollars in payments.

**Areas:** Government Data · Healthcare · Open Data · Transparency · Payments · Clinical Data · Physicians · Open Government · Public Sector

## CMS Open Payments on APIs.io

Everything profiled for CMS Open Payments is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/open-payments/](https://apis.io/providers/open-payments/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [CMS Open Payments Datastore Query API](https://apis.io/apis/open-payments/open-payments-datastore-query-api/) — Structured query over a dataset distribution.
- [CMS Open Payments Datastore SQL API](https://apis.io/apis/open-payments/open-payments-datastore-sql-api/) — SQL query over a datastore resource.
- [CMS Open Payments Download API](https://apis.io/apis/open-payments/open-payments-download-api/) — Bulk CSV or JSON download of query results.
- [CMS Open Payments Metastore API](https://apis.io/apis/open-payments/open-payments-metastore-api/) — DCAT-US dataset catalog and metadata.
- [CMS Open Payments Search API](https://apis.io/apis/open-payments/open-payments-search-api/) — Full-text and faceted dataset discovery.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Open Payments Agentic Access](https://apis.io/agentic-access/open-payments/open-payments-agentic-access/)

#### Collections (6)

Postman and Open Collection request collections.

- [CMS Open Payments API](https://apis.io/collections/open-payments/open-open-payments/)
- [CMS Open Payments Datastore Query API](https://apis.io/collections/open-payments/open-open-payments-datastore-query-api/)
- [CMS Open Payments Datastore Query Datastore SQL API](https://apis.io/collections/open-payments/open-open-payments-datastore-sql-api/)
- [CMS Open Payments Datastore Query Download API](https://apis.io/collections/open-payments/open-open-payments-download-api/)
- [CMS Open Payments Datastore Query Metastore API](https://apis.io/collections/open-payments/open-open-payments-metastore-api/)
- [CMS Open Payments Datastore Query Search API](https://apis.io/collections/open-payments/open-open-payments-search-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Open Payments Authentication](https://apis.io/security/open-payments/open-payments-authentication/)
- [Open Payments Domain Security](https://apis.io/security/open-payments/open-payments-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Open Payments Plans Pricing](https://apis.io/plans/open-payments/open-payments-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Open Payments Rate Limits](https://apis.io/rate-limits/open-payments/open-payments-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Open Payments Finops](https://apis.io/finops/open-payments/open-payments-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://openpaymentsdata.cms.gov)
- [Documentation](https://openpaymentsdata.cms.gov/about/api)
- [Sign up](https://www.cms.gov/priorities/key-initiatives/open-payments)

## API Evangelist rating

**Kin Score 28.1** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 44.4 |
| Contract governance | 0.0 |
| Operational transparency | 7.9 |
| Developer ergonomics | 32.9 |
| Access clarity | 18.4 |

**Agent readiness 17.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 11.8** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/open-payments/](https://apis.io/providers/open-payments/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for CMS Open Payments: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/open-payments/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
