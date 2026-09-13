# Audit writer

## Steps

1. Create `lib/audit.ts` → `writeAudit({ action, recordType, recordId, before, after, eventId })`.
2. Always set `organisation_id` from the session, never from the client body.
3. Call it from every privileged write listed in the audit doc.
4. Never throw away a successful write because audit failed — but log a Sentry error and alarm. Prefer a transaction: write + audit together.

## Done when

Creating an event produces an audit row you can see on an `/audit` page restricted to Owner / Director / Control Manager.
