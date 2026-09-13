# Cannot sign in

1. Is it one user (password, MFA, disabled membership) or everyone (Auth outage)?
2. One user: reset email, check invite, check org status.
3. Everyone: Supabase Auth status, email provider, clock skew.
4. Do not create a backdoor login “just for tonight”.
5. If the only owner is locked out: platform break-glass, audited, then force MFA reset.
