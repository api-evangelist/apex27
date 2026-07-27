---
name: Capture a lead and book a viewing in Apex27
description: Take an inbound property enquiry, create or match the contact, raise the lead, find a real appointment slot and book the viewing against the listing.
api: openapi/apex27-crm-api-openapi.yml
operations: [listContacts, createContact, createLead, getViewingAvailability, createListingViewing, createTask, createContactNote, getListing]
generated: '2026-07-26'
method: generated
---

# Capture a lead and book a viewing

## Before you start

Tenant `x-api-key` header, base URL `https://api.apex27.co.uk`. No sandbox exists — anything you do
here happens in the agency's live CRM. Confirm with the operator before writing.

## Steps

1. **Match before you create.** Call `listContacts` filtered by `email`, or by `e164` for a phone
   number, or by `externalId` if your system already owns an identifier. Set `single` when you want
   one record back. Creating a duplicate contact in an estate agency CRM is a real operational
   problem — always attempt the match first.

2. **Create the contact only on a miss.** `createContact` requires `firstName` and `lastName`;
   everything else rides in the same JSON body. Keep the returned contact id.

3. **Raise the lead.** `createLead` records the enquiry itself. Leads carry a `status` from the
   fixed set `New`, `Approached`, `Awaiting Action`, `Completed`, `Closed`, and can be filtered by
   `branchId`, `contactId` and `listingId` — so bind the lead to both the contact and the listing
   the enquiry was about.

4. **Check availability before proposing a time.** `getViewingAvailability` accepts `postal_code`
   or `listing_id`, plus `date_start`, `date_end`, `time_start` and `time_end`. Do not invent a
   slot; ask the API what is free. (`getValuationAvailability` is the equivalent for appraisals.)

5. **Book the viewing against the listing.** `createListingViewing` sits under
   `/listings/{listingId}/viewings`, so you must have the listing id — confirm it with `getListing`
   if the enquiry only gave you a reference.

6. **Leave a trail.** `createContactNote` records what the applicant actually said, and `createTask`
   assigns the follow-up to a negotiator (`assignedTo`, `createdBy`, and a required `description`).

## Rules

- **There is no idempotency key.** If a `createContact`, `createLead` or `createListingViewing` call
  times out, do **not** replay it. Re-query with `listContacts` / `listLeads` filters to find out
  whether it landed, then act on the answer.
- Contacts and listings support `PATCH` for partial updates (`patchContact`, `patchListing`). Most
  other resources are `PUT`-only, which means a full replace — read before you write or you will
  silently blank fields.
- A `401` means the key is missing or not valid for this tenant. A `404` on a plausible-looking path
  usually means the resource name is wrong — Apex27 pluralises (`/listings`, not `/properties`).
