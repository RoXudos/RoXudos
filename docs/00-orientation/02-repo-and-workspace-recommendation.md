# Repo and workspace recommendation

## Recommendation

**Do not build Livehelm in this GitHub repository.**

This repository (`RoXudos/RoXudos`) is a GitHub profile repository. Its root `README.md` is what GitHub shows on the public profile. It is the wrong place for application code, secrets, CI, and a production SaaS history.

Create a **new dedicated product repository** before writing application code.

Keep these markdown files as the project bible. Copy or move them into the new repository under `/docs` so product and documentation live together.

## Why this matters

| Risk if you build here | What goes wrong |
| --- | --- |
| Profile README collision | Product docs overwrite or confuse the public GitHub profile |
| Wrong default visibility / purpose | A profile repo is not set up as a production engineering repo |
| Messy history | Company, legal, and app history get mixed with profile commits |
| Access control | Future staff or contractors should not need access to a personal profile repo |
| CI and environments | Production deploy keys and GitHub Environments do not belong on a profile repo |

## What to create

Create one private GitHub repository:

```text
livehelm
```

If the working name changes, rename the repo when the product name is final.

Recommended settings:

- Private
- Default branch `main`
- Branch protection on `main`
- Required pull requests
- Required status checks once CI exists
- GitHub Environments: `staging` and `production`
- CODEOWNERS for `/docs`, `/supabase`, and `/src`

Optional later:

- `livehelm-status` public status page repo
- `livehelm-legal` only if counsel wants contracts in a separate store. Prefer keeping legal templates in the product repo until that becomes awkward.

## Workspace layout for the product repo

```text
livehelm/
  docs/                  # this bible, copied across
  apps/
    web/                 # Next.js control-room web app
  packages/
    db/                  # Drizzle schema, migrations
    shared/              # types, permission maps, zod schemas
    config/              # eslint, tsconfig, tailwind presets
  supabase/              # local config, policies, seed
  scripts/
  .github/workflows/
```

Start simpler if you are alone: a single Next.js app at the repo root is acceptable until a second app exists. The day you add a mobile client or a worker, split into `apps/web`.

The playbooks assume this path:

1. Single Next.js app at repo root while the foundation is built.
2. Extract `packages/db` and `packages/shared` as soon as a second surface appears.
3. Do not start a monorepo tool debate. If you need one, use `pnpm` workspaces. No extra tool is required on day one.

## What stays in the profile repo

After the product repo exists:

1. Leave a short pointer in the profile README if you want.
2. Stop adding product files here.
3. Treat this repo as personal profile content again.

## Immediate action

- [ ] Create private GitHub repo `livehelm`
- [ ] Copy `/docs` into that repo
- [ ] Add a product `README.md` that links to `docs/README.md`
- [ ] Invite nobody until org/user access rules are written
- [ ] Turn on branch protection before the first production deploy
