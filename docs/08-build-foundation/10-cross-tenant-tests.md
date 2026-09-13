# Cross-tenant tests

Automate the matrix in [../04-security/03-tenant-isolation.md](../04-security/03-tenant-isolation.md).

Minimum automated set:

- Org A owner cannot GET Org B event
- Org A operator cannot LIST Org B incidents (table may not exist yet — add these tests as tables appear)
- Invite token for Org A cannot be used to join Org B

Run in CI.

## Done when

CI fails if someone comments out an RLS policy.
