---
name: Sync Apex27 listings into an external system
description: Pull the agency's live property inventory out of the Apex27 CRM API, expand the media and rooms an agent cares about, and keep it current with incremental polling.
api: openapi/apex27-crm-api-openapi.yml
operations: [listListings, getListing, listListingMedia, listListingRooms, listListingLinks, listSearchRegions, listBranches]
generated: '2026-07-26'
method: generated
---

# Sync Apex27 listings

## Before you start

- You need a tenant API key. It is issued inside the Apex27 CRM admin panel of a **paying tenant**.
  There is no self-serve developer signup, no sandbox and no test key. If you do not have a key,
  stop — every route returns `401 {"success":false,"message":"Unauthorised.","errors":[]}`.
- Send the key as the `x-api-key` **request header** on every call. Base URL
  `https://api.apex27.co.uk`.
- Apex27 publishes no response schemas. Treat every response body as untyped JSON and code
  defensively — do not assume a field exists.

## Steps

1. **Establish the tenant shape.** Call `listBranches` and `listSearchRegions` once and cache them.
   Listings carry `branchId` and `mainSearchRegionId`, and you will need the lookups to render them.

2. **Page the inventory.** Call `listListings` with `page` starting at 1 and `pageSize` at your
   chosen size. `pageSize` must be **between 25 and 250** — the API rejects values outside that
   band. Keep incrementing `page` until a page comes back short.

3. **Scope the pull.** Narrow with the filters rather than pulling everything:
   `transactionType` (`Sale`, `Rent`, `Land`, `Commercial Sale`, `Commercial Rent`), `branchId`,
   `city`, `minBeds`, `minPrice`, `maxPrice`, `websiteStatus`. Set `archived` only when you
   deliberately want withdrawn stock.

4. **Expand in the list call, not in N+1 calls.** `listListings` accepts `includeImages`,
   `includeRooms`, `includeOffers`, `includeValuations` and `includeContacts`. Turning these on is
   far cheaper than calling `getListing` per record. Use `getListing` only for a single record you
   already have an id for.

5. **Pull media and detail where the expansion is not enough.** `listListingMedia` takes the media
   collection as a **path segment**: one of `images`, `epcs`, `floorplans`, `brochures`, `videos`.
   `listListingLinks` takes `virtual-tours`, `videos`, `epc-reports` or `brochures`.
   `listListingRooms` returns room-level detail.

6. **Go incremental after the first full pull.** Record the timestamp of your run, then poll
   `listListings` with `minDtsUpdated` (or `minDtsCreatedUpdated` for creations) set to it. This is
   the supported change-detection mechanism.

## Rules

- **Do not retry a write blindly.** Apex27 has no idempotency key and no documented retry
  semantics. Reads are safe to retry; writes are not.
- **No rate limits are published.** Back off on your own schedule — start conservative.
- Errors come back as `{success, message, errors}` served as `text/json`, not RFC 9457 problem
  details. Branch on the HTTP status, not on a `type` URI.
- Nothing about this API is versioned. There is no `/v1` (it returns 404) and no version header, so
  a breaking change will arrive without a signal. Pin nothing; validate what you receive.
