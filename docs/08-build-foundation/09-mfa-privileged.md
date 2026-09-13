# MFA for privileged roles

## Steps

1. Enable TOTP in Supabase Auth.
2. After login, if the user’s effective roles include a privileged role and MFA is not enrolled, force `/settings/mfa` before any event route.
3. Privileged roles: Owner, Director, Control Manager, Medical Manager, Safeguarding Lead, Security Manager, Platform Admin.
4. Recovery codes stored by the user, not by us in plaintext.

## Done when

A Control Manager account without MFA cannot open Live.
