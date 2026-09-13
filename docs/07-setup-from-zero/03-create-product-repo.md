# Create the product repo

1. In the GitHub organisation, click New repository.
2. Name: `livehelm`.
3. Private.
4. Add a README and an MIT or more likely a **proprietary** licence. This is a commercial SaaS. Use a private All Rights Reserved licence unless you intend to open source. **Recommendation: proprietary. Do not MIT the product.**
5. Do not make the repo public “for the portfolio” while it contains customer-shaped seed data.

## Protect main

- Require pull request
- Require 1 approval when a second person exists
- Require status checks: `lint`, `typecheck`, `unit`, `rls` once they exist
- No force push
- No deletions

## Environments

Create GitHub Environments `staging` and `production` with required reviewers on production.

## Copy the bible

See [12-copy-docs-into-product-repo.md](12-copy-docs-into-product-repo.md).

## First commit on the product repo

A README that points to `/docs` and says how to run locally. No secrets.
