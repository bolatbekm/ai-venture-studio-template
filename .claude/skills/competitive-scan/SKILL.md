---
name: competitive-scan
description: Run Stage 4 competitor and alternative analysis. Dispatches competitive-intelligence to map direct/indirect/manual competitors, pricing, and positioning, and to surface underserved market gaps. Use once problem + ICP are defined, or to refresh competitive intel periodically.
---

# /competitive-scan

Runs Stage 4 (Competitor / alternative analysis).

## Steps

1. Read the active venture's `state.md` (PROBLEM, ICP) and `research/02-icp.md`.
2. Dispatch `competitive-intelligence` (Agent tool) with a full brief per CLAUDE.md §10,
   EXPECTED OUTPUT pointing at `ventures/<slug>/research/04-competitive-intelligence.md`.
   Instruct it to cover direct, indirect, manual/Excel/ChatGPT alternatives — not just funded
   startups.
3. Review the output. Do not accept "competition exists, therefore bad market" as a conclusion —
   push back if the agent frames it that way; require a market-gap analysis instead.
4. Update `state.md`: ALTERNATIVES, COMPETITORS, DIFFERENTIATION.
5. Update `scorecard.md`: competition, differentiation rows.
6. Log any positioning decision that follows (e.g. "we differentiate on X gap") in
   `decision-log.md`.
7. Respond using the Default Response Format. End with the highest-leverage next action —
   typically `/validate-idea` (if not yet run) or `/red-team-review`.
