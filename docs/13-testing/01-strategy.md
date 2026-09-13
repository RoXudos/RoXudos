# Test strategy

## Layers

1. **Unit** — permissions map, public ID format, programme NOW/NEXT, document expiry state, staff-on-site derivation
2. **RLS / API** — cross-tenant and restricted modules
3. **E2E** — sign in, log, incident timeline, task, map click, clone, report
4. **Manual rehearsal** — staging script
5. **Restore drill** — backups

Do not chase 100% coverage. Chase the leak and the slow log form.

## Data

Factories create org A, org B, and one event each. Never use production dumps.
