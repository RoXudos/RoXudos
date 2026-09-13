# Domain, email, and identity

## Domain

Buy:

- the product name `.com` if available
- the product name `.co.uk`
- obvious hyphen / typo domains if cheap

Point DNS through **Cloudflare** so R2, email routing, and later WAF sit in one place.

Do not use a free email domain as the from-address for operational or legal mail.

## Email

Use Google Workspace or Microsoft 365.

Create at least:

| Address | Use |
| --- | --- |
| founder personal | daily |
| `privacy@` | data subject requests |
| `security@` | vulnerability reports |
| `support@` | customers |
| `ops@` | internal operations |
| `legal@` | contracts |

Turn on MFA on the Google / Microsoft tenant before you add payment cards to anything else.

## Password manager

Every vendor account goes in a shared vault with least privilege. No shared “password123” spreadsheet.

## GitHub

Prefer a **GitHub Organisation** owned by the company, not a personal account, before contractors arrive.

## Social handles

Reserve the working name on LinkedIn and whatever you will actually use. Do not build a content operation before the control room exists.

## Certificates and DKIM

When transactional email is configured (Resend or Postmark):

- SPF
- DKIM
- DMARC (`p=quarantine` once mail is stable)
