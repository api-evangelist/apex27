---
name: Manage Apex27 webhook subscriptions
description: Register, inspect and retire webhook subscriptions on the Apex27 CRM API, and fall back to timestamp polling because Apex27 publishes no event catalogue.
api: openapi/apex27-crm-api-openapi.yml
operations: [listWebhooks, createWebhook, getWebhook, updateWebhook, deleteWebhook, listListings, listContacts, listTenancies]
generated: '2026-07-26'
method: generated
---

# Manage Apex27 webhook subscriptions

## What you are working with

Webhook subscriptions are a first-class resource on the Apex27 CRM API with full CRUD at
`/webhooks`. Apex27's own integration page confirms webhooks are part of the API surface.

**But Apex27 publishes no event-type catalogue, no payload schema and no delivery, retry, signing or
replay semantics.** The event names exist only inside a paying tenant. Nothing in this repository
guesses them, and neither should you.

## Steps

1. **Read what already exists first.** Call `listWebhooks`. In a live agency tenant there are often
   subscriptions you did not create — portal feeds, accounting sync, a previous integration. Never
   assume the list is empty.

2. **Discover the event vocabulary from inside the tenant.** Inspect an existing subscription with
   `getWebhook` to learn the field names and the event identifiers this tenant actually uses. If
   there are no existing subscriptions, ask Apex27 support — the vocabulary is not published.

3. **Create the subscription.** `createWebhook` takes an opaque JSON body (Apex27's own client passes
   it straight through). Register your endpoint, then verify with `getWebhook` that it stored what
   you sent.

4. **Update and retire deliberately.** `updateWebhook` is a `PUT` — a full replace. Fetch with
   `getWebhook`, modify, then write the whole object back. `deleteWebhook` removes it.

5. **Build the polling fallback anyway.** Because delivery semantics are unpublished, do not treat
   webhooks as an exactly-once event stream. Run a reconciliation poll alongside them:
   `listListings`, `listContacts` and `listTenancies` all accept `minDtsUpdated`, and listings and
   saved searches also accept `minDtsCreatedUpdated`. Poll on a timer, diff against your own state.

## Rules

- Verify inbound deliveries yourself. No signature scheme, shared secret or source IP range is
  published, so authenticate the callback at your own layer (a secret path segment, mTLS, or a
  reconciliation read against the API before you act on the payload).
- Assume at-least-once and possibly zero delivery. Make your handler idempotent on your side — the
  API gives you nothing to do it with on theirs.
- All webhook routes are key-gated: they returned `401`, not `404`, on anonymous probes.
