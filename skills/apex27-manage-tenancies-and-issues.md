---
name: Run Apex27 lettings management — tenancies, inspections, issues and keys
description: Work the lettings side of the Apex27 CRM API — track live tenancies, run inspections, raise and resolve maintenance issues, and manage key custody.
api: openapi/apex27-crm-api-openapi.yml
operations: [listTenancies, getTenancy, patchTenancy, listListingInspections, createListingInspection, listListingIssues, createListingIssue, updateListingIssue, listListingKeys, checkOutListingKey, checkInListingKey, createTask, listListingOnboardingChecks, updateListingOnboardingCheck]
generated: '2026-07-26'
method: generated
---

# Run Apex27 lettings management

## Before you start

Tenant `x-api-key` header, base URL `https://api.apex27.co.uk`. This is the lettings-management
half of the CRM, and everything here touches a live tenancy — a real tenant in a real home. Confirm
with the operator before any write.

## Steps

1. **Find the live book.** `listTenancies` filters on `activeOnly`, `listingId`, `branchId`,
   `tenantId` and `minDtsUpdated`. Start with `activeOnly` set, page with `page` / `pageSize`
   (25-250), then use `minDtsUpdated` for subsequent incremental runs.

2. **Read one tenancy before you change it.** `getTenancy` returns the record. Tenancy is one of the
   few resources that supports `PATCH` — use `patchTenancy` for a partial update rather than
   replacing the object.

3. **Run inspections.** `listListingInspections` sits under `/listings/{listingId}/inspections`;
   `listInspections` gives you the cross-listing view. Record a new visit with
   `createListingInspection`.

4. **Raise and work maintenance issues.** `createListingIssue` opens an issue against the property;
   `listListingIssues` reads the open book for one listing; `updateListingIssue` is a `PUT`, so
   fetch with `getListingIssue`, amend, and write the whole object back. Pair each issue with a
   `createTask` so a named person owns it.

5. **Manage key custody.** `listListingKeys` shows the key sets held for a property.
   `checkOutListingKey` and `checkInListingKey` are distinct `POST` operations at
   `/listings/{listingId}/keys/{keyId}/check-out` and `.../check-in`. Key custody is an audit trail
   — check keys back in promptly and never fabricate a movement.

6. **Keep compliance current.** `listListingOnboardingChecks` and `updateListingOnboardingCheck`
   carry the onboarding/compliance checklist on a listing. In UK lettings this is where gas safety,
   EPC and licensing evidence is tracked. Read it before you market a property.

## Rules

- **No idempotency key exists.** A replayed `checkOutListingKey` or `createListingIssue` produces a
  duplicate custody event or a duplicate issue. On a timeout, re-read with `listListingKeys` /
  `listListingIssues` and decide from the actual state.
- `PUT` on issues, inspections and keys is a full replace. Read-modify-write, always.
- Apex27 publishes no response schema, so field names in the returned objects are only discoverable
  from a live authenticated call in your own tenant. Do not assume.
- No status page and no SLA exist. If the API is unreachable, you have no upstream signal to check —
  fail closed and alert the operator.
