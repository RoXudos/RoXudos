# Permissions engine

## Steps

1. Create `lib/permissions.ts` with the role → permission map from [../03-architecture/06-rbac.md](../03-architecture/06-rbac.md).
2. Create `requirePermission({ user, eventId, permission })` used by every server action.
3. Return 404 for missing event in another tenant, 403 for same tenant without permission.
4. Unit-test the map: Control Operator cannot `safeguarding.read`; Safeguarding Lead can; Owner cannot unless also assigned.

## Rules

- One function. No `if (role === 'admin')` scattered in pages.
- UI reads the same map to hide nav. UI is not authoritative.

## Done when

Unit tests cover each FPR role against a fixture of critical permissions.
