# First deployable app

Before any product feature, ship:

1. `/api/health` returns `{ ok: true, db: true }`
2. A sign-in page that talks to Supabase Auth
3. A signed-in placeholder: “Livehelm — no events yet”
4. Staging URL works
5. Production URL works
6. Sentry receives a test error and you delete it
7. Uptime is green

This is **slice 0**. Do not skip it to jump to the map.

## Definition of done for slice 0

- [ ] Local `pnpm dev` works
- [ ] Staging deployed from `main`
- [ ] Health check green
- [ ] You can invite yourself and sign in
- [ ] You cannot sign in with a random email
- [ ] No demo incidents in production
