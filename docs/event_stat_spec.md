# Kannada Words Match PWA — Event and Stats Specification

## Purpose

Define what should be counted, what should be persisted, and what can remain temporary during Milestone 2.

## Design rule

Persist **aggregate stats**, not a large raw event history.

Use temporary in-memory event objects only when they help generate session summaries or simplify round logic.

## Persistent aggregate stats

Per item:
- `seen`
- `correct`
- `incorrect`
- `streak`
- `bucket`
- `last_reviewed`

Per session or app meta:
- `last_session_at`
- `session_count`

## Optional in-memory event shape

If temporary event objects are useful during a live session, use a simple shape like:

```json
{
  "type": "incorrect_match",
  "word_id": "mane",
  "timestamp": "2026-04-14T10:00:00Z",
  "session_id": "session_2026_04_14_001"
}
```

## Recommended event types

- `item_shown`
- `correct_match`
- `incorrect_match`
- `round_complete`
- `session_complete`

## Counting rules

### `seen`
Increment when the item appears in a round.

### `correct`
Increment when the learner makes a correct final match for that item.

### `incorrect`
Increment when the learner attempts a wrong match involving that item.

### `streak`
Increment on correct resolution of an item; reset on incorrect outcome.

### `last_reviewed`
Update when the item participates in a completed learner interaction for the current session.

## Session summary examples

Milestone 2 summaries can reasonably include:
- rounds completed
- total pairs shown
- correct matches
- incorrect attempts
- items missed most often in the current session

## Non-goal

Milestone 2 does not require a forensic replay log of every learner action across all sessions.
