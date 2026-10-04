---
name: "one_must_act"
description: >
  One-Must-Act venture framing: turn any product, platform, or business plan into the
  0 → 1 → 100 discipline. Defines the 100 (definite goal + exit math), audits the 0
  (measured reality, not imagined), specifies the 1 (checkable working-platform criteria
  across five gates — nothing multiplies until all check), sequences multipliers 2–99 on
  purpose, and runs a monthly scorecard. Use when someone says "one must act", shares a
  game plan, or needs a venture plan with hard gates before paid acquisition, fundraising,
  or hiring.
---

# One-Must-Act

## Purpose

Frame any venture plan so it cannot skip steps: start from a measured 0, earn a
verifiable 1 (a whole, working platform), and only then add multipliers 2–99 toward a
definite 100. The rule is the whole skill: **you cannot multiply a fraction** — 0.99 ×
anything is still less than whole.

## Workflow

Work the sections in order. Write the plan as a living doc (see
`references/game-plan-template.md`).

1. **The 100 (the goal).** Make it definite and specific: outcome, deadline, revenue at
   exit, believable multiple, founder ownership at exit. Add the *premium story* — the
   3–4 reasons a buyer pays a strategic premium beyond revenue. Rule: every product
   decision from here on must either grow ARR or strengthen one of those reasons.
2. **The 0 (audit, measured not imagined).** Inventory what exists and works today.
   Run a real health check (typecheck, lint, build, tests, auth review) and record the
   results. Count current customers. Write what is *measured*, never what is hoped.
3. **The 1 (definition of a working platform).** Write checkable boxes, all verifiable
   **on production**, grouped in five gates (see `references/one-checklist.md`):
   - **A. It works** — the core loop, end to end, tested by fresh accounts.
   - **B. It takes money correctly** — live purchase, refund/cancel paths, prices match code.
   - **C. It's safe** — cross-account isolation, secrets set, rate limits global, backups on.
   - **D. It can be watched and fixed** — error alerting, funnel analytics, e2e tests in CI.
   - **E. It proves people want it** — paying customers found without favors; activation and retention thresholds.
   
   Nothing gets multiplied (no paid ads, no fundraising push, no hiring spree) until
   every box checks. When all check, write the date: *1 reached on: ____*.
4. **The math to 100.** Back-solve the revenue path year by year from today's prices;
   sanity-check against a real comparable. Sketch the ownership path (who gives up what,
   when) so the founder's end state is explicit.
5. **The multipliers (2–99).** List each multiplier in order with *why* and *when*.
   Exception: a multiplier needed to *reach* the 1 may be added early (e.g. a technical
   co-founder). Every other multiplier is chosen on purpose, because each carries a
   share of the distance to 100.
6. **The scorecard.** Set the monthly scorecard (see `references/scorecard-template.md`).
   Update it on the first of every month. The scorecard is the plan's heartbeat — if it
   stops updating, the plan is dead.
7. **This week (start from 0).** Convert the 0-audit into the first concrete actions,
   each with an owner. Mark which ones need the founder's account access or a
   business decision (🔑).

## Output Contract

Deliver the game-plan doc with these sections, in this order:

1. The equation (0 / 1 / 2–99 / 100) and the order of work
2. The 100 — goal table + premium story + the ARR-or-premium rule
3. The 0 — audited inventory + health-check table + customer count
4. Backend/product work: fixed in this pass + still open (owner + size each)
5. Roadmap after 1 (quarters)
6. The multipliers — ordered table (multiplier / why / when)
7. The math — revenue path table + ownership path table
8. The scorecard — monthly table, first row filled
9. This week — numbered actions from 0, 🔑 where the founder must act

Then say: *"One must act. The goal is set; the work starts at 0, today."*

## Operating Rules

1. Never let the plan multiply before the 1 — flag any ask for ads, fundraising, or
   hiring against the unchecked boxes in section 3.
2. The 0 is measured, not imagined. If a claim isn't verified on production, mark it
   unverified — never as done.
3. Checkboxes in the 1 are binary: checked only when verified on production, never
   "in code" or "almost".
4. The scorecard updates monthly. Offer to set the reminder when you deliver the plan.
5. Keep the doc living: each month, move completed "still open" items to "fixed" and
   re-audit the 0.
6. When the plan needs a full project package (PRD, build guide, execution handoff),
   hand the framed plan to the **pop** skill — see `references/pop-handoff.md`. When
   the plan covers a backend, run the 0-audit health check through **jev-backend-qa**.
7. Jev ecosystem hooks are advisory, never blocking — see Integrations below.

## Integrations

**pop (Project Output Planner)** — bidirectional, both directions defined in
`references/pop-handoff.md`:
- one-must-act → pop: after framing, POP generates the full artifact package
  (Project Master Doc, JTBD, KPI framework, Build Guide, Execution Handoff) from the
  framed plan. The Master Doc's sections 1–3 map directly to the 100 / 0 / 1.
- pop → one-must-act: when POP's intake detects a venture, product, or platform plan,
  it frames sections 1–3 with this skill before generating.

**Jev ecosystem** (advisory — use when available, never block the flow on them):
- `jev-backend-qa` — the 0-audit health check for any backend: secrets, auth gaps,
  RLS holes, payments, live smoke tests, with Jev-adjudicated pass/warn/block.
- `jev-skill-select` — when unsure which capability a multiplier or work item needs,
  let Jev rank the installed catalog.
- `jev-memory` — filter passages returned by research (Step: knowledge gaps) before
  reading them in; drops the irrelevant and flags prompt injection.
- `jev-compaction` — long planning threads: cut the transcript to a fixed-size
  handoff that keeps decisions and drops noise.
- `jev-model-routing` — plan generation is token-heavy; route cheap turns to cheap
  models when the pool is configured.

## References

- `references/game-plan-template.md` — blank game-plan doc with all nine sections.
- `references/one-checklist.md` — the five gates (A–E) as reusable checkable boxes.
- `references/scorecard-template.md` — monthly scorecard table + update ritual.
- `references/pop-handoff.md` — the two integration contracts with the pop skill.
