# Site

## sites

An event may have one site in FPR. Keep the table anyway.

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| name | text | |
| center_lat | float null | |
| center_lng | float null | |
| default_zoom | int null | |
| boundary | jsonb null | GeoJSON polygon |

## zones

| Column | Type | Notes |
| --- | --- | --- |
| site_id | uuid | |
| name | text | General Admission |
| geometry | jsonb | polygon |
| access_level | text | public, staff, production, control, medical, … |
| colour | text | |

## locations

| Column | Type | Notes |
| --- | --- | --- |
| site_id | uuid | |
| zone_id | uuid null | |
| name | text | Main Stage |
| type | text | see maps architecture |
| geometry | jsonb | point or polygon |
| notes | text null | |
| accessible | bool | |
| status | text | open, closed, limited |

## accessibility_assets

Optional child of location or standalone:

`wheelchair_access`, `accessible_toilet`, `viewing_platform`, `quiet_area`, `hearing_loop`, `bsl`, `accessible_transport`, `assistance_dogs`, `accessible_parking`, `step_free_route`, `accessible_shuttle`

Organisers tick these during planning. They appear as map filters.
