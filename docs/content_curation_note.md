# Kannada Words Match PWA — Content Curation Note

## Purpose

Define how the first serious word deck should be chosen so that the app teaches useful vocabulary rather than merely demonstrating gameplay.

## Immediate target

Milestone 2 should use a curated **50-word starter deck**.

This number is a deliberate compromise:
- large enough to make the app useful
- small enough to curate carefully
- manageable for learner testing and iteration
- suitable as the first serious release before broader expansion

## Content philosophy

The app is a beginner vocabulary trainer. Therefore, the initial word set should prioritize usefulness, clarity, and learnability.

The first deck should not aim for completeness. It should aim for instructional quality.

## Selection criteria

Prefer words that are:
- common in everyday life
- visually and semantically concrete
- easy to gloss in one English word or short phrase
- likely to recur in basic Kannada exposure
- suitable for short recognition-based matching practice

## Good starter category split

A practical first-pass category balance for the 50 words is:

| Category | Count | Notes |
|---|---:|---|
| Home | 10 | house, door, room, water-related, object words |
| Family/People | 8 | mother, father, child, friend-like words |
| Nature | 8 | sun, tree, flower, rain-like concrete items |
| Body | 8 | eye, hand, head, leg, ear-like items |
| Food/Daily use | 10 | milk, rice, fruit, salt, cup-like words |
| Concrete verbs | 6 | go, come, eat, drink, see, sit-like high-utility verbs |

This is a planning balance, not yet the final approved list.

## Avoid in the first deck

Avoid words that are:
- abstract
- strongly context-dependent
- difficult to gloss briefly in English
- uncommon in daily use
- too literary for the beginner stage
- highly confusable with other early items

## Why not start with a bigger deck

A weak 200-word deck creates noise, confusion, and low instructional value.

A carefully chosen 50-word deck is more useful because:
- learners get repeated exposure sooner
- mistakes become more interpretable
- review logic can be tested on cleaner content
- the product can evolve on a stronger foundation

## Future content bands

Later, the vocabulary can expand into bands such as:
- core daily-use
- extended everyday
- intermediate/contextual
- literary/cultural

Milestone 2 does not need to operationalize all of these bands, but it should avoid mixing them carelessly.

## Introduction strategy

The app should eventually avoid fully random exposure across the entire corpus.

A better long-term strategy is:
- start with core daily-use words
- introduce new words in controlled batches
- recycle weak or missed items more often
- reduce the frequency of stable items without removing them entirely

Milestone 2 does not need to implement this logic fully, but the deck and schema should support it.

## Required production process before deck integration

Before coding the 50-word deck, prepare a candidate list and review it for:
- ambiguity
- overlap
- beginner relevance
- category balance
- clarity of English meanings
- redundancy across near-synonyms
- whether verbs are concrete enough for matching gameplay

## Required artifact

Milestone 2 deck work should not begin until there is a separate reviewed artifact containing:
- all 50 candidate items
- category assignment
- proposed English gloss
- notes on any ambiguity or substitution risk

## Ownership note

Deck curation is not an implementation side task. It is a blocking product/content deliverable.
