# Medical extras

DPIA must be in progress. Module flag off on production until [../02-company-and-legal/11-dpia-medical-and-safeguarding.md](../02-company-and-legal/11-dpia-medical-and-safeguarding.md) is signed.

## Steps

1. `medical_incident_extras` table + RLS.
2. UI only if `medical.read`.
3. General incident wall shows category Medical, location, priority, status — not treatment.
4. Audit reads of extras.
5. Ambulance / hospital fields and timestamps.
6. Reports include medical counts only for permitted exporters.

## Done when

A Control Operator cannot fetch extras via the API. A Medical Manager can. Tests prove it.
