# AGENT_PROJECT.md (example: a small product app)

This file is the root bootstrap for this repo. Read it before interpreting shorthand or taking meaningful action.

## Identity

- project: `mano-app`
- owner: the product owner, final decision-maker
- purpose: offline mobile app for logging how you feel; privacy is the product

## Paths

- operating model: `../agent-operating-system/core/AGENT_USER_TEMPLATE.md`
- docs-root: `docs/` (git-ignored planning files) and `TASKS.md` (committed hand-off)
- product-philosophy: `none`

## Startup reads for `ss`

1. `TASKS.md`
2. `docs/REVIEW-LEDGER.md` (what was reviewed and decided)
3. `git status` and the last five commits

## Source of truth, in order

1. this file
2. `docs/ACTION-PLAN.md` and `docs/BRIEF.md`
3. `TASKS.md`
4. code and verified device behaviour

## Local rules (tighten only)

- Every user-visible string exists in both languages; a change to one is a change to both.
- Crisis numbers are verified against `content/regions/nepal.json`; nothing else may hard-code them.
- No release without the owner's explicit go.

## `sss`

Update `TASKS.md` first, then the ledger if a review happened, then show the owner the "Next" list.
