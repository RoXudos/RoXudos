# Vercel environments

1. Import the `livehelm` GitHub repo.
2. Framework: Next.js.
3. Production branch: `main`.
4. Preview: pull requests, pointed at **staging** Supabase, never production.
5. Create environment variables per [09-env-and-secrets.md](09-env-and-secrets.md).

## Project settings

- Node LTS
- Region: prefer Frankfurt or London if offered for serverless. Document the actual region in the subprocessor list.

## Custom domains

- `app.yourdomain.com` production
- `staging.yourdomain.com` staging, password-wall or allowlist if you can

## Deploy freeze

See [../12-production/06-deploy-freeze.md](../12-production/06-deploy-freeze.md).
