# The 1 — Five Gates (reusable checklist)

The venture is a **1** when every box below is checked **on production**, not just in
code. Until then: no paid ads, no fundraising round, no hiring beyond what's needed to
check these boxes. Boxes are binary — checked only when verified, never "almost".

## A. It works (the core loop)

- [ ] All database migrations applied to production and verified.
- [ ] A brand-new visitor can complete the core loop end to end: land → sign up →
      first value delivered → value still there the next day. Tested by fresh test accounts.
- [ ] All current customers have completed that loop and said it was useful.

## B. It takes money correctly

- [ ] Payments in live mode. A real purchase goes checkout → webhook → tier/entitlement
      upgraded → features unlocked.
- [ ] Quantity > 1 / team-seat purchase works (if the pricing has seats).
- [ ] Cancel and refund paths tested. Customer portal works.
- [ ] Pricing page, checkout, and pricing code all show the same prices.

## C. It's safe

- [ ] Cross-account test passes: account B can never see account A's data
      (profile, files, workspaces, chats).
- [ ] Every production secret is set (check `.env.example` parity); no public defaults.
- [ ] Rate limits on expensive/AI endpoints hold across all servers, not per server.
- [ ] Database backups (point-in-time recovery) turned on.

## D. It can be watched and fixed

- [ ] Error tracking receiving errors from production; alert reaches the founder's phone.
- [ ] Analytics funnel live for the core loop (e.g. started → completed → paid).
- [ ] End-to-end tests of the core loop run in CI on every pull request.

## E. It proves people want it

- [ ] **10 paying customers** (any tier) who found it without a personal favor.
- [ ] **40%+** of new sign-ups reach first value in week 1.
- [ ] **25%+** of sign-ups come back in week 4.

When A through E are all checked, write the date: **1 reached on: ____________**

---

## Running the checklist with Jev

For backends, run gates A–D through **jev-backend-qa** (deterministic full-tree scans:
secrets, auth gaps, unbounded queries, RLS holes; DB/API/env/payment audits; live
smoke tests; Jev-adjudicated pass/warn/block with a fix-loop). Treat a BLOCK verdict
as an unchecked box — fix, re-run, then check.
