# Kannada Words Match PWA — Roadmap (Updated)

## Current baseline

This roadmap assumes that **Milestone 1 already exists** as the delivered prototype:
- single-file PWA
- 5-pair matching rounds
- embedded starter data
- Devanagari scaffold
- no persistence, no review scheduling, no personal-word entry

The roadmap below describes the next development streams from that baseline.

---

## Stream A — Prototype to learning module

### Goal
Turn the current match game into a credible daily-use beginner vocabulary trainer while preserving the lightweight, inspectable design philosophy of the wider Kannada app ecosystem.

### Outcomes
- keep the app as a **single self-contained HTML file** by default
- perform a **logical refactor**, not necessarily a physical multi-file split
- freeze a curated 50-word starter deck
- add local persistence
- add aggregate learner stats
- add event capture needed for session summaries
- preserve the Devanagari scaffold
- prepare the data model for later Lite-Leitner scheduling

### Milestone alignment
This stream corresponds to **Milestone 2: Learning-ready foundation**

---

## Stream B — Learning science under the hood

### Goal
Introduce memory support without overcomplicating the app.

### Outcomes
- Lite-Leitner style review buckets
- mistakes-first review support
- new vs review balancing
- simple learner-state progression
- session-based review cadence

### Milestone alignment
This stream corresponds to **Milestone 3: Review intelligence**

---

## Stream C — Ecosystem alignment

### Goal
Make this app behave like a true module in the broader Kannada learning suite.

### Outcomes
- align stats language and session vocabulary with other Kannada apps
- align localStorage conventions where practical
- harmonize UX patterns
- make future cross-app analysis possible
- reduce accidental divergence from the single-file PWA pattern

### Milestone alignment
This becomes the next integration-focused milestone after Milestone 3.

---

## Stream D — Content growth and pedagogy refinement

### Goal
Expand content depth without losing simplicity.

### Outcomes
- extend beyond the first 50 words
- introduce additional intro stages
- expand categories in a controlled way
- optionally introduce difficulty tiers beyond `core`
- add rules for confusable-word handling in early rounds
- later consider scaffold controls or fade logic

---

## Stream E — Learner-owned vocabulary

### Goal
Let the app support words the learner encounters elsewhere, without weakening the curated core deck.

### Feature direction
**Personal Deck / My Words**

### Purpose
Allow the learner to add words discovered from books, conversations, classes, or other apps, then practice them inside the same trainer.

### Recommended design
- keep the shipped **core deck** separate
- store user-added words in a **personal local deck**
- allow practice modes such as:
  - core only
  - personal only
  - mixed
- keep learner stats separate but compatible across both decks

### Why this is deferred
This is valuable, but it adds:
- a second content pipeline
- duplicate and normalization concerns
- new UI for add/edit/delete
- quality-control issues for glosses and scaffolds

So it should be implemented **after the core trainer loop is stable**.

### Suggested timing
After Milestone 3, or in a later expansion milestone.

---

## Stream F — Optional enrichment

### Goal
Add only features that clearly improve learning.

### Possible additions
- audio support
- richer dashboards
- export/import or backup
- optional category-based filtering
- advanced review settings

---

## Current milestone sequence

### Milestone 1 — Prototype
Delivered already.

### Milestone 2 — Learning-ready foundation
- single-file logical refactor
- 50-word curated deck
- local persistence
- stats and event capture
- session summary
- schema/version groundwork

### Milestone 3 — Review intelligence
- Lite-Leitner buckets
- review cadence
- mistakes-focused practice
- basic mastery logic

### Milestone 4 — Ecosystem convergence / expansion
- alignment with the broader Kannada suite
- content growth
- possible personal deck groundwork

### Milestone 5+ — Later extensions
- personal deck / My Words
- optional enrichment features
- deeper pedagogy refinements

---

## Roadmap guardrails

- Do not break the single-file ecosystem pattern casually.
- Do not add heavy architecture before the trainer proves useful.
- Do not add user-entered vocabulary before the curated loop is stable.
- Keep learner state out of the deck itself.
- Treat content curation as a first-class dependency, not an afterthought.
