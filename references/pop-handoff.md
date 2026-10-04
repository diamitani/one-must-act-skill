# POP ↔ One-Must-Act Handoff Contracts

The **pop** skill (Project Output Planner) and **one-must-act** are built to call each
other. Each direction has one contract. Neither direction changes the other skill's
core flow — the handoff is a step inserted at a defined point.

---

## Direction 1: one-must-act → pop

**When:** the framed game plan needs a full execution package (PRD, build guide,
execution handoff, Asana tasks).

**Contract:**

1. one-must-act delivers the completed game-plan doc (sections 1–9 of the Output
   Contract) as the input.
2. Invoke pop with the game plan as the raw ask: *"POP: turn this game plan into a
   full project package."*
3. POP runs its canonical flow (PAL → interview → RAG DAL → NPAO → generate →
   handoff), treating the game plan's sections as pre-answered interview input:
   - Section 1 (the 100) → project goal / north-star outcome
   - Section 3 (the 1) → definition of done for the Master Doc and Build Guide
   - Section 4.2 (still open) → the initial NPAO-classified task list
   - Section 8 (this week) → the first Necessity tasks in the Execution Handoff
4. POP's guardrails apply unchanged (hard stops, confirm-first, autonomous).

## Direction 2: pop → one-must-act

**When:** POP's intake (Step 0/1) detects the project is a venture, product, or
platform plan — a business being built, not a one-off task.

**Contract:**

1. After PAL (Step 1) and before the interview (Step 2), run the one-must-act
   Workflow steps 1–3 (frame the 100, audit the 0, define the 1) as a pre-pass.
2. Feed the framed 100 / 0 / 1 into POP's artifacts:
   - **Master Doc sections 1–3** (Overview, Goals/KPIs, KPI Reporting Framework) ←
     the 100 and the 1-checklist gates
   - **Master Doc section 7** (Build Plan) ← the 0→1 work items (section 4.2)
   - **KPI doc** ← the scorecard: north-star, KPI tree, monthly cadence
   - **NPAO classification** ← multipliers 2–99 are O (Optimize) by default until
     the 1 is reached; anything needed to reach the 1 is N (Necessity)
3. Then continue POP's normal flow at Step 2 (interview), skipping questions the
   framing already answered.
4. If the user didn't ask for venture framing, skip the pre-pass — POP's normal
   flow is unchanged.

## Shared rules

- The 1-checklist boxes are binary and production-verified. POP's "Done when"
  conditions in the Build Guide inherit that bar.
- P&L ownership (POP Golden Rule 8) maps to the game plan's Owner line — never blank.
- Jev hooks stay advisory in both directions: `jev-backend-qa` for the 0-audit on
  backends, `jev-skill-select` for multiplier/tool choice, `jev-memory` for research
  filtering, `jev-compaction` for long handoffs. Never block either flow on Jev.
