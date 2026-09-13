# Programme

## programme_stages

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| name | text | Main Stage |
| location_id | uuid null | |
| sort_order | int | |

## programme_items

| Column | Type | Notes |
| --- | --- | --- |
| stage_id | uuid | |
| title | text | Headliner |
| kind | text | performance, activity, parade, other |
| start_at | timestamptz | |
| end_at | timestamptz null | |
| artist_name | text null | FPR: name only |
| notes | text null | |
| status | text | scheduled, live, done, cancelled, delayed |

NOW = item where now is in [start, end) or the latest started not done.  
NEXT = the following scheduled item on that stage or event-wide.

Compute in a query. Do not store NOW as a fragile flag unless you also recompute on write.

Authorised updates are immediately visible via realtime.
