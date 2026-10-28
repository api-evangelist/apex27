# Apex27

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

Apex27 Limited is a United Kingdom estate agency CRM vendor, founded in 2019 and headquartered in the UK, selling cloud software to sales, lettings and commercial agents for £35 per user per month. It sits in the middle of the UK residential value chain — between the agent and the portals — capturing leads, applicants, listings, viewings, valuations, offers, sales progression and tenancies, then syndicating listings out to Rightmove, Zoopla, OnTheMarket and others. Because the UK has no MLS and no cooperative listing database, that CRM seat is the only practical route a listing takes to market, and Apex27 is one of the private gatekeepers of it. Apex27 does operate two real HTTP APIs — the Apex27 CRM API at api.apex27.co.uk and a per-tenant Portal API that powers agency websites — but neither has a public developer portal. The documentation URL that Apex27's own published n8n node points at, docs.apex27.co.uk, returns 404, and every CRM endpoint returns 401 Unauthorised without a key issued inside a paid tenant. Access is customer-only, not self-serve. RESO does not apply — no RESO Web API or Data Dictionary certification exists for Apex27 or for the UK market at all, since RESO is a NAR/MLS construct with no UK counterpart. Apex27 publishes no open data; the UK's open property layer belongs to HM Land Registry and Ordnance Survey, not to the CRM vendors.

**Areas:** Real Estate · United Kingdom · PropTech · Property Listings · CRM · Estate Agency · Lettings · Rentals · Property Management · Valuation · Tenancy · Conveyancing

## Apex27 on APIs.io

Everything profiled for Apex27 is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/apex27/](https://apis.io/providers/apex27/)** — or go straight to one of the APIs or properties below.

### APIs (33)

- [Apex27 Availability API](https://apis.io/apis/apex27/apex27-availability-api/) — Appointment availability for valuations and viewings.
- [Apex27 Branches API](https://apis.io/apis/apex27/apex27-branches-api/) — Agency branches within the tenant.
- [Apex27 Call Logs API](https://apis.io/apis/apex27/apex27-call-logs-api/) — Telephone activity recorded against a contact.
- [Apex27 Client Portal API](https://apis.io/apis/apex27/apex27-client-portal-api/) — Client-portal authentication and sign-in links.
- [Apex27 Completions API](https://apis.io/apis/apex27/apex27-completions-api/) — Sales completions and progression.
- [Apex27 Contact Orders API](https://apis.io/apis/apex27/apex27-contact-orders-api/) — Orders placed against a contact.
- [Apex27 Contact Referrals API](https://apis.io/apis/apex27/apex27-contact-referrals-api/) — Referrals raised against a contact (conveyancing, mortgage, survey).
- [Apex27 Contacts API](https://apis.io/apis/apex27/apex27-contacts-api/) — Applicants, vendors, landlords, tenants and buyers held in the CRM.
- [Apex27 Documents API](https://apis.io/apis/apex27/apex27-documents-api/) — Documents attached to listings or contacts.
- [Apex27 Enquiries API](https://apis.io/apis/apex27/apex27-enquiries-api/) — Website enquiries and valuation requests.
- [Apex27 Favourites API](https://apis.io/apis/apex27/apex27-favourites-api/) — Saved listings for a portal contact.
- [Apex27 Global Search API](https://apis.io/apis/apex27/apex27-global-search-api/) — Cross-entity search.
- [Apex27 Inspections API](https://apis.io/apis/apex27/apex27-inspections-api/) — Property inspections (lettings management).
- [Apex27 Leads API](https://apis.io/apis/apex27/apex27-leads-api/) — Inbound leads and their pipeline status.
- [Apex27 Listing Issues API](https://apis.io/apis/apex27/apex27-listing-issues-api/) — Maintenance issues raised against a listing.
- [Apex27 Listing Keys API](https://apis.io/apis/apex27/apex27-listing-keys-api/) — Key sets held for a listing, including check-out and check-in.
- [Apex27 Listing Links API](https://apis.io/apis/apex27/apex27-listing-links-api/) — Virtual tours, videos, EPC reports and brochure links on a listing.
- [Apex27 Listing Media API](https://apis.io/apis/apex27/apex27-listing-media-api/) — Images, EPCs, floorplans, brochures and videos on a listing.
- [Apex27 Listing Rooms API](https://apis.io/apis/apex27/apex27-listing-rooms-api/) — Room-by-room detail on a listing.
- [Apex27 Listing Searches API](https://apis.io/apis/apex27/apex27-listing-searches-api/) — Saved applicant listing searches used for matching and alerts.
- [Apex27 Listings API](https://apis.io/apis/apex27/apex27-listings-api/) — Sales, lettings, land and commercial property records.
- [Apex27 Notes API](https://apis.io/apis/apex27/apex27-notes-api/) — Free-text notes attached to a contact or a listing.
- [Apex27 Notifications API](https://apis.io/apis/apex27/apex27-notifications-api/) — In-app notifications to users, branches, listings or contacts.
- [Apex27 Offers API](https://apis.io/apis/apex27/apex27-offers-api/) — Offers made against listings.
- [Apex27 Onboarding Checks API](https://apis.io/apis/apex27/apex27-onboarding-checks-api/) — Compliance and onboarding checklists on a listing.
- [Apex27 Search Regions API](https://apis.io/apis/apex27/apex27-search-regions-api/) — Named geographic search regions.
- [Apex27 Statistics API](https://apis.io/apis/apex27/apex27-statistics-api/) — Portal inventory statistics.
- [Apex27 Tasks API](https://apis.io/apis/apex27/apex27-tasks-api/) — Work items assigned to users.
- [Apex27 Tenancies API](https://apis.io/apis/apex27/apex27-tenancies-api/) — Tenancy agreements and their lifecycle.
- [Apex27 Users API](https://apis.io/apis/apex27/apex27-users-api/) — CRM users within the tenant.
- [Apex27 Valuations API](https://apis.io/apis/apex27/apex27-valuations-api/) — Market appraisals and valuation appointments.
- [Apex27 Viewings API](https://apis.io/apis/apex27/apex27-viewings-api/) — Viewing appointments.
- [Apex27 Webhooks API](https://apis.io/apis/apex27/apex27-webhooks-api/) — Webhook subscription management.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Apex27 Webhooks](https://apis.io/asyncapis/apex27/apex27-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [apex27](https://apis.io/servers/apex27/apex27/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Apex27 Agentic Access](https://apis.io/agentic-access/apex27/apex27-agentic-access/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Apex27 Vocabulary](https://apis.io/vocabularies/apex27/apex27-vocabulary/)

#### Collections (2)

Postman and Open Collection request collections.

- [Apex27 CRM API](https://apis.io/collections/apex27/open-apex27-crm-api/)
- [Apex27 Portal API](https://apis.io/collections/apex27/open-apex27-portal-api/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Apex27 Crm Api Overlay](https://apis.io/overlays/apex27/apex27-crm-api-overlay/)
- [Apex27 Portal Api Overlay](https://apis.io/overlays/apex27/apex27-portal-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Apex27 Authentication](https://apis.io/security/apex27/apex27-authentication/)
- [Apex27 Domain Security](https://apis.io/security/apex27/apex27-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://apex27.co.uk/)
- [Pricing](https://apex27.co.uk/estate-agent-software-pricing)
- [Sign up](https://apex27.co.uk/estate-agent-software-sign-up)
- [Support](https://apex27.co.uk/contact-apex27)
- [Changelog](https://apex27.co.uk/crm-changelog)
- [Blog](https://apex27.co.uk/estate-agency-blog)
- [Terms of service](https://apex27.co.uk/terms-of-use)
- [Privacy policy](https://apex27.co.uk/privacy-policy)

## API Evangelist rating

**Kin Score 33.5** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 25.4 |
| Contract governance | 8.3 |
| Operational transparency | 23.7 |
| Developer ergonomics | 30.4 |
| Access clarity | 44.7 |

**Agent readiness 20.0** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 24.5** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/apex27/](https://apis.io/providers/apex27/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Apex27: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/apex27/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
