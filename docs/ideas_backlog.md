# Ideas Backlog — Kannada Words Match PWA

This document is a parking lot for later ideas that are promising but intentionally kept out of the active milestone scope.

---

## 1. Personal Deck / My Words

### Summary
Allow the learner to add new words encountered elsewhere and practice them within the app.

### Why it is valuable
The learner may discover useful words from:
- books
- conversations
- classes
- other Kannada apps
- real-world exposure

This feature would let the app become not only a curated trainer, but also a personal vocabulary companion.

### Recommended product framing
Do **not** frame this as a “dictionary.”

Better labels:
- My Words
- Personal Deck
- Add a Word
- Words I’m Learning

### Recommended architecture
Keep two deck sources:

#### Core deck
- curated
- shipped with the app
- stable and reviewable

#### Personal deck
- user-added
- stored locally
- editable later

At runtime, allow practice source choices:
- core only
- personal only
- mixed

### Likely fields for a user-added word
- Kannada
- Devanagari scaffold
- English meaning
- category
- optional note
- optional tag(s)

### Guardrails to consider
- duplicate detection
- required-field validation
- normalization of IDs
- keep newly added words out of the main pool until explicitly enabled
- allow delete/edit later

### Risks
- inconsistent gloss quality
- inconsistent Devanagari scaffolds
- duplicate entries
- too many hard words entering the review pool too quickly
- noisy learner stats

### Recommended timing
After Milestone 3, once the core trainer, persistence, and review logic are stable.

---

## 2. Scaffold fade / hide options

### Summary
Let Devanagari support fade out or be hidden once a learner becomes stronger on a word set.

### Status
Deferred. Not needed for Milestone 2.

---

## 3. Confusable-set aware round generation

### Summary
Avoid placing too many highly similar words in the same early round.

### Examples
- maga / magalu / magu
- anna / akka
- kai / kaalu / kannu / kivi

### Status
Useful for early implementation planning. Could be introduced during Milestone 2 or 3, depending on issue scope.

---

## 4. Category-based practice modes

### Summary
Allow practice by semantic category such as home, family, body, nature, food.

### Status
Deferred.

---

## 5. Audio support

### Summary
Add pronunciation support for selected words.

### Status
Deferred.

---

## 6. Import / export personal vocabulary

### Summary
Allow backing up or moving personal words and learner progress.

### Status
Deferred until after local personal deck exists.
