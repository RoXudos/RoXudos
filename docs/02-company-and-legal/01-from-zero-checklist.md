# From-zero checklist

You asked for a recommendation on company, domain, email, and analytics accounts. The recommendation is: **do the full list**. There is no existing company stack, the product will hold staff, medical, and safeguarding data, and the first market is UK + EU + US.

Tick in order. Legal work can overlap with foundation coding, but **do not put real personal data on production until rows 1–20 are done**.

## Company

- [ ] Choose a legal name (can differ from Livehelm)
- [ ] Check Companies House, trade mark, and domain together
- [ ] Incorporate a UK limited company
- [ ] Appoint directors and record PSCs
- [ ] Open a business bank account
- [ ] Register for Corporation Tax
- [ ] Register for VAT when required
- [ ] Set up accounting (Xero or FreeAgent)
- [ ] Issue founder shares / cap table note
- [ ] Get a registered office that can receive mail

## Identity

- [ ] Buy the product domain and obvious typos
- [ ] Google Workspace or Microsoft 365 on that domain
- [ ] Founder email, `ops@`, `privacy@`, `security@`, `support@`
- [ ] Password manager (1Password or Bitwarden business)
- [ ] Hardware keys or app MFA on every admin account

## Brand (minimum)

- [ ] Wordmark is enough for FPR
- [ ] Do not delay engineering for a full brand programme

## Privacy and legal

- [ ] ICO registration (UK)
- [ ] Record of processing activities (ROPA)
- [ ] Lawful bases per data type
- [ ] Retention schedule
- [ ] Privacy policy
- [ ] Cookie / analytics policy (keep analytics minimal)
- [ ] Customer terms of service
- [ ] Data processing agreement for customers
- [ ] Subprocessor list
- [ ] Acceptable use policy
- [ ] Incident / breach response plan
- [ ] DPIA drafted before medical or safeguarding go live
- [ ] Counsel review before the first paying customer (recommended)

## EU and US

- [ ] Decide EU representative if required
- [ ] Decide US state privacy approach (see US file)
- [ ] Standard contractual clauses / UK IDTA where needed
- [ ] Do not advertise HIPAA compliance. This is not a US medical-record product.

## Insurance

- [ ] Professional indemnity
- [ ] Public / product liability as advised
- [ ] Cyber insurance once a broker understands the data types

## Product accounts (create in this order)

See [../07-setup-from-zero/01-accounts-to-create.md](../07-setup-from-zero/01-accounts-to-create.md).

Minimum:

- [ ] GitHub organisation (recommended) or a dedicated private repo under a company account
- [ ] Vercel
- [ ] Supabase
- [ ] Cloudflare
- [ ] Domain DNS
- [ ] Resend or Postmark
- [ ] Sentry (EU)
- [ ] Better Stack or Checkly for uptime
- [ ] Open-Meteo (no key) or a paid weather API
- [ ] Map tile account if you leave OSM/MapLibre default tiles

## Analytics recommendation

**Do not install a US ad-tech pixel.**

For FPR:

- Product analytics: none, or a self-hosted / EU option later (PostHog EU)
- Error tracking: Sentry EU
- Uptime: Better Stack
- Marketing site analytics can wait until there is a marketing site

## What can wait

- US subsidiary
- EU company
- SOC 2
- ISO 27001
- Trade mark in every class worldwide
- Office lease
