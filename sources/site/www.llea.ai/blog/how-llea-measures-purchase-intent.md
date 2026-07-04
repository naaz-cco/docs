# Source: https://www.llea.ai/blog/how-llea-measures-purchase-intent

[All posts](https://www.llea.ai/blog)

"AI-powered intent" is the kind of phrase that means everything and nothing. This post unpacks exactly what we measure, how we turn raw behaviour into a score between 0 and 100, and what you can and can't expect from intent data.

## The signals we actually read

llea.ai listens to four families of signals. None of them require code changes or a custom pixel. They come from the Shopify Admin API and our standard web pixel or theme extension.

| Family | What we read |
| --- | --- |
| Engagement depth | Time on product pages, scroll depth, image carousel interactions, variant swatch clicks |
| Funnel progression | Product view → add to cart → checkout start → contact info entered → purchase |
| Repeat behaviour | Number of sessions on a product/category in the last 7/14/30 days; cross-device stitching where customer ID is known |
| Recency & velocity | How recently the shopper engaged, and whether engagement is accelerating or decaying |

## How signals become a score

We don't bolt the same formula on every store. Each merchant gets a per-store model trained on their own purchase history. The model learns, for your specific catalog, which combinations of signals reliably preceded a purchase. That score (0–100) is what shows up on every customer's profile.

Every score links back to the underlying signals. Click a high-intent customer and you'll see _why_ they're scored that way: which sessions, which products, which signals. No black box.

Engagement depthtime, scroll, swatchesFunnel progressionview → cart → checkoutRepeat behavioursessions in 7/14/30 dRecency & velocityaccelerating or decayingPer-store modeltrained on your purchases87/ 100Every score links back to the signals that produced it.

Four signal families feed a model trained on your store's own purchase history. Output: one score per shopper, 0–100.

## How many sessions before a shopper is "high intent"?

Usually 2–4 sessions on a product or category within a 7-day window, combined with at least one mid-funnel signal (add-to-cart, variant change, lingering on product page). The exact threshold is store-specific. Fashion stores see intent crystallise faster than electronics, which involve more deliberation.

## What about anonymous visitors?

Most Shopify traffic is anonymous on first visit. llea.ai assigns a pseudonymous visitor ID (a cookie / local-storage key) and scores them just like any logged-in shopper. If they later enter their email at checkout or via a popup, we stitch the anonymous history to their Shopify customer ID automatically. No history is lost.

## Multi-device shoppers

Cross-device stitching happens once the shopper is identified (email captured, logged in, past customer). Before identification we treat each device as a separate session, which is the honest answer. No analytics tool can reliably link anonymous mobile and desktop sessions to the same human without a shared signal. We don't fingerprint.

## How accurate is the prediction?

On a mature model (4–8 weeks post-install), our top-decile intent scores convert at roughly **4–7× the rate of the average visitor**. The bottom decile rarely converts at all. The middle bands are noisier, and that is expected. Predicting human shopping decisions is probabilistic, not deterministic.

What matters operationally is not the absolute number but the _ranking_: if your top 5% of visitors today convert 6× as well as your average, you have a high-ROI list to focus spend on. That's what the dashboard shows.

store averageD1D2D3D4D5D6D7D8D9D10Conversion rate by intent decileTop decile converts ~6× the store average. Bottom 30% barely move.Top decile (D9–D10) · where outreach pays

Visitors bucketed into intent deciles. Outreach spend goes into D9–D10. The bottom 30% gets left alone.

## Window shoppers vs serious buyers

The model learns the difference. Window shoppers tend to have wide, shallow engagement: many product views, low time-per-page, no funnel progression. Serious buyers narrow their attention: fewer products, more time, mid-funnel signals like add-to-cart or revisits to the same variant. We score these very differently.

## What we deliberately don't do

- **No browser fingerprinting.** We respect Do Not Track headers and GPC. Cookies are the only persistent identifier.
- **No cross-merchant data sharing.** Your customers' intent profiles never leave your store. We do not pool data across our customer base.
- **No training of foundation models on your data.** Our LLM provider is contractually barred from training on your prompts.

## What you can do with the score

- Build a "ready to buy" prediction list of customers likely to convert in the next 7, 30, or 90 days, refreshed continuously
- Trigger Email, WhatsApp, or SMS only when intent crosses a threshold
- Suppress your blast list to exclude low-intent shoppers, so spend goes to the high-intent cohort instead
- Identify which products are generating the most organic intent, useful for restock and ad-spend decisions

The point of intent data isn't to replace your judgement. It's to give your judgement better inputs. If you want to see how it plays out on your store's actual traffic, [book a 30-minute call](https://calendly.com/riyaz-llea/30min) and we'll walk through a live dashboard.