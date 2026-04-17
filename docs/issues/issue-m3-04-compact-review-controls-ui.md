# Issue M3-04 — Add compact review controls in the UI

## Goal

Expose review-oriented play choices in the UI without cluttering the current clean layout.

## Why

Milestone 3 should make review behavior visible and usable, not just hidden in internal logic. But the control surface must remain compact and learner-facing.

## Scope included

- keep the app as a single self-contained HTML file
- add a compact way to choose review mode / round source
- preserve the current visual style and hierarchy
- keep the board visually primary
- make mobile behavior acceptable

## Suggested UI direction

A lightweight control such as:
- a small segmented control
- a compact select/dropdown
- a small mode row

Possible modes:
- All words
- Review
- Mistakes
- Weak words

Codex may choose the cleanest compact control that fits the current layout.

## Out of scope

- no major redesign
- no heavy settings panel
- no Devanagari display modes
- no audio
- no personal deck

## Acceptance criteria

- learner can see and change the active practice mode
- controls remain compact and visually secondary
- current gameplay remains stable
- mobile responsiveness is not worsened
- app remains a single HTML file

## Validation

- switch between modes and start new rounds
- verify the selected mode affects round source appropriately
- verify layout remains clean on desktop and narrow widths
- verify no console errors

## Likely file

- `index.html`

## Constraints

- keep text chrome low
- preserve the current UI polish direction
