# Source: https://www.llea.ai/blog/privacy-security-compliance

[All posts](https://www.llea.ai/blog)

Privacy is one of those topics that vendors tend to bury behind a "trust centre" page, three logos, and zero substance. This post is the substance. If you're evaluating llea.ai for a Shopify store — yours or a client's — these are the facts your DPO or compliance officer is going to want, written in plain language.

For the full legal text, see our [Privacy Policy](https://www.llea.ai/privacy) and [Data Processing Agreement](https://www.llea.ai/dpa).

## Who owns what (the controller / processor split)

Under GDPR, the merchant is the **controller** of shopper data and llea.ai is the **processor**. In plain English: you decide what to do with your customer data, we just do it for you. We never use shopper data for our own purposes, and we never share it with another merchant.

- **Merchant data** (your store, your staff, your billing): we're a controller for billing/account admin and a processor for app-feature data.
- **Shopper data** (your customers): you're the controller, we're the processor. We act only on your documented instructions, governed by our DPA.

## Where your data lives

llea.ai runs on a small, deliberately chosen set of sub-processors. Every one of them has a signed DPA in place and a recognised certification. The full list is canonical in the Privacy Policy and updated there before any change rolls out.

Where your data livesEvery sub-processor, what they do, and the certifications they hold.VENDORPURPOSEREGIONCERTIFICATIONSSupabaseDatabase, auth, storageUSSOC 2 Type IIVercelFrontend hostingUS/EdgeSOC 2, ISO 27001LovableBuild + preview platformUSSOC 2, GDPRGoogle Vertex AILLM inference (no training)US/EUSOC 2, ISO 27001, DPFPostHog CloudProduct analyticsEU/USSOC 2, ISO 27001, GDPRShopifyApp platform, billingGlobalSOC 2/3, PCI DSS L1ResendTransactional emailUSSOC 2 Type IICrispMarketing-site chat (no app data)EUGDPR (EU-hosted)

The full sub-processor list. Every vendor is named in the Privacy Policy with a signed DPA. We give 30 days' notice before any change.

- We do not pool data across customers. Your shoppers' intent profiles never leave your store's tenant boundary.
- We do not sell, rent, or share shopper data with any third party — including ad networks.
- EU/UK shoppers: data transfers rely on EU SCCs (Module 2 + Module 3), the UK IDTA, and the Swiss addendum where applicable.
- US-based sub-processors that are DPF-certified rely on the EU–US Data Privacy Framework as the primary mechanism, SCCs as fallback.

## GDPR, CCPA, and India's DPDPA

We're built for compliance across the three regimes that matter most to Shopify merchants:

| Regime | How we comply |
| --- | --- |
| GDPR (EU/EEA) | Controller/processor DPA, SCCs for international transfers, 72-hour breach notification, Art. 28 sub-processor authorisation, data subject rights routed via Shopify GDPR webhooks. |
| UK GDPR | UK IDTA addendum to SCCs; UK supervisory authority recognised. |
| CCPA / CPRA (California) | Notice-at-collection, no sale or sharing of personal information, no use for cross-context behavioural advertising, opt-out and limit-use mechanisms honoured. |
| DPDPA (India) | Aligned with the Digital Personal Data Protection Act, 2023 — consent-based processing, data principal rights honoured via the same Shopify webhook path. |
| Swiss FADP | Swiss addendum to SCCs for transfers out of Switzerland. |

## Shopify's data policies

llea.ai is built around Shopify's mandatory GDPR webhooks. We HMAC-verify every webhook with your per-shop client secret and act on all three:

- **`customers/data_request`**: within 30 days the merchant receives the shopper data we hold for the requested customer.
- **`customers/redact`**: on receipt, the shopper's records are deleted from our database and any downstream caches.
- **`shop/redact`**: 48 hours after uninstall, the merchant's full data is deleted from our database. Activity is logged in the `compliance_requests` audit table.

## Cookies and anonymous visitors

llea.ai's web pixel sets pseudonymous visitor IDs in cookies / local storage to track behaviour across sessions for anonymous shoppers. The rules:

- Cookies are strictly first-party. We don't set tracking cookies under any third-party domain.
- We respect Do Not Track headers and Global Privacy Control (GPC) signals.
- No browser fingerprinting. Cookies are the only persistent identifier.
- On the marketing site we set strictly-necessary, analytics, functional, and support cookies — gated through a consent banner with Google Consent Mode v2 in EU/UK.
- On the storefront pixel inside Shopify admin, only strictly-necessary cookies are set.

## How shoppers opt out

Shoppers exercise rights through the merchant — they're the controller. The flow:

- First contact: the merchant whose store they shopped on. The merchant submits a Shopify GDPR webhook that reaches us automatically.
- If they can't reach the merchant, they email admin@llea.ai and we route the request to the merchant and process the relevant webhook.
- Browser-level: GPC signals are honoured automatically.

## AI and the training question

The single biggest privacy question for AI-enabled SaaS is: _"do you train models on my data?"_ Our answer is no, with specifics:

- **Per-store models, never pooled.** Each merchant's intent model is trained only on their own data. We do not train a shared "llea.ai model" across customers.
- **Foundation models are off-limits.** Our LLM provider (Google Cloud Vertex AI / Gemini) is contractually barred from training its foundation models on customer prompts or responses, per Google Cloud's Generative AI terms.
- **No automated decisions with legal effect.** Our outputs assist the merchant, the merchant decides what to send. Compliant with GDPR Art. 22.
- **EU AI Act transparency.** Where required, our Privacy Policy serves as the transparency disclosure for limited-risk AI use.

## What happens when you uninstall

What happens to your data when you uninstallAutomatic, audited, and complete. No support ticket needed.Hour 0Uninstall

You click "Remove app" in Shopify

Hour 4848-hour purge

Store-level deletion completes

Day 3030-day backups

Encrypted backups rotate out

DoneFully gone

No trace remains anywhere

Driven by Shopify's app/uninstalled + shop/redact webhooks. No human in the loop.

The standard Shopify uninstall flow drives the deletion. No support ticket, no email exchange — the webhook handler does the work.

- **Hour 0:** you click "Remove app" in Shopify admin. The `app/uninstalled` webhook fires immediately.
- **Hour 0–48:** we begin store-level data deletion. A re-install in this window restores your data (handy if uninstall was accidental).
- **Hour 48:** the `shop/redact` webhook from Shopify confirms final purge. Your store-level data is gone from the live database.
- **Day 30:** the last encrypted backup containing any trace of your data rotates out. We hold backups for security/disaster recovery — they expire automatically.

The audit record of "we deleted this on this date" is kept in our `compliance_requests` table for 2 years — no shopper PII, just the proof of deletion. This is what your DPO will ask for if there's ever a question.

## Security in practice

The headline items, lifted directly from our DPA Annex II:

- TLS 1.2+ in transit on every endpoint; AES-256 at rest on the Supabase database
- Row-Level Security on every multi-tenant table — per-shop credentials never shared
- HMAC SHA-256 verification on every Shopify webhook against the per-shop client secret
- Per-shop Shopify OAuth credentials, never re-used across stores
- Least-privilege staff access, MFA enforced on all staff accounts, audit logging
- Encrypted, automatically expiring backups (30 days)
- Content sanitisation via DOMPurify for any HTML rendered in the app
- 72-hour breach notification to controllers per GDPR Art. 33

## The summary your DPO wants

- GDPR + UK GDPR + CCPA + DPDPA + Swiss FADP compliant
- Signed DPA, SCCs (Modules 2 & 3), UK IDTA, Swiss addendum in place
- No model training on customer data, contractually enforced with our LLM provider
- No sale, no sharing, no cross-context behavioural advertising
- Sub-processor list canonical in the Privacy Policy with 30-day change notice
- 48-hour deletion on uninstall, driven by Shopify's own GDPR webhooks

If you need a signed counterpart of the DPA for your records, email [admin@llea.ai](mailto:admin@llea.ai). If you have specific compliance questions before installing, [book a 30-minute call](https://calendly.com/riyaz-llea/30min) and we'll walk through them.