# Issue M3-05 — Refine mastery and summary semantics for review intelligence

## Goal

Adjust the learner summaries and mastery interpretation so they remain honest and useful once review intelligence is active.

## Why

The app now has richer learner-state semantics: direct correct, incorrect, forced completion, buckets, and review modes. The summary language and mastery logic should stay aligned with that richer model.

## Scope included

- keep the app as a single self-contained HTML file
- refine mastery calculation only if the new review model makes it necessary
- refine summary wording if needed for clarity
- keep the UI compact
- preserve the distinction between direct success and elimination-based completion
- make sure summaries still feel learner-facing rather than analytical

## Out of scope

- no major dashboard
- no charts
- no Devanagari display modes
- no personal deck
- no audio
- no major UI redesign

## Acceptance criteria

- mastery logic remains explicit and honest
- summaries still read clearly after Milestone 3 changes
- direct correct and forced completion remain distinct in learner-facing language
- current gameplay remains unchanged
- app remains a single HTML file

## Validation

- inspect summaries after several rounds in different modes
- verify mastery still behaves sensibly
- verify summary wording matches the underlying data model
- verify no console errors

## Likely file

- `index.html`

## Constraints

- do not introduce opaque scoring
- preserve the clean compact UI
