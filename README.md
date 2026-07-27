# MLS Grid (mls-grid)

The MLS Grid is a United States MLS data-distribution cooperative created by a network of Multiple Listing Services to give brokers, MLSs and technology vendors ONE normalized data feed, ONE license agreement and ONE compliance process instead of dozens of per-MLS RETS and Web API feeds. It ingests listing data from participating MLSs, converts it to the RESO Data Dictionary, and republishes it as a single RESO Web API (OData v4) replication surface. Its API posture is the sector archetype: the documentation is genuinely public and complete, and MLS Grid is RESO-certified for Data Dictionary 2.0 and Web API Server Core 2.0.0 — but nothing is reachable without credentials, and credentials require a signed Master Data License Agreement plus approval from each originating MLS.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mls-grid/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mls-grid/refs/heads/main/apis.yml)

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## Tags

- Real Estate
- United States
- MLS
- RESO
- Property Listings
- IDX
- PropTech
- OData
- Data Licensing

## APIs

### MLS Grid Web API v2

MLS Grid's RESO Web API — a replication-oriented OData v4 surface over listing data normalized to the RESO Data Dictionary and pooled from the participating MLSs. Documented entity sets are Property, Member, Office, OpenHouse and Lookup, with Media, Rooms and UnitTypes available through `$expand`. Replication is driven by `$filter` on `OriginatingSystemName` plus `ModificationTimestamp`, paged with `@odata.nextLink`. Probed anonymously on 2026-07-26, the service root, `/Property` and `$metadata` all returned HTTP 401.

- **Human URL:** [https://docs.mlsgrid.com/api-documentation/api-version-2.0.md](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- **Base URL:** `https://api.mlsgrid.com/v2/`

#### Tags

- Real Estate
- MLS
- RESO
- OData
- Property Listings
- Replication

#### Properties

- [Documentation](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- [Documentation](https://docs.mlsgrid.com/master.md)
- [Metadata](https://api.mlsgrid.com/v2/$metadata) — HTTP 401 anonymously
- [License Agreement](https://www.mlsgrid.com/s/MLS-GRID-Data-License-Agreement.pdf)
- [Support](mailto:support@mlsgrid.com)

## RESO Posture

RESO-certified and listed in the RESO directory of certified organizations under Technology Company, UOI `T00000045`, status "Certified Current" (directory date 2023-04-06):

- **RESO Data Dictionary 2.0** — status `certified`
- **RESO Web API Server Core 2.0.0** — status `certified`

Certification is not reachability. The OData `$metadata` document — the machine-readable contract a RESO Web API is certified against — returns HTTP 401 to anonymous callers.

## Access Gate

Licence agreement. A developer must:

1. Sign the MLS Grid Master Data License Agreement, accepted through the MLS Grid online licensing portal.
2. Have a data subscription created and a licensee added.
3. Be **approved by the originating MLS**.

Only then is a long-lived OAuth 2.0 bearer token generated on the token tab of the subscription in the MLS Grid web application. There is no self-serve signup, no public sandbox, and no published price card.

## Common Properties

- [Website](https://www.mlsgrid.com/)
- [Documentation](https://docs.mlsgrid.com/)
- [Documentation index (llms.txt)](https://docs.mlsgrid.com/llms.txt)
- [Documentation sitemap](https://docs.mlsgrid.com/sitemap.md)
- [MLS Grid web application (member login)](https://app.mlsgrid.com/)
- [Interest form](https://www.mlsgrid.com/interest-form)
- [MLS Grid Data License Agreement (PDF)](https://www.mlsgrid.com/s/MLS-GRID-Data-License-Agreement.pdf)
- [FAQ](https://www.mlsgrid.com/faq)
- [Resources](https://www.mlsgrid.com/resources)
- [Overview](https://www.mlsgrid.com/overview)
- [About](https://www.mlsgrid.com/whoisthemlsgrid)
- [Approved vendors](https://www.mlsgrid.com/vendors)
- [News](https://www.mlsgrid.com/news)
- [Contact](https://www.mlsgrid.com/contact-us)
- [Support](mailto:support@mlsgrid.com)
- [GitHub Organization](https://github.com/mlsgrid) — 0 public repositories
- [RESO certification directory entry (UOI T00000045)](https://certification.reso.org/summary/T00000045)
- [RESO list of certified organizations](https://www.reso.org/certificates/)
- [RESO Web API specification](https://www.reso.org/reso-web-api/)
- [RESO Data Dictionary](https://www.reso.org/data-dictionary/)

## Artifacts

Harvested from the public documentation on 2026-07-26. Nothing below was derived from a
machine-readable contract — the OData `$metadata` document returns HTTP 401 anonymously.

- `authentication/mls-grid-authentication.yml` — long-lived OAuth 2 bearer profile, issuance gate, gzip and media User-Agent requirements
- `conventions/mls-grid-conventions.yml` — OData replication semantics: pagination, filter grammar, prefixed keys, signal fields, licence-in-payload
- `errors/mls-grid-problem-types.yml` — documented and observed error conditions plus the OData error envelope
- `rate-limits/mls-grid-rate-limits.yml` — 2 rps / 7,200 hr / 40,000 day / 4 GB hr, suspension and reinstatement
- `changelog/mls-grid-changelog.yml` — 36 dated release notices (2025-02-18 → 2026-06-05)
- `lifecycle/mls-grid-lifecycle.yml` — v2 URI versioning, deprecation practice, 7-day delete retention, no public status page or SLA
- `conformance/mls-grid-conformance.yml` — RESO certification evidence plus OData/OAuth/RFC conformance assertions
- `data-model/mls-grid-data-model.yml` — entity sets, expanded resources and relationships
- `vocabulary/mls-grid-vocabulary.yml` — resources, signal fields, licence flags, enumerations, 37 originating systems with key/field prefixes
- `examples/` — the Property and Lookup records published verbatim in the docs
- `packages/mls-grid-packages.yml` — no first-party SDK; one third-party PyPI library
- `llms/mls-grid-llms.txt` — the documentation site's own llms.txt, saved verbatim
- `well-known/mls-grid-well-known.yml` — every `/.well-known/` probe missed; absence is the finding
- `security/mls-grid-domain-security.yml` — TLS/HSTS/DNS posture across all four hosts

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
