# CMS Open Payments (open-payments)

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

CMS Open Payments is the U.S. federal transparency program, run by the Centers for Medicare and Medicaid Services (CMS), that publishes payments and transfers of value made by drug and medical device manufacturers and group purchasing organizations (GPOs) to physicians, non-physician practitioners, and teaching hospitals. The public data site at [openpaymentsdata.cms.gov](https://openpaymentsdata.cms.gov) is a DKAN open data catalog that exposes a **free, open, no-authentication REST API** under `/api/1` for querying general payments, research payments, and ownership and investment records by program year.

**Access model:** Read access is completely free. There is **no API key, no token, and no account required** — every endpoint (metastore catalog, search, datastore query, SQL, and CSV/JSON download) was confirmed reachable anonymously over HTTPS on the review date. The records are U.S. government works in the public domain. (The underlying DKAN platform has write/moderation endpoints behind HTTP Basic Auth, but those are for CMS data publishers, not public consumers.)

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/open-payments/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/open-payments/refs/heads/main/apis.yml)

## Tags

- Government Data
- Healthcare
- Open Data
- Transparency
- Payments
- Clinical Data

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## Base URL

`https://openpaymentsdata.cms.gov/api/1`

## APIs

### Open Payments General Payments API

Query general (non-research, non-ownership) payment records — payments and transfers of value from manufacturers and GPOs to covered recipients — via the DKAN datastore query endpoint, one distribution per program year. Supports filtering by recipient NPI, name, state, manufacturer, nature of payment, and amount, plus column selection, sorting, and pagination.

- **Human URL:** [https://openpaymentsdata.cms.gov/about/api](https://openpaymentsdata.cms.gov/about/api)
- **Base URL:** `https://openpaymentsdata.cms.gov/api/1`

### Open Payments Research Payments API

Query research payment records — payments and transfers of value made in connection with a formal research agreement or clinical research protocol, including study names, principal investigators, and associated recipients — through the same datastore query interface, one distribution per program year.

- **Human URL:** [https://openpaymentsdata.cms.gov/about/api](https://openpaymentsdata.cms.gov/about/api)
- **Base URL:** `https://openpaymentsdata.cms.gov/api/1`

### Open Payments Ownership and Investment API

Query ownership and investment interest records — physician (and immediate family member) ownership or investment stakes in reporting manufacturers and GPOs — by program year, useful for surfacing potential financial conflicts of interest.

- **Human URL:** [https://openpaymentsdata.cms.gov/about/api](https://openpaymentsdata.cms.gov/about/api)
- **Base URL:** `https://openpaymentsdata.cms.gov/api/1`

### Open Payments Datastore Query API

The generic DKAN datastore access layer beneath every Open Payments dataset — a structured query endpoint (conditions, properties, sorts, limit, offset over GET or POST), a SQL query endpoint at `/datastore/sql`, and CSV/JSON download. Works against any distribution by dataset id and index, or directly by distribution id.

- **Human URL:** [https://openpaymentsdata.cms.gov/about/api](https://openpaymentsdata.cms.gov/about/api)
- **Base URL:** `https://openpaymentsdata.cms.gov/api/1`

### Open Payments Metastore and Search API

The DCAT-US metastore catalog and search over all Open Payments datasets — list and retrieve dataset metadata (with reference ids to resolve distribution and datastore identifiers), browse data dictionaries, and full-text or faceted search across program years and payment categories.

- **Human URL:** [https://openpaymentsdata.cms.gov/about/api](https://openpaymentsdata.cms.gov/about/api)
- **Base URL:** `https://openpaymentsdata.cms.gov/api/1`

## Example Queries

Every call below is anonymous — no key required.

```
# List datasets (metastore catalog)
GET https://openpaymentsdata.cms.gov/api/1/metastore/schemas/dataset/items?page-size=10

# Resolve a dataset's distribution id
GET https://openpaymentsdata.cms.gov/api/1/metastore/schemas/dataset/items/0380bbeb-aea1-58b6-b708-829f92a48202?show-reference-ids

# Query 2021 General Payment Data (11.5M rows), first 10
GET https://openpaymentsdata.cms.gov/api/1/datastore/query/0380bbeb-aea1-58b6-b708-829f92a48202/0?limit=10

# Structured POST query
POST https://openpaymentsdata.cms.gov/api/1/datastore/query/0380bbeb-aea1-58b6-b708-829f92a48202/0
{
  "conditions": [ { "property": "recipient_state", "value": "CA", "operator": "=" } ],
  "properties": ["covered_recipient_npi", "total_amount_of_payment_usdollars"],
  "sorts": [ { "property": "total_amount_of_payment_usdollars", "order": "desc" } ],
  "limit": 25
}

# Bulk download as CSV
GET https://openpaymentsdata.cms.gov/api/1/datastore/query/0380bbeb-aea1-58b6-b708-829f92a48202/0/download?format=csv

# SQL query
GET https://openpaymentsdata.cms.gov/api/1/datastore/sql?query=[SELECT * FROM resource-id][LIMIT 10];
```

## Common Properties

- [Authentication](authentication/open-payments-authentication.yml) — none required for reads
- [Domain Security](security/open-payments-domain-security.yml)
- [Website](https://openpaymentsdata.cms.gov)
- [Documentation](https://openpaymentsdata.cms.gov/about/api)
- [Program Home](https://www.cms.gov/priorities/key-initiatives/open-payments)
- [Plans](plans/open-payments-plans-pricing.yml)
- [Rate Limits](rate-limits/open-payments-rate-limits.yml)
- [Fin Ops](finops/open-payments-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
