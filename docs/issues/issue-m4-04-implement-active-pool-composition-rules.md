# Issue M4-04 — Implement active-pool composition rules for new vs review vs weak words

## Goal

Make round composition intentionally review-heavy by defining how new, review, and weak words should mix in active play.

## Why

Once the app moves to 100 words, the active pool must stay trainer-like. A flat random draw would make the learning loop weaker and noisier.

## Scope included

- define and implement active-pool composition rules
- balance new words against review words and weak words
- preserve the current focused review modes
- keep the default practice mode learner-friendly and stable

## Suggested direction

A practical mix may emphasize:
- review words first
- weak words second
- a small number of new words
- no flood of unseen words

The exact ratio may be refined by implementation, but the logic should remain explicit and inspectable.

## Out of scope

- no personal deck
- no category/stage practice UI expansion beyond what already exists
- no major UI redesign
- no advanced analytics

## Acceptance criteria

- default practice is not a flat random draw across all active content
- new words enter in limited quantities
- weak/review words remain prominent
- focused practice modes still work
- app remains stable and understandable

## Validation

- play multiple rounds after staged introduction is active
- verify the round mix feels review-heavy rather than random
- verify weak/review/new words appear in sensible proportions
- verify no console errors

## Likely file

- `index.html`

## Constraints

- keep the model explicit and inspectable
- avoid opaque weighting formulas
