# Milestone 3 — Review Intelligence

## Purpose

Turn the current learner-stat foundation into a genuinely useful review system.

Milestone 2 established:
- a stable single-file architecture
- a curated 50-word deck
- per-word persistence in `localStorage`
- separate tracking for:
  - `seen`
  - `direct_correct`
  - `incorrect`
  - `forced_completion`
- lightweight session and all-time summaries
- a simple mastery progress indicator

Milestone 3 should build on that foundation to make review more intentional and scientifically stronger, without overcomplicating the app.

## Milestone goal

Introduce lightweight review intelligence so the app can:
- prioritize words that need work
- distinguish new words from review words
- support mistakes-focused practice
- begin using bucket-based progression
- keep the experience simple, inspectable, and learner-facing

## Guiding principles

- Keep the app as a single self-contained HTML file.
- Prefer explicit, inspectable rules over opaque scoring.
- Keep raw learner signals separate from derived review decisions.
- Preserve the distinction between direct correct and forced final-pair completion.
- Avoid a heavy dashboard or overengineered scheduler.

## In scope

- Lite-Leitner bucket logic
- review-ready data fields and bucket updates
- simple review selection rules
- mistakes / weak-words practice support
- basic mode selection for practice scope
- modest UI additions needed to support review behavior
- refinement of mastery interpretation where necessary

## Out of scope

- audio or pronunciation support
- Devanagari display modes
- category/stage-limited practice beyond what is explicitly included in this milestone
- Personal Deck / My Words
- import/export
- API-assisted intake
- cloud sync
- major UI redesign
- advanced analytics or charts

## Proposed issue sequence

1. **Introduce review-ready selection modes and round-source rules**
2. **Implement Lite-Leitner buckets and bucket update logic**
3. **Add mistakes / weak-words practice modes**
4. **Add compact review controls in the UI**
5. **Refine mastery and summary wording for the review-intelligence model**

## Completion criteria

Milestone 3 is complete when:
- the app can choose words from meaningful review-oriented pools
- bucket progression exists and updates from learner performance
- the learner can explicitly practice mistakes / weak words
- the UI exposes the review modes without clutter
- current gameplay remains stable
- the app still feels lightweight and understandable
