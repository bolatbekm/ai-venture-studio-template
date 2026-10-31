---
name: pain-discovery
description: Run Stage 1 problem discovery. Dispatches the painstorming agent (and icp-researcher in a supporting role) to surface candidate painful problems, then compresses the results for the founder to pick a direction. Use when there's no venture idea yet, or the founder wants fresh problem surface area.
---

# /pain-discovery

Runs Stage 1 (Pain discovery).

## Steps

1. Read `ventures/ACTIVE_VENTURE.md` and the active venture's `state.md` and `founder-profile.md`
   for context (industry preference, geography, B2B/B2C, constraints).
2. Dispatch the `painstorming` subagent (Agent tool, `subagent_type: painstorming`) with a full
   brief per CLAUDE.md §10, EXPECTED OUTPUT pointing at
   `ventures/<slug>/research/01-painstorming.md`. Bias the search toward the founder's stated
   domain knowledge/preferences if any exist, but do not artificially narrow if the founder has
   none. The brief must instruct the agent to run its mandatory competitive gut-check (see the
   agent's own file, `.claude/agents/01-painstorming.md`) on every shortlisted candidate — a
   dedicated software/directory search pass, not just the general pain-discovery search. This
   was added 2026-10-12 after two separate candidates in one venture (`opportunity-3`) each
   turned out to have a live competitor that a general search pass missed.
3. Optionally, if the founder wants a specific industry angle, dispatch `icp-researcher` in
   parallel to sanity-check candidate ICPs for the most promising 2-3 problems surfaced.
4. **Review critically** — don't relay the subagent's list verbatim. Rank the candidate problems
   by pain intensity, frequency, and evidence strength (CLAUDE.md §6). Flag any that read as
   "cool AI idea" rather than "real painful job." **Check that every candidate you present to the
   founder as a strong option carries a completed competitive gut-check** (per the agent's
   mandatory step). If a candidate you'd otherwise rank highly is missing one, either ask the
   agent to run it before presenting that candidate, or present it to the founder explicitly
   flagged as "competitive status unchecked" rather than implying a clean field. Never present a
   candidate's "no competitor found" as settled — carry the agent's own confidence-qualified
   wording into your summary.
5. Update `ventures/<slug>/state.md`: OPEN QUESTIONS and NEXT ACTIONS, and PROBLEM if the founder
   picks one now.
6. Log the outcome in `decision-log.md` if a problem was selected (this is a real decision:
   ALTERNATIVES CONSIDERED = the other candidate problems).
7. Respond using the Default Response Format. Present 3-7 candidate problems compressed as: what
   we know → what it means → what we should test next. End with the single highest-leverage next
   action (usually: pick one to validate, or proceed to `/define-icp`).
