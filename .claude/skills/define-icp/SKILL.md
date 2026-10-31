---
name: define-icp
description: Run Stage 2 ICP definition. Dispatches the icp-researcher agent to narrow the target customer for the chosen problem, separating user/buyer/decision-maker. Use once a problem has been selected from pain discovery, or whenever the current ICP needs sharpening.
---

# /define-icp

Runs Stage 2 (ICP definition).

## Steps

1. Read the active venture's `state.md` (PROBLEM, PAIN) and `research/01-painstorming.md`.
2. Dispatch `icp-researcher` (Agent tool) with a full brief per CLAUDE.md §10, EXPECTED OUTPUT
   pointing at `ventures/<slug>/research/02-icp.md`. Explicitly instruct it to reject vague
   descriptors and separate USER/BUYER/DECISION MAKER.
3. Review the output. Push back (re-dispatch with sharper QUESTIONS TO ANSWER) if the ICP is
   still described broadly (e.g. "SMBs", "marketers").
4. Update `state.md`: ICP, USER, BUYER, DECISION MAKER (add a field under Customer if the
   decision maker differs from the buyer).
5. Log the ICP choice in `decision-log.md` if it's a meaningfully narrowed/changed target.
6. Respond using the Default Response Format. End with the highest-leverage next action —
   typically `/validate-idea` or `/competitive-scan`.
