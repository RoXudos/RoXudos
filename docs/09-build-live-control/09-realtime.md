# Realtime

## Steps

1. Per-event channel, authorised.
2. Subscribe from Live, Log, Incidents, Map, Programme, Comms.
3. On `INSERT/UPDATE` of operational tables, refetch the affected query or patch the cache.
4. Redacted payloads only.
5. On disconnect: banner + 15s poll.

## Done when

Two operators, two browsers, one event: a log line and an incident status change appear on the other screen within two seconds on a healthy network.

If it does not, do not fake it with a client-only prepend that never arrived at the server.
