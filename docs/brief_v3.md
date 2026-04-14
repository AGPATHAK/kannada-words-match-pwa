# Kannada Words Match PWA — Brief v3.1

## 1. Problem

A beginner learner of Kannada needs a low-friction way to build recognition of common Kannada words through repeated exposure and active recall. The current prototype proves the matching mechanic, but it does not yet support structured vocabulary growth, persistence, or scientifically grounded review.

The next version should turn the prototype into a lightweight but serious vocabulary-learning module within a broader Kannada learning ecosystem.

## 2. Target user

A beginner Kannada learner who benefits from script support and short daily practice sessions, and who is gradually moving from recognition to retention.

This version is not aimed at advanced learners.

## 3. Product concept

Build a lightweight PWA that uses a word-matching interaction to strengthen Kannada vocabulary recognition and retention.

The visible interaction remains simple: match Kannada words to English meanings.

Underneath, the app begins to behave like a real trainer through:
- local persistence
- aggregated performance tracking
- error-aware review preparation
- later support for Lite-Leitner scheduling

## 4. Product role in the ecosystem

This app is not a standalone game. It is one vocabulary-focused module within a broader Kannada learning ecosystem that already includes other trainers and is moving toward more scientifically grounded practice design.

This app should therefore evolve in conceptual alignment with those tools rather than as an isolated novelty product.

## 5. Core design philosophy

- Keep the surface interaction simple.
- Keep the implementation lightweight and inspectable.
- Preserve the broader suite's low-ceremony hosting model.
- Add learning science under the hood only where it clearly improves retention.
- Prefer local-first design.
- Avoid feature bloat.
- Keep the Devanagari scaffold for now as a beginner support layer.
- Refactor only enough to support clean future growth.

## 6. Architecture decision for Milestone 2

The broader Kannada PWA suite favors **single self-contained HTML files**, because they are easy to host on GitHub Pages, easy to inspect, and easy to edit directly.

Milestone 2 should therefore use a **logical refactor by default**, not an automatic multi-file split.

Preferred pattern inside one HTML file:
- `Deck` module or namespace
- `Storage` module or namespace
- `State` module or namespace
- `Engine` module or namespace
- `UI` module or namespace

A physical split into multiple files is allowed later, but only as an explicit documented decision, because it would diverge from the existing ecosystem pattern.

## 7. Success criteria for the next stage

The next stage is successful if:
- the app remains simple and pleasant to use
- the code becomes easier to evolve through a disciplined logical refactor
- the app supports a curated 50-word starter deck
- learner performance persists locally across sessions
- incorrect attempts and item-level performance can be tracked
- each session produces meaningful learner feedback
- the app is genuinely ready for Lite-Leitner implementation in the next milestone
- the Devanagari scaffold remains available without displacing Kannada as the primary script

## 8. Scope for Milestone 2

### Included
- Logical refactor of the current app structure while preserving single-file friendliness by default.
- Replace the embedded starter list with a curated 50-word deck.
- Define a richer item schema.
- Define localStorage schema and schema versioning before implementation.
- Add local persistence.
- Add session-level statistics.
- Add aggregated event/error tracking.
- Retain the current core tap-to-pair interaction.
- Retain round-based play.
- Keep mobile-friendly simplicity.

### Excluded
- Full spaced repetition scheduler.
- Audio.
- Cloud sync.
- Account system.
- Advanced dashboards.
- Multiple game modes.
- Large content-management workflows.
- Literary or advanced vocabulary sets.
- Cross-app integration logic beyond basic conceptual alignment.
- Full per-event historical logging if aggregate stats are sufficient.

## 9. Content strategy

The first serious release should use **50 carefully chosen core daily-use words**.

### Why 50
- Enough breadth to make the app useful.
- Still small enough to curate carefully.
- Manageable for testing instructional quality.
- Suitable for later staged expansion.

### Selection principles
The 50 words should favor:
- common concrete nouns and a few concrete high-frequency verbs
- common daily-use words
- low ambiguity
- high everyday utility
- beginner accessibility

Later expansions can separate vocabulary into bands such as:
- core daily-use
- extended everyday
- intermediate/contextual
- literary/cultural

## 10. Item schema

Each word item should be structured to support later growth.

Suggested fields:
- `id`
- `kannada`
- `devanagari`
- `english`
- `category`
- `difficulty_band`
- `intro_stage`
- optional `tags`

These names are chosen to avoid overlap with future learner-state fields.

## 11. Working definitions

### `difficulty_band`
A **static content classification** describing the inherent level or breadth of the vocabulary item, such as `core`, `extended`, or `intermediate`.

### `intro_stage`
A **static rollout marker** describing when a word becomes eligible to enter the learner's practice pool, such as stage 1, 2, 3, and so on.

### `bucket`
A **dynamic learner-state value** introduced in Milestone 3, describing the learner's current review level for that item.

These three concepts must remain separate.

## 12. Lite-Leitner target model for Milestone 3

Milestone 2 should not yet implement full Lite-Leitner scheduling, but its data design must explicitly support the following target model:

- 5 buckets.
- Bucket 1 reviewed every session.
- Bucket 2 reviewed every 2 sessions.
- Bucket 3 reviewed every 4 sessions.
- Bucket 4 reviewed every 7 sessions.
- Bucket 5 reviewed every 14 sessions or considered near-mastered.
- Promotion: 2 consecutive correct outcomes move an item up one bucket.
- Demotion: 1 incorrect outcome resets an item to Bucket 1.

Milestone 2 must store enough learner-state information for this to be implemented cleanly later.

## 13. Persistence model for Milestone 2

Milestone 2 should use versioned localStorage with clearly named top-level keys.

Recommended top-level keys:
- `kannada_match_meta`
- `kannada_match_stats`
- `kannada_match_settings`

The persistence model should prefer **aggregate per-item stats** rather than an ever-growing raw event history.

## 14. Event/stat model for Milestone 2

Milestone 2 should define data shapes before coding.

The default recommendation is:
- per-item aggregate counters for long-term persistence
- lightweight per-session in-memory event objects only if needed for summary generation

This avoids localStorage bloat while still supporting meaningful learner feedback.

## 15. Interaction model

Keep the existing tap-to-pair model.

Reasons:
- lighter than drag-and-drop
- more reliable on mobile
- easier to maintain
- better aligned with low-friction beginner practice

## 16. Non-goals

This version is not intended to:
- teach grammar
- teach sentence comprehension
- replace the sentence or alphabet trainers
- become a large vocabulary database
- optimize for advanced learners
- become a feature-heavy educational platform

## 17. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Weak curation makes the 50-word deck feel arbitrary | Freeze and review a candidate list before coding deck integration |
| Learners over-rely on Devanagari | Keep scaffold always visible in Milestone 2, but design later optional fade/hide rules after review data exists |
| Logging becomes noisy or bloated | Prefer aggregate per-item stats over large persistent raw event logs |
| Refactor invites scope creep | Restrict Milestone 2 refactor to logical modularization, not UI reinvention or major gameplay change |
| Premature learning science harms simplicity | Freeze Milestone 3 model now, but implement only data foundations in Milestone 2 |
| Future schema changes break stored data | Add `schema_version` and migration guard on load |

## 18. Milestone anchor

**Milestone 2: Learning-ready foundation**

A logical refactor plus a curated 50-word deck, versioned local persistence, aggregate learner stats, and session summary, while preserving the current matching interaction and Devanagari scaffold.
