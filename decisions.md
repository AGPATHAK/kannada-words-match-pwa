# Decisions

## Milestone 1

- v1 is intentionally a single-file `index.html` prototype so the product stays easy to inspect, test, and iterate.
- The interaction model uses tap-to-pair selection instead of drag-and-drop because it is simpler and more reliable on mobile.
- Kannada tiles include a Devanagari scaffold under the main Kannada text to support beginner learners without replacing Kannada as the primary script.
- Milestone 1 was delivered as a focused issue-by-issue build, keeping scope limited to the implemented prototype loop rather than adding extra systems early.
- The initial prototype dataset was later replaced with a finalized curated 50-word beginner deck, while preserving the same core match interaction.
- The app remains single-file by design, but the internal code was logically refactored into clearer sections to support later persistence and stats work.
- At round completion, the English column realigns to the Kannada order so matched pairs line up visually.
- UI fit and visual polish were adjusted after deck expansion so the app sits more comfortably in the viewport without changing gameplay.
