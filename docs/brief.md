# Kannada Words Match PWA — Brief v2

## 1. Problem

A beginner learning Kannada needs a simple and low-friction way to build recognition of common Kannada words and their English meanings. Existing learning approaches can be too broad, too text-heavy, or too feature-rich for quick daily practice. A lightweight word-matching game can provide focused exposure and repetition without cognitive overload.

## 2. Target user

A beginner learner of Kannada who is starting to visually engage with Kannada script and wants to improve recognition of common words through short, repeatable practice rounds.

## 3. Product concept

Build a very simple single-page PWA that presents 5 Kannada word tiles and 5 English meaning tiles in two columns. The learner matches each English meaning to the correct Kannada word using a tap-to-pair interaction. Correct matches receive immediate visual feedback and lock in place.

## 4. Success criteria

The first version is successful if:

- the app loads cleanly as a single-page web app
- one round consists of exactly 5 Kannada words and 5 English meaning tiles
- the English meanings are shuffled relative to the Kannada words
- the learner can pair meanings with words through a simple tap-to-pair interaction
- correct matches are clearly indicated visually and become unclickable
- incorrect matches are clearly indicated, then reset automatically
- the round can be completed without confusion or ambiguity
- the app works well on both desktop and mobile browser
- the implementation remains simple, readable, and contained in a single file

## 5. Scope for v1

Included in scope:

- single-file HTML/CSS/JavaScript implementation
- fixed round size of 5 word pairs
- mixed bag drawn from a fixed starter dataset
- Kannada word on one side and English meaning on the other
- Devanagari support text shown under each Kannada word as a beginner scaffold
- tap-to-pair interaction
- immediate visual feedback for correct and incorrect matches
- replay or new-round control

Explicitly out of scope for v1:

- Latin transliteration
- pronunciation or audio
- category-based grouping
- progress tracking across rounds or sessions
- scoring history
- spaced repetition or Leitner-lite scheduling
- login, backend, or cloud sync
- large content management workflows
- multiple game modes

## 6. Non-goals

This version is not intended to:

- teach grammar
- teach sentence formation
- measure long-term mastery
- provide a complete Kannada curriculum
- optimize for advanced learners

## 7. Interaction model

Preferred interaction model: simple tap-to-pair selection rather than drag-and-drop.

Reason:

- easier on mobile
- simpler to implement and debug
- lower UI friction for first version

Expected behavior:

- the learner taps one Kannada tile and one English tile to form a proposed pair
- if the match is correct, both tiles turn soft green, show a confirmed matched state, and become locked for the rest of the round
- if the match is incorrect, both selected tiles flash a soft error state and then clear automatically after a brief delay of about 800 milliseconds
- after an incorrect match reset, the learner can immediately try again
- only unmatched tiles remain interactive

## 8. Content model

### 8.1 Starter dataset

The app will ship with a fixed starter dataset embedded directly in the JavaScript as an array of objects. The first version should use a small set of common, concrete, and relatively unambiguous words so that gameplay tests recognition rather than vocabulary ambiguity.

Recommended starter dataset:

| Kannada | Devanagari scaffold | English |
|---|---|---|
| ಮನೆ | मने | house |
| ನೀರು | नीरु | water |
| ಪುಸ್ತಕ | पुस्तक | book |
| ಶಾಲೆ | शाळे | school |
| ಹೂವು | हूवु | flower |
| ಹಣ್ಣು | हण्णु | fruit |
| ಊಟ | ऊट | food |
| ಸೂರ್ಯ | सूर्य | sun |
| ಚಂದ್ರ | चंद्र | moon |
| ಮಗು | मगु | child |
| ಹಾಲು | हालु | milk |
| ಬಾಗಿಲು | बागिलु | door |
| ಕಿಟಕಿ | किटकि | window |
| ರಸ್ತೆ | रस्ते | road |
| ಬೆಕ್ಕು | बेक्कु | cat |
| ನಾಯಿ | नायी | dog |
| ಮರ | मर | tree |
| ಕೈ | कै | hand |
| ಕಣ್ಣು | कण्णु | eye |
| ಕಿವಿ | किवि | ear |

### 8.2 Why Devanagari is included

The Kannada tile will display the Kannada word as the primary text and a smaller Devanagari scaffold beneath it. This is intentional. It makes the first version more accessible to a beginner learner who can use Devanagari as a pronunciation support layer while still visually engaging with Kannada script as the primary target.

### 8.3 Round behavior

- one round selects 5 pairs from the starter dataset at random
- the Kannada column remains in one stable order for the full duration of that round
- the English meanings are shown in a separately shuffled order
- the stable Kannada column is intentional: it gives positional anchoring during the round so the learner is not forced to re-scan both columns after every attempt

## 9. UI and state decisions

The brief does not require a complex architecture section, but the following implementation decisions are fixed because they affect interaction clarity:

- the app will maintain a simple in-memory state object
- the state should track the currently selected Kannada tile, the currently selected English tile, and the set of matched pair IDs
- UI updates should be driven from that state rather than from ad hoc DOM mutations alone
- matched tiles must have a visually distinct locked state
- incorrect attempts must reset automatically after the feedback interval

## 10. Constraints

- keep implementation in a single file
- keep UI minimal and aesthetically clean
- keep first version mobile-friendly
- avoid unnecessary dependencies
- avoid feature creep inside the first issue
- prioritize clarity and reliability over polish-heavy interaction
- keep the dataset embedded locally in the file for v1

## 11. First milestone

Deliver a working prototype where a learner can complete one round of 5 Kannada-English matches with immediate feedback and replay or generate another round from the embedded starter dataset.

## 12. Risks and assumptions

Assumptions:

- learner benefits from recognition-based exposure at this early stage
- Devanagari support improves accessibility without replacing Kannada as the primary script
- a mixed bag of common concrete words is acceptable for the first prototype
- a small fixed round size keeps the experience manageable

Risks:

- some learners may depend too much on the Devanagari scaffold
- poor visual design could make tile selection confusing
- touch feedback may feel weak if the selected state is not clearly visible
- ambiguous or overly similar meanings in future expanded word sets could weaken gameplay quality

## 13. First GitHub issue anchor

The first implementation issue should be framed roughly as:

**Build a single-file Kannada word matching PWA with 5 random pairs per round, tap-to-pair interaction, Devanagari scaffold under Kannada words, clear correct/incorrect feedback, and replay/new-round support.**

That issue should include acceptance criteria for:

- rendering 5 Kannada tiles and 5 English tiles
- random pair selection from the starter dataset
- separate shuffling of English meanings
- correct match lock behavior
- incorrect match feedback and timed reset
- round completion behavior
- replay or new-round behavior
