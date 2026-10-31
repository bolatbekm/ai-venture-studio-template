---
name: venture-status
description: Print a compressed status summary of the active venture (or the whole portfolio) — current stage, key state fields, scorecard highlights, and the last few decisions. No research is run; this is a read-only summary. Use whenever the founder asks "where are we" or at the start of a session to re-orient.
---

# /venture-status

Read-only. Dispatches no subagents.

## Steps

1. Read `ventures/ACTIVE_VENTURE.md`.
   - If `slug: none` — read `ventures/INDEX.md` and present the portfolio table instead (skip to
     step 5).
2. Read the active venture's `state.md`, `scorecard.md`, and the last 3-5 entries of
   `decision-log.md`.
3. Compress into the Default Response Format (CLAUDE.md §15):
   - CURRENT STAGE, OBJECTIVE (what the venture is trying to accomplish right now), FINDINGS
     (compressed state highlights: problem, ICP, differentiation, pricing, key metrics if any),
     RISKS/UNKNOWN (from MAJOR RISKS and OPEN QUESTIONS), and the last decision made.
4. List OPEN QUESTIONS and NEXT ACTIONS verbatim from `state.md`.
5. End with the single highest-leverage next action — typically naming the next skill to run
   (e.g. "run `/competitive-scan` next").

Do not modify any files during this skill — it is pure read-and-summarize.
