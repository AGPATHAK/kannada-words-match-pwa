# Kannada Words Match PWA

Kannada Words Match PWA is a small single-file prototype for beginner Kannada vocabulary practice. It presents 5 Kannada words and 5 English meanings in two columns, lets the learner pair them with tap-to-select matching, gives immediate correct or incorrect feedback, and supports starting a fresh round from the embedded starter dataset without reloading the page.

## v1 Features

- Single-file `index.html` prototype with embedded HTML, CSS, JavaScript, and starter data
- Fixed starter dataset embedded directly in the app
- Exactly 5 random word pairs per round
- Kannada tiles with Devanagari scaffold shown beneath the Kannada text
- English meanings shuffled independently from the Kannada column
- Tap-to-pair interaction with one active Kannada tile and one active English tile at a time
- Correct-match confirmation with locked matched tiles
- Incorrect-match feedback with automatic reset after a short delay
- Round completion detection when all 5 pairs are matched
- New-round control that starts another playable round without page reload

## Out Of Scope In v1

- Scoring
- Progress tracking
- Persistence or `localStorage`
- Category-based word sets
- Audio or pronunciation playback
- Leitner-lite or spaced repetition scheduling
- Multiple game modes
- Backend, accounts, or cloud sync

## Run Locally

1. Clone or download this repository.
2. Open [index.html](/Users/ardhendupathak/Documents/GitHub/kannada-words-match-pwa/index.html) in a browser.

No build step, package install, or local server is required for the current prototype.

## Prototype Note

This Milestone 1 version is intentionally implemented as a single-file prototype. The full app shell, styles, interaction logic, and starter dataset all live in `index.html`.

## Roadmap

Likely next improvements after Milestone 1:

- Transliteration or pronunciation support for beginners who need more reading help
- Category-based word sets instead of a single mixed starter pool
- Progress tracking across rounds
- Leitner-lite or spaced repetition ideas for review scheduling

