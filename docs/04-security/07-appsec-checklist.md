# Appsec checklist

## Every PR

- [ ] Authz on the new endpoint
- [ ] Zod input validation
- [ ] No raw SQL concatenation
- [ ] No HTML injection in log rendering (users will type `<`)
- [ ] File type check
- [ ] Rate limit on create-incident / create-log / login / invite
- [ ] CSRF protection on cookie session mutations
- [ ] New table has RLS
- [ ] Audit on privileged writes

## Before production

- [ ] Dependency audit (`pnpm audit`, GitHub dependabot)
- [ ] Secret scan
- [ ] Headers: CSP (careful with MapLibre), `X-Content-Type-Options`, `Referrer-Policy`, `Permissions-Policy`
- [ ] Session cookie flags
- [ ] 404 for cross-tenant
- [ ] Backup restore test
- [ ] MFA enforced on privileged roles
- [ ] `security@` mailbox live
- [ ] Rate limits verified

## Do not

- Roll your own crypto
- Store JWTs in localStorage
- Disable RLS “just for the demo”
- Use production data in preview apps
