# Credentials and vendors

## credentials

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| public_id | text | |
| person_id | uuid null | |
| holder_name | text | |
| organisation_name | text null | |
| kind | text | staff, security, contractor, vendor, artist, production, vip, media, emergency_services |
| status | text | draft, active, suspended, expired, revoked |
| valid_from | date | |
| valid_to | date | |
| zone_ids | uuid[] | allow-list |
| qr_secret | text | random, not the public_id alone |

QR payload: signed token containing credential id + event id. Rotate secret on revoke.

## vendors

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| name | text | |
| kind | text | food, bar, trader, sponsor, contractor, supplier |
| status | text | applied, approved, rejected, withdrawn |
| pitch_location_id | uuid null | |
| power_notes | text null | |
| water_notes | text null | |
| arrival_at | timestamptz null | |
| departure_at | timestamptz null | |
| payment_notes | text null | |

## vendor_documents

| Column | Type | Notes |
| --- | --- | --- |
| vendor_id | uuid | |
| kind | text | insurance, risk_assessment, licence, other |
| expires_on | date null | |
| file_id | uuid | |
| status | text | valid, expiring, expired, missing |

Nightly job: if `expires_on` within 30 days → `expiring`; if past → `expired`.
