---
name: validate-idea
description: Run Stage 3 problem validation and Stage 5 idea revalidation. Dispatches idea-revalidator (to attack the idea) and customer-interview (to design non-leading interviews) in parallel, then applies the Validation Ladder to decide whether to proceed, test more, revise, pivot, or kill. Use before any product/technical work begins on an idea.
---

# /validate-idea

Runs Stage 3 (Problem validation) and Stage 5 (Idea revalidation). Can be re-run any time new
evidence arrives.

## Steps

1. Read the active venture's `state.md`, `research/01-painstorming.md`, `research/02-icp.md`.
2. Dispatch in parallel (single message, multiple Agent tool calls):
   - `idea-revalidator` → brief per CLAUDE.md §10, EXPECTED OUTPUT
     `ventures/<slug>/research/03-idea-revalidation.md`. Emphasize: try to prove this wrong, run
     the pre-mortem, identify the cheapest invalidating test.
   - `customer-interview` → brief with EXPECTED OUTPUT
     `ventures/<slug>/research/15-customer-interviews.md`, asked to produce a non-leading
     interview script for this specific ICP/problem (not to fabricate interview results).
3. Review both outputs critically. Identify contradictions between them and with prior research.
4. Apply the **Validation Ladder** (CLAUDE.md §6): classify all evidence gathered so far as
   Weak / Moderate / Strong. Do not let the venture advance past Stage 5 on Weak evidence alone
   when Moderate/Strong evidence is cheaply obtainable — recommend the founder actually run the
   interview script against real people before proceeding, if that hasn't happened yet.
5. Update `state.md`: VALIDATION EVIDENCE (tagged Weak/Moderate/Strong), KEY ASSUMPTIONS, MAJOR
   RISKS.
6. Update `scorecard.md` (pain intensity, frequency, urgency, willingness to pay rows at minimum).
7. **Make and log the gate decision** in `decision-log.md`: Proceed / Test / Revise / Pivot /
   Kill, with WHY, EVIDENCE, ALTERNATIVES CONSIDERED, REVERSIBLE/IRREVERSIBLE, WHEN TO REVISIT.
   If the decision is Kill, update `ventures/INDEX.md` status to `killed` and reset
   `ACTIVE_VENTURE.md` — the founder decides whether to start `/new-venture` again immediately.
8. Respond using the Default Response Format, DECISION field explicit. End with the highest-
   leverage next action.
