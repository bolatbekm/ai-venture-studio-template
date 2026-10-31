---
name: business-model
description: Run Stage 6 business modeling. Dispatches business-analyst (revenue model, CAC/LTV, bear/base/bull scenarios, MRR milestones) and pricing-monetization (pricing tiers) in parallel. Use once the problem/ICP/competitive landscape are validated, before solution design begins.
---

# /business-model

Runs Stage 6 (Business model).

## Steps

1. Read the active venture's `state.md`, `research/02-icp.md`, `research/04-competitive-intelligence.md`.
2. Dispatch in parallel:
   - `business-analyst` → EXPECTED OUTPUT `ventures/<slug>/research/05-business-analysis.md`.
     Require bear/base/bull scenarios and explicit assumptions next to every number — reject
     fake precision.
   - `pricing-monetization` → EXPECTED OUTPUT
     `ventures/<slug>/research/11-pricing-monetization.md`. Require willingness-to-pay evidence
     and competitor pricing be considered before a number is chosen; max 2-4 tiers.
3. Cross-check: does the pricing model actually produce the margins/CAC assumed in the business
   analysis? If not, flag the contradiction and re-dispatch one or both agents with sharper
   constraints.
4. Update `state.md`: BUSINESS MODEL, PRICING.
5. Update `scorecard.md`: willingness to pay, retention potential, expansion potential rows.
6. Log the business model / pricing decision in `decision-log.md`.
7. Respond using the Default Response Format. End with the highest-leverage next action —
   typically `/solution-design`.
