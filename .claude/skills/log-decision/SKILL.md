---
name: log-decision
description: Append a correctly-formatted entry to the active venture's decision log (date, decision, why, evidence, assumptions, alternatives considered, reversible/irreversible, when to revisit). Use any time a real decision is made — advancing a stage, choosing tech/pricing/GTM direction, overruling a subagent, killing/pivoting — even outside another skill's normal flow.
---

# /log-decision

Appends one entry to `ventures/<slug>/decision-log.md`. Never edits or deletes a prior entry — if
a past decision is reversed, add a new entry that references it by date/title.

## Steps

1. Read `ventures/ACTIVE_VENTURE.md` to find the active venture's `decision-log.md`.
2. Gather, from the conversation or by asking the founder if genuinely unclear:
   - **DECISION** — what was decided, one clear sentence.
   - **WHY** — the reasoning.
   - **EVIDENCE** — what supported it, with sources where applicable (link to the relevant
     `research/*.md` file rather than restating it).
   - **ASSUMPTIONS** — what's still unverified.
   - **ALTERNATIVES CONSIDERED** — what else was on the table and why it lost.
   - **REVERSIBLE / IRREVERSIBLE** — which, and why (per CLAUDE.md §16, irreversible technical
     architecture or legal commitments need explicit founder sign-off before logging as decided).
   - **WHEN TO REVISIT** — a concrete trigger or date, never "eventually."
3. Append a new dated entry to `decision-log.md` using the template already in that file. Do not
   reformat or remove existing entries.
4. If the decision changes venture direction (stage, status, kill/pivot), also update
   `state.md` (CURRENT STAGE/STATUS/DECISIONS) and, if relevant, `ventures/INDEX.md`.
5. Confirm back to the founder in one or two sentences what was logged and where.
