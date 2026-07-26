# Apex27 (apex27)

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
