---
name: red-team-review
description: Run a Red Team attack against the current venture at any stage — why might nobody care/pay, CAC/retention/regulatory/API-dependency risk, and whether a competitor or ChatGPT could destroy the product. Use at Stage 5 as a gate, and periodically afterward (before major spend, before build, before launch, or whenever the founder senses confirmation bias creeping in).
---

# /red-team-review

Runs a Red Team attack. Mandatory at Stage 5; recommended before Stage 9 (build) and Stage 11
(launch), and any time the founder asks for a reality check.

## Steps

1. Read the **full** active venture `state.md`, `scorecard.md`, and the last 3-5 decision-log
   entries.
2. Dispatch `red-team` (Agent tool) with a full brief per CLAUDE.md §10 — CONTEXT must include
   the entire `state.md` content, not a summary. EXPECTED OUTPUT:
   `ventures/<slug>/research/18-red-team.md` (append a new dated session, don't overwrite prior
   ones).
3. Take the findings seriously even when uncomfortable — do not soften them before presenting to
   the founder. If the Red Team's verdict conflicts with other agents' optimism, surface the
   conflict explicitly rather than picking a side.
4. Update `state.md`: MAJOR RISKS (add/update), and CURRENT STAGE only if this review is the
   stage-5 gate check.
5. **Make and log the gate decision** in `decision-log.md`: Proceed / Test / Revise / Pivot /
   Kill, with the Red Team's findings as EVIDENCE.
6. Respond using the Default Response Format, DECISION field explicit. End with the highest-
   leverage next action — often the "cheapest test that could invalidate the idea" the Red Team
   or idea-revalidator identified.
