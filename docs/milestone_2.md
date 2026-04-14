# Milestone 2 — Learning-Ready Foundation

## Purpose

Convert the current prototype into a lightweight but credible vocabulary-learning module that is ready for daily use and properly prepared for Milestone 3 Lite-Leitner logic.

## Why this milestone matters

The current app proves the interaction model, but it is still a prototype. This milestone creates the data and structural foundation required for future scientific learning support without making the app heavy or overengineered.

## Core milestone decision

Milestone 2 should prefer a **logical refactor inside the current single-file PWA pattern**.

That means:
- clearer internal module boundaries
- cleaner state management
- defined storage and stats formats
- no mandatory build step
- no unnecessary divergence from the rest of the Kannada app suite

A physical split into multiple files is not the default deliverable for this milestone.

## Milestone outcomes

By the end of this milestone, the app should:
- use a logically refactored internal code structure
- support a curated 50-word deck
- persist learner progress locally
- use a versioned localStorage schema
- track core learner stats in aggregate form
- provide a basic session summary
- preserve the existing matching interaction and Devanagari scaffold
- be structurally ready for later Lite-Leitner scheduling logic

## Included scope

### 1. Logical refactor
Restructure the code into clearly separated logical modules or namespaces such as:
- `Deck`
- `Storage`
- `State`
- `Engine`
- `UI`

### 2. Curated 50-word deck
Replace the embedded prototype list with a curated 50-word deck based on core daily-use vocabulary.

### 3. Word metadata structure
Move from a minimal item object to a richer item structure that supports future progression and review.

### 4. localStorage schema
Define before implementation:
- key names
- object shapes
- `schema_version`
- migration behavior for stale or missing data

### 5. Aggregate learner stats
Persist per-item learner stats such as:
- `seen`
- `correct`
- `incorrect`
- `streak`
- `bucket` placeholder or future-compatible field
- `last_reviewed`

### 6. Session summary
Provide a lightweight end-of-session or round summary that helps the learner reflect on performance.

### 7. Lightweight event objects if needed
Use short-lived in-memory event objects only where they improve summary generation or debugging. Do not default to a large persistent event history.

## Explicit exclusions

This milestone should not include:
- full Lite-Leitner scheduling
- audio support
- account system
- cloud sync
- large dashboards
- multiple game modes
- complex content management features
- advanced curriculum logic
- raw persistent event history unless a strong reason emerges

## Constraints

- Keep the app local-first.
- Keep the UI simple and beginner-friendly.
- Preserve the tap-to-pair interaction.
- Preserve the Devanagari scaffold.
- Do not over-architect.
- Do not silently diverge from the suite's single-file philosophy.
- Refactor only as much as needed for clean future growth.

## Acceptance standard

Milestone 2 is complete when:
- the refactored app behaves at least as reliably as the current prototype
- the 50-word deck is integrated and functional
- local persistence is working
- schema versioning is implemented
- aggregate learner stats are working
- session summary is visible and meaningful
- the codebase is clearly easier to extend into Milestone 3

## Dependencies that must be frozen before implementation issues begin

- architecture note
- Lite-Leitner skeleton
- localStorage schema
- aggregate stats format
- candidate 50-word list
- clarified schema field names and definitions

## Suggested issue groups

### Group A — Logical refactor and preserve behavior
Refactor the current code into clear modules without changing core gameplay.

### Group B — Deck and schema
Add the curated 50-word deck and richer item structure.

### Group C — Storage and migration
Implement versioned local persistence.

### Group D — Stats and session summary
Add aggregate learner stats and learner-facing session summary.

### Group E — Readiness review
Validate that the app is genuinely ready for Milestone 3 logic.

## Definition of success

The milestone succeeds if the app still feels simple on the surface but becomes meaningfully stronger underneath, without losing the ecosystem's low-maintenance design discipline.
