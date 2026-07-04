# Source: https://www.llea.ai/dpa

# Data Processing Agreement (DPA)

- **Effective date:** 26 May 2026
- **Version:** 1.0

This Data Processing Agreement ("DPA") forms part of the agreement between:

- **LLEA DATA SCIENCE PRIVATE LIMITED**, \[registered address\] ("**llea.ai**", "Processor")

and

- **The Shopify merchant** identified by the shop domain on which the llea.ai app is installed ("**Merchant**", "Controller")

(each a "Party", together the "Parties").

By installing or continuing to use the llea.ai Shopify app, the Merchant accepts this DPA. A signed counterpart is available on request at [admin@llea.ai](mailto:admin@llea.ai).

## 1\. Definitions

Terms not defined here have the meaning given in the EU General Data Protection Regulation 2016/679 ("**GDPR**") and, where applicable, the UK GDPR, the Swiss FADP, and the California Consumer Privacy Act as amended by the CPRA ("**CCPA**").

- **Personal Data**: as defined in Art. 4(1) GDPR.
- **Processing**: as defined in Art. 4(2) GDPR.
- **Data Subject**: shoppers of the Merchant, Merchant staff, and other natural persons whose Personal Data is processed under the Principal Agreement.
- **Sub-processor**: any third party engaged by llea.ai to process Personal Data on behalf of the Merchant.
- **Principal Agreement**: the Merchant's subscription to the llea.ai Shopify app and llea.ai's Terms of Service.

## 2\. Subject matter, duration, nature & purpose

- **Subject matter:** processing of Personal Data necessary to provide the llea.ai app (customer segmentation, smart engagement, smart clearance, analytics).
- **Duration:** the term of the Principal Agreement, plus the retention periods in Annex II.
- **Nature & purpose:** automated processing for the features described above.
- **Categories of Data Subjects and Personal Data:** see Annex I.

## 3\. Roles

- The **Merchant is the Controller** of shopper Personal Data and Merchant-staff Personal Data.
- **llea.ai is the Processor**, acting solely on the Merchant's documented instructions, which are set out in the Principal Agreement, this DPA, and the in-app configuration the Merchant chooses.

## 4\. Processor obligations (Art. 28 GDPR)

llea.ai will:

1. Process Personal Data only on documented Merchant instructions, including with regard to international transfers, unless required by law (in which case llea.ai will inform the Merchant unless prohibited).
2. Ensure that persons authorised to process Personal Data are bound by confidentiality.
3. Implement the **technical and organisational measures** in Annex II.
4. Engage Sub-processors only under Section 5.
5. Assist the Merchant, by appropriate technical and organisational measures, in responding to Data Subject requests (Chapter III GDPR).
6. Assist the Merchant in ensuring compliance with Arts. 32–36 GDPR (security, breach notification, DPIAs, prior consultation).
7. At the Merchant's choice, delete or return all Personal Data after the end of the provision of services; see Section 10.
8. Make available all information necessary to demonstrate compliance with Art. 28, and allow audits under Section 9.

## 5\. Sub-processors

**5.1** The Merchant grants llea.ai a **general authorisation** to engage the Sub-processors listed in **Annex III** (also kept current in the llea.ai Privacy Policy).

**5.2** llea.ai will give the Merchant at least **30 days' prior notice** of any addition or replacement of a Sub-processor that materially affects shopper Personal Data, via email and/or in-app notice and update of the public list.

**5.3** The Merchant may **object** to a new Sub-processor within 14 days of notice on reasonable data-protection grounds. If the Parties cannot resolve the objection in good faith, the Merchant may terminate the Principal Agreement without penalty for the affected portion.

**5.4** llea.ai will impose on each Sub-processor data-protection obligations no less protective than those in this DPA, by written contract.

## 6\. International transfers

**6.1** Where Personal Data is transferred outside the EEA, UK, or Switzerland to a country not subject to an adequacy decision, the Parties agree that:

