# Kannada Words Match PWA — Deck Schema Note

## Purpose

Define a lightweight word-item schema that supports the current app while leaving room for future review logic, curation, and category-based growth.

## Design goals

The schema should:
- remain simple enough for a lightweight PWA
- support a curated 50-word starter deck
- preserve Devanagari scaffold support
- allow future categorization and progression
- align with the planned Lite-Leitner learner-state model
- avoid field names with overlapping semantics

## Recommended item structure

Each word item should include at least the following fields:

```json
{
  "id": "mane",
  "kannada": "ಮನೆ",
  "devanagari": "मने",
  "english": "house",
  "category": "home",
  "difficulty_band": "core",
  "intro_stage": 1,
  "tags": ["daily-use", "noun"]
}
```

## Field definitions

### `id`
A stable internal identifier.

Requirements:
- unique within the deck
- short and readable
- should not change once released, because performance history may depend on it

### `kannada`
The Kannada-script display form.

Requirements:
- primary learner-facing script
- must be clean and canonical

### `devanagari`
The Devanagari scaffold for beginner support.

Requirements:
- present in Milestone 2
- used only as support text, not as primary display

### `english`
The English meaning used in matching.

Requirements:
- concise
- low ambiguity where possible
- pedagogically appropriate for beginner learners

### `category`
A broad semantic grouping.

Examples:
- home
- food
- family
- body
- nature
- places
- objects
- verbs

Purpose:
- supports content balancing
- enables later category-based progression if needed

### `difficulty_band`
A static content-band classification.

Suggested values:
- `core`
- `extended`
- `intermediate`

Definition:
This describes how inherently basic or advanced the vocabulary item is in the curriculum. It does **not** describe the learner's current mastery.

### `intro_stage`
A static introduction marker.

Examples:
- `1` = first learner-visible batch
- `2` = second batch
- `3` = later batch

Definition:
This describes **when** the word becomes eligible to enter the learner's practice universe. It does **not** describe difficulty and does **not** describe mastery.

### `tags`
Optional freeform descriptors.

Examples:
- `daily-use`
- `noun`
- `home`
- `concrete`

Purpose:
- helps future filtering and analysis without changing the main schema

## Explicit distinction: content fields vs learner-state fields

### Static content fields
These belong to the deck item itself:
- `category`
- `difficulty_band`
- `intro_stage`
- `tags`

### Dynamic learner-state fields
These do **not** belong in the deck item definition. They belong in learner progress storage:
- `bucket`
- `seen`
- `correct`
- `incorrect`
- `streak`
- `last_reviewed`

This separation keeps the deck clean and prevents schema confusion later.

## Suggested content rules for the first 50 words

The starter deck should favor:
- concrete words
- low ambiguity
- high daily utility
- beginner accessibility
- clean one-to-one English meanings where possible

Avoid for now:
- abstract terms
- heavily polysemous words
- culturally dense literary vocabulary
- meanings that require long explanations

## Future-compatible learner-state model to design against

Milestone 3 will introduce a bucket-based review model.

Target skeleton:
- 5 buckets
- promotion after 2 consecutive correct outcomes
- demotion to Bucket 1 after 1 incorrect outcome

Therefore Milestone 2 storage should be compatible with at least:

```json
{
  "seen": 12,
  "correct": 10,
  "incorrect": 2,
  "streak": 3,
  "bucket": 1,
  "last_reviewed": "2026-04-14T10:00:00Z"
}
```

## Recommendation

Keep the actual deck schema modest in Milestone 2, but choose field names now that will not need to be renamed later.
