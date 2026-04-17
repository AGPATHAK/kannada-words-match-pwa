# Issue M3-01 — Introduce review-ready selection modes and round-source rules

## Goal

Refactor round generation so the app can select words from meaningful learning pools rather than from a single undifferentiated deck shuffle.

## Why

Milestone 2 records useful learner signals, but the app still chooses round words as if every word were equally relevant. Milestone 3 needs a clean selection foundation before bucket logic or mistakes practice can become meaningful.

## Scope included

- keep the app as a single self-contained HTML file
- preserve the current core gameplay
- refactor round selection so it can choose from explicit pools such as:
  - full deck
  - new / unseen words
  - review-ready words
  - mistakes / weak words (selection hook only if helpful)
- keep the current default behavior sensible if no special mode is active
- introduce small helper functions that make later mode-specific round selection straightforward
- preserve current stat storage and summaries

## Out of scope

- no bucket promotion/demotion rules yet
- no explicit mistakes mode UI yet
- no Devanagari display modes
- no personal deck
- no major UI redesign

## Acceptance criteria

- round generation is no longer hardwired to one simple full-deck shuffle
- the code clearly supports selecting rounds from different word pools
- current default play still works
- no gameplay regressions
- the app remains a single HTML file

## Validation

- load app normally and play at least one full round
- verify current default behavior still works
- inspect the code and confirm there are clear round-source helpers
- verify no console errors

## Likely file

- `index.html`

## Constraints

- keep implementation lightweight
- do not add review UI yet unless a tiny internal setting is truly needed
- do not implement later issues prematurely
