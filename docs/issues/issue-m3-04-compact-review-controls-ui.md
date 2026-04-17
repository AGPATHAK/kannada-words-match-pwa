# Issue M3-04 — Refine and polish review controls in the UI

## Goal

Refine the already-implemented review mode controls so they feel cleaner, clearer, and more stable across desktop and mobile layouts.

## Why

Milestone 3 Issue 3 already introduced compact review controls for `Daily Mix`, `Mistakes`, and `Weak Words`. That means this issue is no longer about adding review controls from scratch. It is now about polishing the control surface so the modes are clearer, the layout is more robust, and the learner-facing wording feels intentional.

## Scope included

- keep the app as a single self-contained HTML file
- refine the existing review mode controls rather than replacing them wholesale
- improve wording, visual polish, spacing, and interaction clarity where needed
- preserve the current visual style and hierarchy
- keep the board visually primary
- make desktop and mobile behavior more robust if needed
- allow small improvements to mode semantics or labels if they materially improve learner clarity

## Suggested refinement directions

Possible refinements may include:
- improving the wording of existing mode labels
- improving button/segmented-control spacing and balance
- improving selected-state clarity
- improving wrapping or stacking behavior on narrow widths
- making the mode row feel more intentional within the current layout
- optionally refining the set of visible modes if the current labels are not the clearest learner-facing terms

This issue should polish the existing control surface, not redesign the app.

## Out of scope

- no major redesign
- no heavy settings panel
- no Devanagari display modes
- no audio
- no personal deck
- no category/stage-limited practice
- no new analytics panel

## Acceptance criteria

- learner can still clearly see and change the active practice mode
- controls feel cleaner and more intentional than the current first-pass version
- controls remain compact and visually secondary
- current gameplay remains stable
- mobile responsiveness is not worsened
- app remains a single HTML file

## Validation

- switch between modes and start new rounds
- verify the selected mode still affects round source appropriately
- verify layout remains clean on desktop and narrow widths
- verify the active mode remains visually clear
- verify no console errors

## Likely file

- `index.html`

## Constraints

- keep text chrome low
- preserve the current UI polish direction
- do not duplicate work already completed in M3-03
