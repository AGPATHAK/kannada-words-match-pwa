# Kannada Words Match PWA

Kannada Words Match PWA is a lightweight single-file trainer for beginner Kannada vocabulary practice. It presents 5 Kannada words and 5 English meanings in two columns, lets the learner pair them with tap-to-select matching, gives immediate correct or incorrect feedback, and supports starting a fresh round from the embedded curated 50-word deck without reloading the page.

## v1 Features

- Single-file `index.html` app with embedded HTML, CSS, JavaScript, and curated deck data
- Finalized curated 50-word beginner deck embedded directly in the app
- Exactly 5 random word pairs per round
- Kannada tiles with Devanagari scaffold shown beneath the Kannada text
- English meanings shuffled independently from the Kannada column during active play
- Tap-to-pair interaction with one active Kannada tile and one active English tile at a time
- Correct-match confirmation with locked matched tiles
- Incorrect-match feedback with automatic reset after a short delay
- Round completion detection when all 5 pairs are matched
- End-of-round English realignment so Kannada and English pairs line up visually after round completion
- New-round control that starts another playable round without page reload
- Internal logical refactor inside the single-file architecture to prepare for later persistence and stats work

## Out Of Scope In v1

- Progress tracking and learner stats
- Persistence or `localStorage`
- Category- or stage-limited practice modes
- Devanagari display modes
- Audio or pronunciation playback
- Leitner-lite or spaced repetition scheduling
- Personal Deck / My Words support
- Backend, accounts, or cloud sync

## Run Locally

1. Clone or download this repository.
2. Open [index.html](/Users/ardhendupathak/Documents/GitHub/kannada-words-match-pwa/index.html) in a browser.

No build step, package install, or local server is required for the current prototype.

## Prototype Note

The current app remains intentionally implemented as a single-file web app. The full app shell, styles, interaction logic, and curated deck all live in `index.html`. Recent work has improved the internal logical structure while preserving the single-file design philosophy used across the broader Kannada app ecosystem.

## Roadmap

Planned next directions after the current curated-deck baseline:

- versioned localStorage persistence and learner stats
- lightweight session summary
- Lite-Leitner-style review logic in a later milestone
- Devanagari display modes: always on / tap to reveal / always off
- category- and stage-limited practice
- Personal Deck / My Words as a later product direction

## Ideas parked for later

- API-assisted vocabulary intake through a helper workflow
- import / export workflows for learner-added vocabulary
- optional pronunciation support
