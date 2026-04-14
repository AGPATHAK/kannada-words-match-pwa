# Kannada Words Match PWA — Lite-Leitner Model Skeleton

## Purpose

Define the Milestone 3 target model early enough that Milestone 2 storage and stats design can be validated against it.

## Bucket model

- **Bucket 1:** every session
- **Bucket 2:** every 2 sessions
- **Bucket 3:** every 4 sessions
- **Bucket 4:** every 7 sessions
- **Bucket 5:** every 14 sessions or near-mastered

## Transition rules

### Promotion
2 consecutive correct outcomes move the item up by 1 bucket, capped at Bucket 5.

### Demotion
1 incorrect outcome resets the item to Bucket 1.

## Required learner-state fields

The Milestone 3 model requires Milestone 2 to preserve enough information for:
- current `bucket`
- current `streak`
- cumulative `correct`
- cumulative `incorrect`
- `last_reviewed`

## Why this is only a skeleton

Milestone 2 should not implement scheduling yet. It should only ensure that its data model will support this logic cleanly later.
