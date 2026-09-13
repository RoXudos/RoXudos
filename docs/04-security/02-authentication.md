# Authentication

## FPR method

- Email + password via Supabase Auth
- MFA TOTP required for: Organisation Owner, Event Director, Event Control Manager, Medical Manager, Safeguarding Lead, Security Manager, Platform Admin
- MFA optional but encouraged for Control Operator
- Invite-only users. No public self-serve signup for FPR. The owner invites.

Magic links are allowed as a backup if you want fewer passwords. Still require MFA on privileged roles.

## Sessions

- HTTP-only cookies
- Secure + SameSite
- Idle timeout: 12 hours for general, 8 hours for privileged roles during a live event is a product decision — do not kick an operator every 15 minutes on a 16-hour shift. Prefer re-auth for dangerous actions (emergency activate, export restricted report) instead of aggressive idle logout during `event.status = live`.

## Lockout and recovery

- Rate-limit sign-in
- Email recovery through the transactional provider
- Owner can revoke sessions for a user
- Stolen-device runbook: revoke, rotate, audit recent reads

## Passkeys

Phase B+. Do not block FPR on WebAuthn.

## Staff who should not log in yet

Volunteers and contractors may exist as records without user accounts. Create accounts only when that person needs the app.
