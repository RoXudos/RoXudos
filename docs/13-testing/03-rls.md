# RLS tests

Run against local Supabase with two JWTs.

Must fail closed:

- Org B cannot read Org A incidents, log, files, messages, people, credentials, reports
- Operator cannot read medical extras or safeguarding details
- Signed URL for Org A rejected for Org B
- Realtime join for the other event rejected

If these are skipped “because local auth is hard”, FPR is not done.
