# Kannada Words Match PWA — localStorage Schema v1

## Purpose

Define the localStorage keys, data shapes, and migration guard for Milestone 2 before persistence code is written.

## Top-level keys

### `kannada_match_meta`
Stores schema and app-level metadata.

```json
{
  "schema_version": 1,
  "last_session_at": "2026-04-14T10:00:00Z",
  "session_count": 4
}
```

### `kannada_match_settings`
Stores user preferences.

```json
{
  "show_devanagari": true
}
```

### `kannada_match_stats`
Stores aggregated learner-state objects keyed by `word_id`.

```json
{
  "mane": {
    "seen": 12,
    "correct": 10,
    "incorrect": 2,
    "streak": 3,
    "bucket": 1,
    "last_reviewed": "2026-04-14T10:00:00Z"
  },
  "neeru": {
    "seen": 8,
    "correct": 6,
    "incorrect": 2,
    "streak": 1,
    "bucket": 1,
    "last_reviewed": "2026-04-14T10:00:00Z"
  }
}
```

## Versioning rule

`schema_version` must be checked on load.

If data is missing, malformed, or from an unsupported version, the app should:
- fall back safely to defaults
- optionally migrate known older versions
- avoid crashing on startup

## Why aggregate stats are preferred

Milestone 2 should avoid storing a large persistent event history.

Aggregate per-item stats are preferred because they:
- keep storage compact
- are sufficient for Milestone 2 summaries
- support Milestone 3 bucket logic
- reduce migration complexity

## Minimum required stat fields per item

- `seen`
- `correct`
- `incorrect`
- `streak`
- `bucket`
- `last_reviewed`

## Notes

- `bucket` is future-facing in Milestone 2 and may remain `1` for all items until Milestone 3 logic is implemented.
- Additional fields can be added later through versioned migration.
