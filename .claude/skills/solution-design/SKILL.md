---
name: solution-design
description: Run Stages 7-9 solution design. Dispatches product-strategist (MVP scope), ai-solution-architect (where AI adds value), technical-architect (stack), and ux-ui-designer (screens) in sequence/parallel as appropriate. Use once the business model is set, before build begins.
---

# /solution-design

Runs Stage 7 (Solution design) through Stage 9 (MVP architecture).

## Steps

1. Read the active venture's `state.md` (PROBLEM, ICP, VALUE PROPOSITION, BUSINESS MODEL) and
   `research/05-business-analysis.md`.
2. Dispatch `product-strategist` first (EXPECTED OUTPUT
   `ventures/<slug>/research/06-product-strategy.md`) — everything else depends on the MLP scope
   it defines (Job To Be Done, must-have vs. explicitly-not-built features).
3. Review its output, then dispatch in parallel:
   - `ai-solution-architect` → EXPECTED OUTPUT
     `ventures/<slug>/research/07-ai-solution-architecture.md`, briefed with the must-have
     features from step 2. Require it to justify AI vs. deterministic software per component.
   - `technical-architect` → EXPECTED OUTPUT
     `ventures/<slug>/research/08-technical-architecture.md`, briefed with the same features plus
     the AI components once available (may need a second pass after ai-solution-architect
     returns). Apply the Build vs. Buy Rule (CLAUDE.md §9) and the Solo Founder Constraint
     (CLAUDE.md §8).
   - `ux-ui-designer` → EXPECTED OUTPUT `ventures/<slug>/research/09-ux-ui-design.md`, briefed
     with the primary workflow from step 2.
4. Cross-check all three against the Solo Founder Constraint — flag anything requiring large
   teams, heavy enterprise implementation, or significant upfront capital, unless evidence
   justifies it.
5. Update `state.md`: PRODUCT, TECH STACK.
6. Update `scorecard.md`: technical complexity, time to MVP rows.
7. Log the architecture/scope decisions in `decision-log.md` (these are often hard-to-reverse —
   mark REVERSIBLE/IRREVERSIBLE honestly).
8. Respond using the Default Response Format. Flag that Stage 9 "Pre-build validation" (CLAUDE.md
   §5, Stage 8) should happen before actual build if it hasn't (e.g. via `/validate-idea` with
   fresh evidence, or a landing-page/waitlist test). End with the highest-leverage next action.
