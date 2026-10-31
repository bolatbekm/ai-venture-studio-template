---
name: gtm-launch
description: Run Stages 10-12 go-to-market. Dispatches gtm-manifest-builder first (positioning source of truth), then seo-geo-content, smm-distribution, and sales-agent in parallel, briefed with the manifest. Use once the product is built or near-built, before/at launch.
---

# /gtm-launch

Runs Stage 10 (implicit — GTM prep) through Stage 12 (Acquire first customers).

## Steps

1. Read the active venture's `state.md` (VALUE PROPOSITION, ICP, PRICING, DIFFERENTIATION).
2. Dispatch `gtm-manifest-builder` first (EXPECTED OUTPUT
   `ventures/<slug>/research/10-gtm-manifest.md`) — every other agent in this skill depends on
   its positioning statement.
3. Review the manifest with the founder if the positioning is a meaningfully new claim (this is
   close to "external publication" territory — check before it goes live anywhere public).
4. Dispatch in parallel, each briefed with the GTM manifest as CONTEXT:
   - `seo-geo-content` → EXPECTED OUTPUT
     `ventures/<slug>/research/12-seo-geo-content.md`. Require high-intent-query prioritization.
   - `smm-distribution` → EXPECTED OUTPUT
     `ventures/<slug>/research/13-smm-distribution.md`. Require it to pick 2-3 channels max.
   - `sales-agent` → EXPECTED OUTPUT `ventures/<slug>/research/14-sales.md`. Require the early-
     stage framing: learn from customers, don't automate spam.
5. Update `state.md`: DISTRIBUTION.
6. Log the GTM strategy decision in `decision-log.md`.
7. Update `ventures/INDEX.md` status to `launched` once these are actually executed (not merely
   planned) and `state.md` STATUS accordingly.
8. Respond using the Default Response Format. Remind the founder: sending real outreach messages,
   publishing content, or posting publicly requires their explicit go-ahead — this skill produces
   plans and drafts, not sent/published artifacts.
9. End with the highest-leverage next action.
