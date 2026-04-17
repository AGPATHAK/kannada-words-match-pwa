# Issue M3-03 — Add mistakes / weak-words practice modes

## Goal

Allow the learner to intentionally practice words that are currently weak, error-prone, or recently missed.

## Why

This is one of the highest-value learning improvements for the app. Once persistent stats and bucket logic exist, the learner should be able to focus on difficult words instead of always replaying the full deck.

## Scope included

- keep the app as a single self-contained HTML file
- add one or two focused practice modes such as:
  - Mistakes
  - Weak words
- derive these pools from existing stats and/or bucket state
- handle small-pool cases gracefully
- preserve current default play mode
- keep the UI minimal

## Suggested practical definitions

Mistakes pool:
- words with at least one recorded incorrect attempt
- optionally prefer more recent or more frequent mistakes

Weak words pool:
- words in lower buckets and/or with poor direct-correct history
- forced completions should not make a word look strong

Codex may refine the exact thresholds, but they should remain simple and inspectable.

## Out of scope

- no personal deck
- no Devanagari display modes
- no category/stage-limited practice beyond what is necessary for this issue
- no heavy analytics UI
- no major UI redesign

## Acceptance criteria

- learner can trigger at least one focused review mode
- rounds can be drawn from mistakes / weak pools
- current default play still works
- the app handles too-few-words cases gracefully
- the app remains a single HTML file

## Validation

- create some mistakes in the app
- verify mistakes / weak mode draws from appropriate words
- verify the mode still yields playable rounds
- verify no console errors

## Likely file

- `index.html`

## Constraints

- keep the control surface minimal
- do not add bulky explanatory UI