- The **EU Standard Contractual Clauses (Module 2: Controller → Processor)** issued by Commission Implementing Decision (EU) 2021/914 are hereby incorporated by reference, with the Merchant as data exporter and llea.ai as data importer.
- For onward transfers to Sub-processors, **Module 3 (Processor → Processor)** applies.
- The **UK International Data Transfer Addendum** (issued by the ICO) and the **Swiss addendum** apply where the data exporter is in the UK or Switzerland respectively.
- The optional docking clause (Cl. 7) is included. The Parties select **Option 2** of Cl. 9 (general authorisation, 30 days' notice). The governing law and forum for the SCCs are as specified in the Principal Agreement, or, where required by the SCCs, the law and courts of an EU Member State.
- Annex I, II, III of the SCCs are completed by the corresponding Annexes of this DPA.

**6.2** Where a Sub-processor is certified under the **EU-US Data Privacy Framework**, transfers may rely on that framework as the primary mechanism, with the SCCs as fallback.

## 7\. Security

llea.ai will implement and maintain the technical and organisational measures set out in **Annex II**. These include encryption in transit and at rest, Row-Level Security on multi-tenant tables, HMAC verification of Shopify webhooks, role-based access, MFA, and audit logging.

## 8\. Personal data breach

llea.ai will notify the Merchant **without undue delay and in any event within 72 hours** of becoming aware of a Personal Data breach affecting the Merchant's data, providing the information required by Art. 33(3) GDPR to the extent then known.

## 9\. Audits

**9.1** llea.ai will make available to the Merchant, on request, the information necessary to demonstrate compliance with Art. 28 GDPR, including third-party certifications and reports held by its Sub-processors (e.g. Supabase SOC 2 Type II).

**9.2** The Merchant may conduct an audit (or mandate a qualified independent auditor bound by confidentiality) **once per 12-month period**, on at least 30 days' written notice, during business hours, without disrupting llea.ai's operations. The Merchant bears the audit cost unless the audit reveals a material breach by llea.ai.

## 10\. Return or deletion on termination

**10.1** On termination of the Principal Agreement or on Merchant request, llea.ai will, at the Merchant's choice, return or delete all Personal Data within **48 hours**, except where retention is required by law.

**10.2** The 48-hour deletion is initiated automatically on Shopify `app/uninstalled`, with a final purge driven by the Shopify `shop/redact` webhook. A re-installation within the 48-hour window restores the Merchant's data.

**10.3** Encrypted backups are rotated and expire automatically within **30 days**.

## 11\. Liability and indemnity

Liability under this DPA is governed by the limitation-of-liability clauses of the Principal Agreement. Nothing in this DPA limits either Party's liability to Data Subjects under Art. 82 GDPR.

## 12\. Order of precedence

In case of conflict: SCCs (when applicable) → this DPA → Principal Agreement → marketing materials.

## 13\. Governing law

This DPA is governed by the law and exclusive jurisdiction specified in the Principal Agreement, except where mandatory data-protection law requires otherwise.

## Annex I: Description of processing

### A. List of Parties

- **Data exporter (Controller):** The Merchant (shop domain, contact email and address available on the Merchant's Shopify account).
- **Data importer (Processor):** LLEA DATA SCIENCE PRIVATE LIMITED, \[address\], [admin@llea.ai](mailto:admin@llea.ai).

### B. Description of transfer

| Item | Detail |
| --- | --- |
| Categories of Data Subjects | Shoppers of the Merchant; Merchant staff with app access |
| Categories of Personal Data | Identifiers (name, email, phone, Shopify customer id), order & transaction data, behavioural events (views, add-to-cart, checkout, purchase), coarse geolocation, device/browser metadata, pseudonymous visitor ids, Merchant-staff Shopify user id and email |
| Sensitive data | None intentionally collected |
| Frequency of transfer | Continuous |
| Nature of processing | Storage, structuring, segmentation, scoring, generation of recommendations, sending of merchant-authorised messages via merchant-owned conversion channels |
| Purpose | Provide the llea.ai Shopify app features |
| Retention | See Annex II |
| Sub-processor transfers | See Annex III |

### C. Competent supervisory authority

The supervisory authority of the EU Member State / UK nation / Swiss canton in which the Merchant is established, or, where the Merchant is outside the EEA/UK/Switzerland, the supervisory authority designated by the EU representative.

## Annex II: Technical and organisational measures (Art. 32 GDPR)

| Measure | Implementation |
| --- | --- |
| Encryption in transit | TLS 1.2+ enforced on all endpoints |
| Encryption at rest | AES-256 on managed Supabase database and storage |
| Access control | Role-based; least privilege; MFA on all staff accounts; SSO where supported |
| Tenant isolation | Row-Level Security policies on every multi-tenant table; per-shop credentials never shared |
| Authentication of integrations | Per-shop Shopify OAuth credentials; HMAC SHA-256 verification on every Shopify webhook against per-shop client secret |
| Session security | Shopify session tokens (App Bridge v4) for the embedded app |
| Logging & monitoring | Application + edge-function logs; audit trail for compliance events in `compliance_requests` |
| Backups | Encrypted, rotated, automatically expire within 30 days |
| Vulnerability management | Dependency scanning, regular updates, security review of new sub-processors |
| Incident response | Documented runbook; 72-hour breach notification to controllers (see Section 8) |
| Data minimisation | Shopper PII transmitted only to the Merchant's own conversion channels (e.g. via Shopify Flow); never to unrelated third parties |
| Content sanitisation | HTML content rendered via DOMPurify whitelist |
| Retention enforcement | Automated deletion on `customers/redact` and `shop/redact`; 48-hour SLA after uninstall |
| Staff training | Privacy and security training; confidentiality obligations in employment contracts |
| Physical security | Inherited from Sub-processors (Supabase / AWS / Vercel / Lovable) under their respective certifications |
| Sub-processor due diligence | DPA + SCCs in place with every Sub-processor processing Personal Data |

## Annex III: Approved Sub-processors

| Sub-processor | Purpose | Location | Transfer mechanism |
| --- | --- | --- | --- |
| Supabase, Inc. | Database, auth, edge functions, storage | US (SOC 2 Type II) | SCCs |
| Vercel, Inc. | Hosting (marketing site + app frontend) | US / global edge | SCCs / DPF |
| Lovable Labs, Inc. | Application development, build, preview hosting, and publishing platform | US | SCCs (per Lovable DPA dated 17 Nov 2025) |
| Google LLC: Google Cloud / Vertex AI (Gemini) | LLM inference for copy generation and ranking (no training on customer data) | US / EU (regional endpoint) | SCCs / DPF |
| PostHog, Inc. (PostHog Cloud) | Product analytics in EU or US region | EU / US | SCCs |
| Shopify Inc. | App platform, billing, webhooks | Global | Shopify DPA |
| Resend, Inc. | Transactional email | US | SCCs |
| Crisp IM SAS | Marketing-site support chat (no app data) | EU | N/A (intra-EU) |

PostHog Cloud holds SOC 2 Type II, ISO 27001, HIPAA, and GDPR attestations (see posthog.com trust/security). The current sub-processor list is maintained in the llea.ai [Privacy Policy](https://www.llea.ai/privacy). Changes follow the notice procedure in Section 5.

## Signatures

Signed for and on behalf of LLEA DATA SCIENCE PRIVATE LIMITED

Name:

Title:

Date:

Signed for and on behalf of Merchant

(electronic acceptance via app install constitutes signature)

Shop domain:

Date: