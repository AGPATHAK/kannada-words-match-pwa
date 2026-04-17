# Issue M3-02 — Implement Lite-Leitner buckets and bucket update logic

## Goal

Add lightweight bucket-based review progression on top of the existing learner stats.

## Why

The app already records direct correct, incorrect, forced completion, and seen counts. Milestone 3 now needs a simple rule-based progression model so review behavior can become intentional rather than random.

## Scope included

- keep the app as a single self-contained HTML file
- implement a Lite-Leitner model using the existing stat foundation
- use 5 buckets unless implementation strongly justifies a different count
- apply simple promotion/demotion rules
- keep forced final-pair completion distinct from direct correctness
- keep bucket changes inspectable in code and localStorage
- preserve current gameplay and summaries

## Recommended baseline model

- Bucket 1: highest review priority
- Bucket 2: next review priority
- Bucket 3: medium review priority
- Bucket 4: lower review priority
- Bucket 5: stable / low priority

Suggested progression rules:
- 2 consecutive direct correct matches -> move up 1 bucket
- 1 incorrect attempt -> reset to Bucket 1
- forced final-pair completion does not count as a direct success for promotion

Codex may refine details slightly if needed, but the logic should remain simple and explicit.

## Out of scope

- no mistakes/weak-words UI yet
- no category/stage-limited practice
- no audio
- no personal deck
- no major UI redesign

## Acceptance criteria

- bucket values are updated during gameplay
- direct correct and forced completion remain distinct
- incorrect attempts demote/reset appropriately
- current gameplay remains unchanged
- the app remains a single HTML file

## Validation

- play multiple rounds
- inspect localStorage and verify bucket movement is happening coherently
- verify forced completions do not promote like direct correctness
- verify no console errors

## Likely file

- `index.html`

## Constraints

- do not add complex scheduling formulas
- do not collapse raw learner signals into opaque scores
