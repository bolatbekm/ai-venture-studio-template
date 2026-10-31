---
name: growth-loop
description: Run Stages 13-14 measurement and growth. Dispatches product-analytics (what the metrics say) and growth-experiment (what to try next) in parallel, then applies the Kill/Pivot Rule to decide whether to keep improving, pivot, or kill. Use on a recurring cadence once the venture has real customers/usage.
---

# /growth-loop

Runs Stage 13 (Measure retention) and Stage 14 (Improve / pivot / scale). Designed to be re-run
regularly (weekly/biweekly) once the venture has live usage.

## Steps

1. Read the active venture's `state.md` (METRICS, EXPERIMENTS) and any raw usage data the
   founder supplies.
2. Dispatch in parallel:
   - `product-analytics` → EXPECTED OUTPUT `ventures/<slug>/research/17-product-analytics.md`.
     Feed it whatever real metrics exist; do not let it fabricate numbers.
   - `growth-experiment` → EXPECTED OUTPUT
     `ventures/<slug>/research/16-growth-experiments.md`. Feed it the current metrics readout and
     any completed-experiment results so new proposals build on prior learning.
3. Review both. Check whether metrics are trending toward or away from the milestones in
   `research/05-business-analysis.md`.
4. Apply the **Kill/Pivot Rule** (CLAUDE.md §13): if evidence shows weak pain, low willingness to
   pay, unattractive CAC, poor retention, or minimal AI advantage, say so plainly — don't stay
   quiet to avoid disappointing the founder.
5. Update `state.md`: METRICS, EXPERIMENTS, NEXT ACTIONS.
6. Update `scorecard.md` if new evidence changes retention/expansion/CAC-related scores.
7. **Make and log the decision** in `decision-log.md`: continue current course / run specific
   experiments / pivot / kill.
8. If killed or paused, update `ventures/INDEX.md` and `ACTIVE_VENTURE.md` per CLAUDE.md §13.
9. Respond using the Default Response Format, DECISION field explicit. End with the highest-
   leverage next action — usually the single experiment worth running next.
