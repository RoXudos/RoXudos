# Tenant isolation

## Engineering rules

- `organisation_id` on every tenant table
- RLS enabled on every tenant table before it is used
- Integration tests that attempt cross-tenant reads and expect failure
- No shared sequences that leak counts across tenants in a useful way (public IDs are per event, not global)
- Sentry scrubbing must not include row bodies from other tenants — better: do not log row bodies

## Test matrix (minimum)

| Attempt | Expected |
| --- | --- |
| User in Org A opens event ID from Org B | 404, not 403 with a title |
| User in Org A queries incidents with Org B UUID | empty / 404 |
| Signed URL from Org A file used by Org B user | deny |
| Realtime subscribe to Org B event channel | deny |
| Search “Smith” across platform | only Org A people |

Return **404** for out-of-tenant resources so you do not confirm that an ID exists.

## Support access

Platform Admin support view:

- requires a reason field
- time-boxed
- audited
- customer-visible later if you want trust (“Livehelm support accessed this event at 14:02”)
