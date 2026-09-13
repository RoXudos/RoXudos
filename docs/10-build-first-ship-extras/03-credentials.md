# Credentials v1

## Steps

1. Create credential for a person or a named holder.
2. Kind, dates, zone allow-list, status.
3. Generate QR (signed payload).
4. Printable simple pass page (A6 / phone).
5. Gate staff later can scan in Phase B. FPR: visual check + QR exists.
6. Revoke rotates the secret and audits.

## Access control

Zones on the map are the same IDs as `credential.zone_ids`. A pass for General Admission cannot list Backstage.

## Done when

A vendor pass and a staff pass have different zones and the QR payload is not guessable from the public ID alone.
