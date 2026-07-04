# Source: https://www.llea.ai/blog/shopify-setup-and-integrations

[All posts](https://www.llea.ai/blog)

Setup is meant to be boring. The fastest signal that a Shopify app respects your time is how little of it the install takes. This post walks through what installing llea.ai actually looks like, the platforms we connect to out of the box, and the edge cases (custom checkouts, headless, multi-store) that come up most often.

## The 5-minute install

You add the app from the Shopify App Store the same way you'd add any other app. Shopify asks you to approve the OAuth scopes we need — read access to customers, orders, products, and a web pixel for behavioural events. That's it. No theme edits. No code snippets. No developer required.

The pixel registers automatically; you don't paste anything into `theme.liquid`. If you're on a custom theme or a headless storefront, see the section further down.

## What happens in the first 24 hours

The moment you approve OAuth, we backfill the last 90 days of orders and customers from your store. That history is what trains your **per-store** model — the weights are unique to your catalog and your shoppers, not borrowed from another merchant.

Minute 0Install

Click "Add app" in Shopify. OAuth approves access.

Hour 1Backfill

We pull the last 90 days of orders + events.

Hour 24First scores

Per-store model trained. Live intent visible.

Week 4–8Mature model

Top-decile lift stabilises.

From install to live intelligenceNo code, no theme edits, no developer required.

A typical setup runway. Live scores appear within 24 hours; the model continues sharpening over the first 4–8 weeks.

You won't see useful intent on visitors who arrived _before_ the install — we can't backfill what wasn't tracked. From the moment the pixel is live, every session is scored.

## Will it slow down my store?

The pixel is loaded asynchronously and is roughly 14 KB gzipped. It does not block render, does not run on the critical path, and does not call any sub-resource on first load. We've benchmarked it on Shopify themes including Dawn, Impulse, Prestige, and a handful of custom themes — measurable Largest Contentful Paint impact has been under 50 ms in every case we've tested.

If you have a Lighthouse score you care about, run it before and after. If you see any regression we can't explain, we'll roll back the install — no questions asked.

## Theme compatibility

llea.ai works on any theme set as the active Online Store theme. Web Pixel support is tied to the Online Store runtime, not to a theme's age, codebase, or last-updated date. That means Dawn, every theme in the Shopify Theme Store, and older or vintage themes (including pre Online Store 2.0 bases) all deliver pixel events the same way once they're live on the storefront.

## The platforms we integrate with

llea.ai is built to make your existing stack sharper, not to replace it. The most common integrations:

How llea.ai routes outreachPixel events flow in. Outreach flows out through Shopify Flow to the CEP your store already uses.Shopify Storestorefront + adminpixel events\+ past ordersllea.aicomputes intentintent ≥ thresholdevent firedShopify Flownative router + webhooksnative or HTTPtriggerKlaviyoMailchimpWati · WhatsAppPostscript · SMSResend · Emailyour CEPYour campaigns and templates live in the CEP. llea.ai supplies the trigger; Shopify Flow routes it.

The actual control flow. llea.ai turns pixel events into intent, fires a Shopify Flow event when the threshold is crossed, and the CEP triggers the outreach.

- **Shopify Flow is the spine.** Every intent-threshold crossing in llea.ai fires a Flow event. Flow then routes it to whichever CEP you have configured, either through that CEP's native Shopify Flow connector or via an HTTP webhook.
- **Klaviyo, Mailchimp, ActiveCampaign, Omnisend, Brevo**: native Shopify Flow connectors. Your existing campaigns and templates fire on the llea.ai trigger.
- **WhatsApp tools** (Wati, AiSensy, Interakt, Gallabox): triggered via Shopify Flow or webhook, depending on which connector your provider exposes.
- **Postscript, Attentive** (SMS): same hand-off pattern through Shopify Flow.
- **MoEngage, CleverTap, WebEngage**: HTTP-webhook hand-off today; native connectors on the roadmap.
- **Meta and Google ads**: weekly lookalike-seed exports of your top-intent cohort for retargeting and prospecting.

## Custom checkouts, headless, multi-store

- **Custom checkout (Shopify Plus checkout.liquid):** works as-is. The pixel captures checkout events through the standard Web Pixel API regardless of customisations on top.
- **Headless (Hydrogen, Next.js, custom React storefronts):** supported — you'll add our small client SDK to your storefront. About 20 lines of code. We'll send you the snippet and a Hydrogen example.
- **Multi-store merchants:** install once per store. Each store gets its own model and its own dashboard, plus a roll-up view if you have 3+ stores.

## Where llea.ai sits in your existing stack

We don't replace Klaviyo, Shopify Flow, GA4, or your CRM. We add a layer on top that tells those tools _who_ to act on and _when_. If you already have a working Klaviyo flow for abandoned cart, llea.ai makes that flow fire only on the abandons that actually have purchase intent — and suppresses the ones who never had it.

The result is fewer messages going out, but the messages that go out land on the shoppers most likely to convert. Your CRM, your reporting, your campaign tools stay where they are. llea.ai becomes the routing brain in the middle.

## What to expect after install

- **Hour 24:** dashboard shows live intent scoring on current visitors. Backfill complete.
- **Week 1:** first usable segments. Your team can start building Klaviyo audiences.
- **Week 4–8:** model maturity. Top-decile conversion lift stabilises at a multiple of store average.
- **Ongoing:** model retrains weekly on fresh data. Seasonality and catalog changes are absorbed automatically.

If you'd rather see the install end-to-end on a live screen before committing, [book a 30-minute walkthrough](https://calendly.com/riyaz-llea/30min) and we'll do it together on a sandbox store.