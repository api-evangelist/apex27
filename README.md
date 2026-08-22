# Apex27 (apex27)

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

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/apex27/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/apex27/refs/heads/main/apis.yml)

## Tags

- Real Estate
- United Kingdom
- PropTech
- Property Listings
- CRM
- Estate Agency
- Lettings
- Rentals
- Property Management
- Valuation
- Tenancy
- Conveyancing

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

### Apex27 CRM API

The Apex27 CRM API is the vendor's REST interface over the estate agency CRM, covering contacts, leads, listings and their media, rooms, keys, notes, offers, viewings, valuations, inspections, issues and onboarding checks, plus branches, users, tasks, documents, tenancies, completions, call logs, notifications, saved listing searches, search regions, global search, client portal sign-in links and webhook subscriptions. It authenticates with an `x-api-key` request header and paginates with `page` and `pageSize` (25-250). The host is live — every probed collection returned HTTP 401 Unauthorised — but there is no public reference documentation; the documentation URL declared in Apex27's own published n8n credential (https://docs.apex27.co.uk) returned HTTP 404 on 2026-07-26. Keys are issued to paying customers inside the CRM admin panel, so this is a customer-only surface, not a self-serve developer API.

- **Human URL:** [https://apex27.co.uk/integration/n8n](https://apex27.co.uk/integration/n8n)
- **Base URL:** `https://api.apex27.co.uk`

#### Tags

- Real Estate
- CRM
- Property Listings
- Lettings
- Tenancy
- United Kingdom

#### Properties

- [Documentation](https://apex27.co.uk/integration/n8n)
- [Integrations](https://apex27.co.uk/integrations)
- [npm Package](https://www.npmjs.com/package/n8n-nodes-apex27crm)
- [Sign Up](https://apex27.co.uk/estate-agent-software-sign-up)

### Apex27 Portal API

The Apex27 Portal API is the per-tenant, website-facing API that drives search and enquiry on Apex27-built agency websites. Its documented operations are get-listings, get-listing, get-search-options, get-statistics, contact, request-valuation, add-favourite and remove-favourite, spanning sales, lettings and land inventory with sort and filter options. It has no shared host — the base URL is the agency's own portal domain with /api appended (the vendor's published credential uses the placeholder https://portal-abcd1234.apex27.co.uk/api) — and it authenticates with an `api_key` query-string parameter issued under Admin Panel > Websites > [Your Website] > Integrations. No public documentation page for it was found.

- **Human URL:** [https://apex27.co.uk/websites](https://apex27.co.uk/websites)

#### Tags

- Real Estate
- Property Listings
- Property Search
- Valuation
- United Kingdom

#### Properties

- [Documentation](https://apex27.co.uk/websites)
- [npm Package](https://www.npmjs.com/package/n8n-nodes-apex27portal)

## Common Properties

- [Website](https://apex27.co.uk/)
- [Sign Up](https://apex27.co.uk/estate-agent-software-sign-up)
- [Pricing](https://apex27.co.uk/estate-agent-software-pricing)
- [Features](https://apex27.co.uk/estate-agent-software-features)
- [Integrations](https://apex27.co.uk/integrations)
- [Changelog](https://apex27.co.uk/crm-changelog)
- [Blog](https://apex27.co.uk/estate-agency-blog)
- [Support](https://apex27.co.uk/contact-apex27)
- [Terms of Service](https://apex27.co.uk/terms-of-use)
- [Privacy Policy](https://apex27.co.uk/privacy-policy)
- [Compliance](https://apex27.co.uk/acceptable-use-policy)
- [LinkedIn](https://www.linkedin.com/company/apex27)

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
