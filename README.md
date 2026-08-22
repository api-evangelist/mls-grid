# MLS Grid (mls-grid)

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
