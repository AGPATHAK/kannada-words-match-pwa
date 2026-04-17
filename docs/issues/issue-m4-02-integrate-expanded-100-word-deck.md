# Issue M4-02 — Integrate the expanded 100-word deck into the app

## Goal

Replace the current 50-word-only content baseline with the curated 100-word deck while preserving app stability.

## Why

Once the next 50 words are defined, the app needs to actually incorporate them so the learning universe expands in a meaningful way.

## Scope included

- integrate the 100-word curated deck into the single-file app
- preserve current stat storage compatibility where possible
- preserve existing fields and learner-state logic
- keep current gameplay stable

## Out of scope

- no staged introduction logic yet
- no personal deck
- no Devanagari display-mode work
- no major UI redesign

## Acceptance criteria

- app uses the full curated 100-word deck
- deck items remain well-formed and schema-compatible
- current gameplay still works
- current stats and summaries are not broken

## Validation

- load the app and verify the new deck is available
- play multiple rounds and confirm words beyond the original 50 appear
- verify no console errors
- verify localStorage/stat behavior is not broken

## Likely file

- `index.html`

## Constraints

- preserve the current single-file design
- avoid introducing later milestone logic prematurely
