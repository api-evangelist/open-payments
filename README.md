# CMS Open Payments (open-payments)

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
