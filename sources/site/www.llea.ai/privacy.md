# Source: https://www.llea.ai/privacy

# Privacy Policy

- **Effective date:** 26 May 2026
- **Last updated:** 26 May 2026
- **Entity:** LLEA DATA SCIENCE PRIVATE LIMITED ("llea.ai", "we", "us", "our")
- **Contact:** [admin@llea.ai](mailto:admin@llea.ai)
- **Data Protection Officer / Privacy contact:** Muhammad Riyaz, [riyaz@llea.ai](mailto:riyaz@llea.ai)

This Privacy Policy explains how we collect, use, share, and protect personal information across two distinct contexts:

- **Part A: Website visitors** at [https://www.llea.ai](https://www.llea.ai)
- **Part B: The llea.ai Shopify App** installed by merchants and used by their shoppers

A separate **CCPA / CPRA Addendum** for California residents and a **Cookies & Consent** section follow at the end.

If you are a **shopper** on a Shopify store that uses llea.ai, please first read **Part B → Shoppers** and contact the merchant whose store you shopped on. llea.ai processes your data on the merchant's behalf.

## Part A: Website visitors (llea.ai)

This part applies when you visit [https://www.llea.ai](https://www.llea.ai), read our blog, request a demo, or contact us.

### 1\. Information we collect

- **Information you provide:** name, work email, company, role, message contents (demo requests, support, sales chat).
- **Automatically collected:** IP address (truncated where possible), browser, device, OS, referrer, pages visited, timestamps, UTM parameters.
- **Cookies & similar technologies:** see the **Cookies & Consent** section below.

### 2\. Why we use it (lawful basis under GDPR)

| Purpose | Lawful basis |
| --- | --- |
| Respond to your enquiries, schedule demos | Contract / pre-contract steps (Art. 6(1)(b)) |
| Send product updates, marketing emails | Consent (Art. 6(1)(a)); withdrawable any time |
| Measure site performance, fix bugs, prevent fraud | Legitimate interests (Art. 6(1)(f)) |
| Comply with legal obligations | Legal obligation (Art. 6(1)(c)) |

### 3\. Retention

- Demo / sales enquiries: up to **24 months** after last contact, then deleted or anonymised.
- Marketing list: until you unsubscribe, then suppressed (email-only, kept to honour opt-out).
- Server logs: **30 days**.
- Support chat transcripts: **12 months**.

### 4\. Your rights (visitors)

See **Section 9: Your rights** below. Visitor requests go to [admin@llea.ai](mailto:admin@llea.ai).

## Part B: The llea.ai Shopify App

This part applies when a Shopify merchant installs llea.ai, and when shoppers on that merchant's storefront interact with the app's analytics, engagement, or clearance features.

### 5\. Our role

- **Merchant data (about the merchant's business and staff):** we act as a **controller** for billing and account administration, and as a **processor** for app-feature data.
- **Shopper data (the merchant's customers):** the merchant is the **controller**, llea.ai is the **processor**. We process this data only on the merchant's documented instructions, under our Data Processing Agreement (see [/dpa](https://www.llea.ai/dpa)).

### 6\. Categories of data processed

#### 6.1 Merchant store & staff data

- Shop domain, shop name, shop owner name and email, plan, currency, timezone, locale
- Merchant staff identity (Shopify user id, email) for app login
- Billing records (Shopify subscription id, plan, status, invoices)

#### 6.2 Shopper data (via Shopify Admin API and our Web Pixel / theme extension)

- Customer identifiers: Shopify customer id, email, name, phone (when provided by the merchant's store)
- Order and transaction data: order ids, line items, totals, currency, status, timestamps
- Behavioural / event data: product views, add-to-cart, checkout-started, purchase events
- Coarse location (country / region) and device/browser metadata
- Pseudonymous visitor ids (cookies / local storage) for shoppers who are not signed in

#### 6.3 Compliance & audit data

- Records of Shopify GDPR webhooks received (`customers/data_request`, `customers/redact`, `shop/redact`), stored in `compliance_requests` for our and the merchant's audit trail

We do **not** intentionally collect special-category data (health, biometric, political, religious, etc.). We do **not** collect government IDs, full payment card numbers, or banking credentials; payments are handled by Shopify Billing.

### 7\. How we use the data

- Provide the app's features: customer segmentation, smart engagement (recovery / re-engagement messaging via merchant-owned channels), smart clearance, analytics dashboards.
- Train and run the merchant's per-store models. We do **not** train shared or foundation models on merchant or shopper data.
- Send messages to shoppers **only through the merchant's own conversion channels** (e.g. their email / SMS provider via Shopify Flow). llea.ai does not contact shoppers directly.
- Operate billing, support, and security monitoring.

### 8\. Sub-processors

We rely on the following sub-processors. This list (in this Privacy Policy) is the canonical, versioned source. We update it here before adding or replacing any sub-processor.

| Sub-processor | Purpose | Location | Certifications |
| --- | --- | --- | --- |
| Supabase | Database, auth, edge functions, storage | US | SOC 2 Type II, HIPAA |
| Vercel | Hosting (marketing site + app frontend) | US / global edge | SOC 2 Type II, ISO 27001, GDPR, DPF |
| Lovable (Lovable Labs, Inc.) | Application development, build, preview hosting, and publishing platform | US / global edge | SOC 2 Type II, ISO 27001, GDPR |
| Google Cloud: Vertex AI (Gemini) | LLM inference for copy generation and ranking (no training on our data) | US / EU (regional endpoint) | SOC 2 Type II, ISO 27001/27017/27018, HIPAA, GDPR, DPF |
| PostHog Cloud | Product analytics (cloud, EU or US region) | EU / US | SOC 2 Type II, ISO 27001, HIPAA, GDPR (per posthog.com) |
| Shopify | App platform, billing, webhooks | Global | SOC 2 / 3, PCI DSS Level 1 |
| Resend | Transactional email | US | SOC 2 Type II |
| Crisp | Marketing-site support chat | EU | GDPR (EU-hosted) |

We will give merchants at least **30 days' notice** before adding or replacing a sub-processor in a way that materially affects shopper data, and merchants may object per the DPA.

### 9\. Retention (app)

| Data | Retention |
| --- | --- |
| Merchant store & staff data while subscribed | Duration of the subscription |
| After uninstall: store-level deletion | Initiated **immediately**, full deletion within **48 hours** unless the app is reinstalled in that window (see `shopify-uninstall` + `shop/redact` flow) |
| Shopper records on customers/redact | Deleted across all related tables on receipt of the Shopify webhook |
| 90-day purchase-exclusion window | Order-derived flags retained for up to **90 days** to suppress redundant engagement; then expired |
| compliance\_requests audit log | **2 years** for our records (no shopper PII beyond what Shopify already requires) |
| Backups | Encrypted, rotated, automatically expire within **30 days** |

### 10\. Shopify GDPR webhooks (how rights are honoured at the platform level)

We implement and HMAC-verify all three mandatory Shopify webhooks:

- `customers/data_request`: within **30 days** the merchant receives the data we hold for the requested shopper.
- `customers/redact`: on receipt, the shopper's records are deleted from our database and downstream caches.
- `shop/redact`: 48 hours after uninstall, the merchant's data is deleted from our database; activity is logged in `compliance_requests`.

### 11\. AI and automated processing disclosure

- We use Google Cloud Vertex AI (Gemini 2.0 Flash) to generate copy suggestions, summarise behaviour, and rank product recommendations. Google does not use Vertex AI customer prompts or responses to train its foundation models (per Google Cloud's Generative AI terms).
- These models **do not make decisions that produce legal or similarly significant effects on individuals** (GDPR Art. 22). Outputs assist the merchant; the merchant decides what to send and to whom.
- We do **not** authorise our sub-processors to train their foundation models on merchant or shopper data.
- Where required by the EU AI Act, this notice serves as our transparency disclosure for limited-risk AI use.

### 12\. How shoppers exercise rights

- **First:** contact the merchant whose store you shopped on, as they are the controller of your data and can submit a Shopify GDPR request that reaches us automatically.
- **If you cannot reach the merchant**, contact [admin@llea.ai](mailto:admin@llea.ai). We will route the request to the merchant and process the relevant Shopify webhook.

### 13\. International data transfers

Data may be transferred to and processed in the United States and other jurisdictions outside the EEA / UK / Switzerland.

We rely on:

- **EU Standard Contractual Clauses (SCCs)**: Module 2 (Controller → Processor) and Module 3 (Processor → Processor) as applicable, plus the UK International Data Transfer Addendum and the Swiss addendum
- The **EU-US Data Privacy Framework** where the receiving sub-processor is certified
- Supplementary technical and organisational measures (encryption in transit and at rest, access controls, RLS, HMAC verification of webhooks)

We do **not** rely on bare "you consent to the transfer" language.

### 14\. Data Processing Agreement (DPA)

Our DPA is published at [https://www.llea.ai/dpa](https://www.llea.ai/dpa) and is incorporated by reference into the merchant's subscription on installation. A signed copy is available on request at [admin@llea.ai](mailto:admin@llea.ai).

## 9\. Your rights (all users)

Subject to applicable law, you may:

- Access the personal data we hold about you
- Request correction or deletion
- Restrict or object to certain processing
- Withdraw consent at any time (without affecting prior processing)
- Receive your data in a portable, machine-readable format
- Lodge a complaint with your local supervisory authority (EU/UK: your national DPA)

**Response SLA:** 30 days (extendable by a further 60 days for complex requests, with notice).

## CCPA / CPRA Addendum (California residents)

This addendum supplements Parts A and B for California residents and is offered in compliance with the **California Consumer Privacy Act** as amended by the **California Privacy Rights Act**.

### Notice at collection

We collect the following categories in the preceding 12 months:

| CCPA category | Examples | Source | Purpose |
| --- | --- | --- | --- |
| Identifiers | name, email, IP, Shopify customer id | You; merchant; Shopify | Service, security |
| Customer records | order history, contact details | Merchant; Shopify | Service |
| Commercial information | products viewed, purchased | Shopper behaviour; Shopify | Service |
| Internet activity | page views, events | Cookies; pixel | Analytics, service |
| Geolocation (coarse) | country / region | IP | Localisation |
| Inferences | segment, intent score | Derived | Service |

We do **not** collect sensitive personal information (SPI) as defined by the CPRA, and we do not use any data for cross-context behavioural advertising.

### Your California rights

- Right to **know** what we collect, use, disclose
- Right to **delete**
- Right to **correct**
- Right to **opt out of sale or sharing** of personal information
- Right to **limit use of sensitive personal information** (n/a; we do not collect SPI)
- Right to **non-discrimination** for exercising your rights

### "Do Not Sell or Share My Personal Information"

We do **not sell** personal information, and we do **not share** it for cross-context behavioural advertising as defined by the CPRA. If this ever changes, we will publish an opt-out link here and honour Global Privacy Control (GPC) browser signals.

### Authorized agents

You may use an authorised agent to submit a request. We will require written proof of authorisation and may verify your identity directly.

### Submitting a request

Email [admin@llea.ai](mailto:admin@llea.ai) with the subject line "California Privacy Request". We respond within 45 days.

## Cookies & Consent

We use cookies and similar technologies on our marketing site:

| Category | Examples | Purpose |
| --- | --- | --- |
| Strictly necessary | session, CSRF | Site operation |
| Analytics | Google Analytics, PostHog | Aggregate usage |
| Functional | language, theme | Preferences |
| Support | Crisp | Live chat |

In the EU / UK we obtain prior, granular consent via our cookie banner and pass the result to Google via **Consent Mode v2**. You can change your choice at any time through the "Cookie preferences" link in our footer.

The llea.ai app inside Shopify admin sets only strictly necessary cookies / session tokens required for authenticated app sessions.

## Security

- TLS in transit; AES-256 at rest (managed by Supabase)
- Row-Level Security on all multi-tenant tables; role-based access for staff
- HMAC SHA-256 verification on every Shopify webhook against the per-shop client secret
- Per-shop OAuth credentials, never shared across stores
- Least-privilege staff access, audit logs, MFA enforced
- Encrypted, automatically expiring backups

No system is perfectly secure. If you believe you have found a vulnerability, please email [admin@llea.ai](mailto:security@llea.ai).

## Children

The app and website are **not directed to children under 16**. We do not knowingly collect personal information from children. If you believe a child has provided us with personal information, contact [admin@llea.ai](mailto:admin@llea.ai) and we will delete it.

## Changes to this policy

We will post material changes here with a new effective date, and where required give merchants advance notice via in-app notification or email.

## Contact

LLEA DATA SCIENCE PRIVATE LIMITED

WeWork Raheja Woods, Kalyani Nagar, Yerwada, Pune - 411006, Maharashtra, India

Email: [admin@llea.ai](mailto:admin@llea.ai)

DPO / Privacy contact: Muhammad Riyaz, [riyaz@llea.ai](mailto:riyaz@llea.ai)