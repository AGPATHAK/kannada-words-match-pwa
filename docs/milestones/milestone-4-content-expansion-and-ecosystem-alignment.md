# Milestone 4 — Content Expansion and Ecosystem Alignment

## Purpose

Expand the curated deck beyond the first 50 words while keeping the app a focused trainer rather than a random-word game.

Milestone 3 established:
- review-ready round selection
- Lite-Leitner buckets
- mistakes / weak-words practice modes
- refined review controls
- clearer mastery and summary semantics

Milestone 4 should build on that by increasing useful vocabulary depth in a disciplined way and aligning the expanded content model with the broader Kannada app ecosystem.

## Milestone goal

Expand the deck from 50 to 100 curated words, introduce them in a staged and controlled way, and keep the active learning pool manageable and trainer-like.

## Agreed design decisions

- Next target deck size: **100 words**
- Long-term soft ceiling before rethinking the model: **150–200 words**
- New words should be introduced in **small staged batches**, not all at once
- Round composition should remain **review-heavy**, with only a small number of new words entering the mix
- The next 50 words should remain focused on **high-frequency everyday vocabulary**
- The expansion should remain **mostly noun-based**, with only a few very high-utility verbs if they remain clean and unambiguous
- Stage progression should initially be **quiet/background introduction**, not a heavy explicit unlock ceremony
- Personal deck support remains deferred until the curated 100-word experience works well

## Guiding principles

- Keep the app as a single self-contained HTML file.
- Preserve learner clarity over vocabulary breadth.
- Prefer staged introduction over flat expansion.
- Keep review signals stronger than novelty signals.
- Avoid turning the app into a dictionary-style random word game.
- Keep content curation deliberate and inspectable.

## In scope

- expand the curated deck from 50 to 100 words
- define the next 50 words in a clean and reviewable way
- preserve or extend stage metadata for controlled introduction
- introduce active-pool rules for mixing new, review, and weak words
- align content and stat conventions with the broader Kannada learning suite where useful
- make small supporting UI changes only if needed for the new content flow

## Out of scope

- Personal Deck / My Words implementation
- API-assisted intake
- import/export
- audio or pronunciation support
- Devanagari display modes
- major UI redesign
- PWA packaging and iPhone installability work
- cloud sync or backend features

## Proposed issue sequence

1. **Define the 51–100 curated word set and supporting schema decisions**
2. **Integrate the expanded 100-word deck into the app**
3. **Implement staged introduction rules for new words**
4. **Implement active-pool composition rules for new vs review vs weak words**
5. **Align content/stats conventions with the broader Kannada suite and clean up wording if needed**

## Completion criteria

Milestone 4 is complete when:
- the app uses a curated 100-word deck
- the next 50 words are integrated coherently
- new words enter the app in controlled batches
- the active round mix remains review-heavy and manageable
- the app still feels like a trainer rather than a random vocabulary game
- the content model is cleaner and better aligned with the broader Kannada suite
