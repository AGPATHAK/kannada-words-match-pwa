# Issue M4-05 — Align expanded content and stat conventions with the broader Kannada suite

## Goal

Clean up content and stat semantics so the expanded app remains compatible in spirit and wording with the broader Kannada learning ecosystem.

## Why

As the deck expands and the learning model becomes richer, the naming and structure should remain coherent with the rest of the Kannada suite. This improves future maintainability and keeps the product family feeling intentional.

## Scope included

- review and refine content/stage terminology where needed
- clean up wording or labels that become stale after deck expansion
- align stat/content conventions with the broader suite where it materially helps
- make small semantic cleanups if needed

## Out of scope

- no personal deck implementation
- no PWA packaging work
- no audio
- no Devanagari display modes
- no major UI redesign

## Acceptance criteria

- expanded content terminology is coherent
- stat/content wording remains learner-facing and consistent
- the app is better aligned with the broader Kannada suite
- current gameplay remains unchanged

## Validation

- inspect labels and summary wording after expansion
- verify terminology still makes sense with 100 words and staged introduction
- verify no console errors

## Likely file

- `index.html`
- related docs if needed

## Constraints

- keep cleanups small and purposeful
- avoid broad speculative refactors
