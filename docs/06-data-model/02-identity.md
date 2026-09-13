# Identity

## organisations

| Column | Type | Notes |
| --- | --- | --- |
| name | text | |
| slug | text unique | |
| legal_name | text null | |
| billing_email | text null | |
| region | text | default `eu_west_2` |
| status | text | `active`, `suspended` |

## users

Supabase `auth.users` is the source of login. Keep a public `profiles` table:

| Column | Type | Notes |
| --- | --- | --- |
| id | uuid pk | equals auth.users.id |
| email | text | |
| display_name | text | |
| mfa_privileged_enforced | bool | denormalised helper |

## organisation_memberships

| Column | Type | Notes |
| --- | --- | --- |
| organisation_id | uuid | |
| user_id | uuid | |
| org_role | text | `owner`, `member`, … |
| status | text | `invited`, `active`, `disabled` |

Unique `(organisation_id, user_id)`.

## event_memberships

| Column | Type | Notes |
| --- | --- | --- |
| organisation_id | uuid | |
| event_id | uuid | |
| user_id | uuid | |
| role | text | see RBAC file |
| status | text | |

A user may have one primary event role in FPR. Multiple roles can wait.

## invites

| Column | Type | Notes |
| --- | --- | --- |
| email | text | |
| organisation_id | uuid | |
| event_id | uuid null | |
| role | text | |
| expires_at | timestamptz | |
| accepted_at | timestamptz null | |

## platform_admins

Separate table. Not an org membership. Break-glass only.
