---
name: new-venture
description: Initialize a new venture (Stage 0). Copies the venture template, asks the founder's high-value intake questions, sets the venture active, and routes into either pain discovery or idea validation. Use when starting to explore a brand new opportunity or when the founder brings an existing idea for the first time.
---

# /new-venture

Runs Stage 0 (Founder goals & constraints) and hands off to Stage 1 or Stage 3.

## Steps

1. **Read `founder-profile.md`.** If key fields are `Unknown — requires input.`, ask the founder
   **at most 3-5 high-value questions in one batch** (CLAUDE.md §14) — do not run a 30-question
   interview. Reasonable questions to prioritize: desired business model, B2B vs B2C, available
   time/capital, technical/sales capability, any hard constraints. Skip questions you can safely
   assume — label the assumption instead of asking.
2. Update `founder-profile.md` with the answers (only overwrite fields the founder actually
   answered; leave others as `Unknown — requires input.`).
3. Ask the founder one framing question if not already obvious from their message: **are we
   searching for a new opportunity, or evaluating an existing idea?**
4. Choose a short kebab-case `slug` for the venture (from the idea, or a placeholder like
   `opportunity-1` if none exists yet).
5. Copy `ventures/_template/` to `ventures/<slug>/` (preserve the `research/` subfolder).
6. Fill in `ventures/<slug>/state.md` header: VENTURE NAME, SLUG, CURRENT STAGE (`1` if
   searching, `2` if an idea exists), STATUS (`exploring`), LAST UPDATED. If an idea already
   exists, fill PROBLEM/PRODUCT with what the founder described, clearly labeled ASSUMPTION where
   unverified.
7. Add a row to `ventures/INDEX.md`.
8. Set `ventures/ACTIVE_VENTURE.md` `slug:` to the new venture.
9. Log the venture's creation in `ventures/<slug>/decision-log.md` using the template there.
10. Route:
    - **No idea yet** → hand off to `/pain-discovery`.
    - **Existing idea** → hand off to `/validate-idea` and `/competitive-scan` (both should run
      before any product/technical discussion — per CLAUDE.md §18).
11. Respond using the Default Response Format (CLAUDE.md §15). End with the single highest-
    leverage next action.
