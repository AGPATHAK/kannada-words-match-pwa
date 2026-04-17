# Issue M4-03 — Implement staged introduction rules for new words

## Goal

Introduce the expanded deck in small controlled batches instead of exposing all 100 words equally at once.

## Why

Without staged introduction, the app risks becoming a random-word game. Controlled introduction keeps the active learning set manageable and helps the review system remain meaningful.

## Scope included

- add stage-aware introduction logic for the 100-word deck
- keep the learner-facing experience lightweight
- initially use quiet/background introduction rather than a heavy unlock ceremony
- make the rules explicit and inspectable

## Suggested direction

- only a limited batch of new words should enter the active learning pool at a time
- later-stage words should remain inactive until the current stage is sufficiently established
- the introduction rule should be simple, defensible, and easy to reason about

## Out of scope

- no personal deck
- no explicit “campaign” or gamified unlock flow
- no major UI redesign

## Acceptance criteria

- all 100 words are not treated as equally active at once
- only a controlled subset of new words enters the learning mix
- current review behavior remains stable
- app remains understandable and lightweight

## Validation

- inspect the active-pool logic
- verify newly introduced words appear in controlled quantities
- verify later-stage words are not dumped in too early
- verify no console errors

## Likely file

- `index.html`

## Constraints

- prefer quiet staged introduction over ceremony
- keep the rule simple and inspectable
