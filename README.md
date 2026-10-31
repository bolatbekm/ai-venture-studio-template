# AI SaaS Venture Studio

A multi-agent system for [Claude Code](https://claude.com/claude-code) that helps a **solo
founder** discover, validate, and build a software business — and, just as importantly, kill the
ideas that don't survive contact with evidence.

It is not an idea generator. Idea generators are abundant and nearly worthless: they produce
confident-sounding pitches with invented market sizes and no competitors, because finding problems
and finding competitors require different searches. This repo is the opposite — a system built to
**attack** ideas, including your own, before you spend months on them.

```
Find a real painful problem → validate that customers will pay → design the smallest
viable solution → build it → get the first customers → improve until it earns real revenue
```

---

## What's in here

| | |
|---|---|
| `CLAUDE.md` | The operating manual. 18 sections, read at the start of every session. This is the actual product — the agents are downstream of it. |
| `.claude/agents/` | 18 specialized subagents (painstorming, ICP research, competitive intel, red team, pricing, architecture, GTM…) |
| `.claude/skills/` | 12 slash-command workflows, one per pipeline stage |
| `founder-profile.md` | Your constraints — capital, time, skills, hard no's. Filled in once, reused forever. |
| `ventures/_template/` | Per-venture scaffold: state, scorecard, decision log, 18 research slots |

No dependencies, no build step, no API keys. It's markdown — the intelligence is in the
instructions, not in code.

## Quick start

```bash
git clone https://github.com/bolatbekm/ai-venture-studio-template.git my-venture-studio
cd my-venture-studio
claude
```

Then, in the session:

```
/new-venture
```

You'll be asked 3-5 questions (deliberately not 30), and the studio will route you into problem
discovery if you have no idea yet, or straight into validation if you do.

Bringing an existing idea? Just paste it and say so. It'll go through competitive analysis and
validation before anyone talks about features or tech stack.

---

## How it works

You talk to one **orchestrator**. It decides which specialists to dispatch, in what order, and
what each needs to know — then reviews what comes back rather than relaying it.

```
        You
         ↓
  ORCHESTRATOR  ──dispatches──→  18 stateless subagents
         ↓                              ↓
  ventures/<slug>/state.md  ←──  research/NN-<agent>.md
         ↓
  Evidence gate  →  next stage, or kill
```

Three design decisions make this work differently from "ask an AI about my startup idea":

**Subagents are stateless and cannot steer.** Each one starts cold with a written brief and
returns findings. Only the orchestrator writes `state.md` and `decision-log.md`. A specialist
can't quietly redefine the business to make its own answer look better.

**Every claim is tagged.** FACT (sourced, verifiable) / ASSUMPTION (unverified belief we're acting
on) / HYPOTHESIS (to be tested) / EVIDENCE / RECOMMENDATION. When something isn't known, the
required answer is `Unknown — requires validation.` — never an invented number. Market sizes,
revenue figures, and complaint counts are exactly where AI systems hallucinate most confidently,
and this is the guardrail against it.

**Evidence is ranked, and weak evidence doesn't pass gates.**

| | |
|---|---|
| **Weak** | You like the idea · AI says it looks promising · people say "interesting" · likes |
| **Moderate** | People confirm the problem · describe real workarounds · actively search for solutions · competitors have paying customers |
| **Strong** | Prospects take interviews · request demos · share internal data · run pilots · sign LOIs · **pay** |

A stage never advances just because the last report looked positive. It takes an explicit gate
check and a logged decision.

## The agents

**Problem & customer** — `painstorming` (finds problems, not ideas) · `icp-researcher` (who has the
pain, who pays, who decides) · `idea-revalidator` (tries to prove the idea wrong) ·
`competitive-intelligence` (direct, indirect and manual competitors) · `red-team` (attacks the
whole business, on demand at any stage) · `customer-interview` (non-leading scripts only)

**Economics** — `business-analyst` (CAC/LTV, margins, bear/base/bull) · `pricing-monetization`
(tiers from customer value, not guesswork)

**Product** — `product-strategist` (smallest lovable product) · `ai-solution-architect` (where AI
actually beats deterministic code) · `technical-architect` (a stack one person can maintain) ·
`ux-ui-designer` (screen by screen)

**Go-to-market** — `gtm-manifest-builder` (positioning, the source of truth for the three below) ·
`seo-geo-content` (search + AI answer engines) · `smm-distribution` (the *smallest* set of
channels) · `sales-agent` (founder-led motion)

**Growth** — `growth-experiment` (small, fast, measurable) · `product-analytics` (metrics that
matter; flags vanity traps)

## Slash commands

```
/new-venture       start a venture (or bring an existing idea)
/pain-discovery    no idea yet — go find a problem
/define-icp        narrow the target customer
/competitive-scan  map competitors and alternatives
/validate-idea     attack the idea + design interviews
/red-team-review   stress-test the whole business
/business-model    economics and pricing
/solution-design   product scope, AI layer, stack, screens
/gtm-launch        positioning and channels
/growth-loop       metrics, experiments, proceed/pivot/kill
/venture-status    where are we (read-only, no research)
/log-decision      record a decision properly
```

You rarely need them. Plain language works: *"check whether anyone already builds this"* routes
itself. Writing detailed briefs to individual agents is doing the orchestrator's job.

---

## Two opinions baked in

**Kill fast, and treat it as a win.** A killed idea is a successful experiment if it saved you
months. The studio is instructed to recommend abandonment on weak pain, low willingness to pay,
impossible distribution, commodity offering, minimal advantage over general-purpose AI, or
unreasonable complexity — and to never get attached. Killed ventures are never deleted; their
research and reasoning stay as institutional memory, which is what stops you from rediscovering the
same dead end in six months.

**Check for competitors first.** Learned the hard way, three times (see `CLAUDE.md` §6): a search
tuned to find *pain* — complaints, forum threads, cost figures — systematically misses small,
SEO-savvy, solo-built competitors, because their marketing doesn't rank on complaint queries. Three
separate ventures were shortlisted on a "no competitor found" read and each had a live, directly
competing product that only a dedicated vendor-site search surfaced. So the competitor pass now
runs **first**, before ICP work, before pain validation, before any product thinking. Validating a
problem whose solution already ships at a third of your intended price is spending the expensive
step before the cheap one.

In the most recent case, an idea arrived from an external generator scored **"9.0 / Pain 9"**. A few
hours of reading vendor pricing and help pages refuted it: the claimed moat was documented verbatim
on the market leader's own help page, at €7.90/month. Independently scored, it came out **24/75**,
with pain intensity 2 and willingness to pay 1.

> `CLAUDE.md` §6 cites specific ventures (`opportunity-2`, `opportunity-3`,
> `catchi-freelance-bookkeeping`) from the author's private venture log, which is not in this repo.
> The lessons are kept verbatim rather than genericized, because the specifics are what make them
> credible. Your own `ventures/` folder starts empty.

## Make it yours

The manual is meant to be edited. It already carries lessons from real ventures; yours will differ.
When something surprises you, write it into `CLAUDE.md` — that's the mechanism by which the studio
gets smarter, and it's worth more than any individual idea it produces.

Start with `founder-profile.md`. Be honest about hours and capital rather than aspirational: those
two numbers invalidate more otherwise-good ideas than anything else, and a studio optimizing
against fictional constraints gives fictional advice.

## License

MIT — do whatever you like with it.
