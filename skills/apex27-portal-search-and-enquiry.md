---
name: Search an Apex27 agency website and submit an enquiry
description: Use the per-tenant Apex27 Portal API to search an agency's public inventory, render listings, capture an enquiry or valuation request, and manage a visitor's saved properties.
api: openapi/apex27-portal-api-openapi.yml
operations: [getSearchOptions, getListings, getListing, contactAgent, requestValuation, addFavourite, removeFavourite, getStatistics]
generated: '2026-07-26'
method: generated
---

# Search an Apex27 agency website and submit an enquiry

## Before you start

- The Portal API is **per-tenant**. There is no shared host: the base URL is the agency's own
  Apex27-built website domain with `/api` appended.
- Authentication is an `api_key` **query-string parameter** — not a header, and not the same key as
  the CRM API. It is issued under Admin Panel > Websites > [Your Website] > Integrations tab >
  Portal API section.
- This surface is public-facing by design: it drives search and enquiry on the agency's website.

## Steps

1. **Load the filter vocabulary first.** Call `getSearchOptions`. It returns the regions, property
   types and bands this particular portal accepts. Different agencies configure different options —
   do not hard-code them.

2. **Search.** `getListings` needs either `transaction_type` or `property_class`. Mind the
   vocabulary: the Portal uses `sales`, `lettings`, `commercial_sales`, `commercial_lettings`,
   `holiday_lettings`, `land` — **not** the CRM API's `Sale` / `Rent` / `Land` / `Commercial Sale` /
   `Commercial Rent`. Getting this wrong is the most common mistake when working across both APIs.

3. **Filter and sort.** `city`, `location`, `min_price`, `max_price`, `min_beds`, `max_beds`,
   `min_baths`, `property_type`, `keywords[]`, `search_region_ids[]`, `min_gross_yield`, and the
   `sw` / `ne` bounding-box pair for map search. `include_sstc` (as `1` or `0`) controls whether
   Sold STC and Let Agreed stock appears. Sort with `featured`, `newest`, `oldest`, `highest_price`,
   `lowest_price`, `nearest` or `newly_instructed`. Page with `page` and `page_size`.

4. **Render images at the right size.** `image_size` accepts `tiny` (320x180), `small` (640x360),
   `medium` (1280x720, the default), `large` (2560x1440) or `custom` with `image_width` /
   `image_height`. `image_count` caps how many come back. Ask for what you will display.

5. **Retrieve one property.** `getListing` takes `id` plus the same image options.

6. **Capture the enquiry.** `contactAgent` posts **form-encoded** (`application/x-www-form-urlencoded`),
   not JSON. It requires `first_name`, `last_name` and `email`, and targets the enquiry with exactly
   one of `listing_id`, `listing_reference` or `branch_id`. The intent flags
   `request_listing_details`, `request_viewing` and `request_valuation` are sent as `1` or `0`.

7. **Or capture a valuation lead.** `requestValuation` requires `first_name`, `last_name`, `email`,
   `address_1`, `city`, `postal_code` and `transaction_type`, and optionally takes `tenure`
   (`freehold`, `leasehold`, `share_of_freehold`, `commonhold`), `condition`, `furnished`,
   `outside_spaces[]` and a `latitude` / `longitude` pair.

8. **Saved properties and reporting.** `addFavourite` and `removeFavourite` both take `listing_id`
   and `contact_id`. `getStatistics` returns portal inventory stats for a `transaction_type` over an
   optional `date_start` / `date_end` range.

## Rules

- The `api_key` travels in the query string, so it lands in server logs, browser history and
  referrers. Proxy these calls server-side; never ship the portal key to a browser.
- Enquiry submissions are unauthenticated writes from the public internet in practice — rate-limit
  and CAPTCHA them at your layer. Apex27 publishes no rate limits of its own.
- There is no idempotency key. A double-submitted enquiry form creates a duplicate lead in the
  agency's CRM. Debounce on your side.
- The tenure vocabulary is England-and-Wales only. Scottish and Northern Irish tenure has no
  representation in this API.
