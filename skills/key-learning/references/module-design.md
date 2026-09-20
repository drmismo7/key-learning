# Module design

Read this only when the module gate has opened, after `curriculum-anchor.md`.

## Rules of construction

Modules start at the diagnosed Bloom level and climb one rung at a time. That climb is a default, not a rule: the revised taxonomy does not claim strict cumulative hierarchy, so departing from it is legitimate and only needs recording. Skip a rung when the learner has already demonstrated the intervening level in conversation. Repeat one when a module has been failed twice. Note either in the review log. See `CREDITS.md` at the plugin root.

Never write more than four modules at once: the later ones are guesses about a learner who will have changed before reaching them.

Each module carries an objective written with a verb from its own level, one line on why that level matters for this theme, and two or three checks. An objective that cannot be checked is not an objective; rewrite it or cut it.

Propose the set before writing it, with one sentence on why the theme earned a plan.

## Verbs by level

| Level | Verbs |
|---|---|
| Remember | define, list, name, recall |
| Understand | explain, paraphrase, classify, summarise |
| Apply | compute, predict, use, carry out |
| Analyse | differentiate, attribute, decompose, compare mechanisms |
| Evaluate | critique, justify, judge against a stated criterion |
| Create | design, derive, construct, propose |

An objective whose verb does not appear at its own level is mislabelled. That is the commonest failure here: a module announced as Analyse whose checks only ask the learner to Understand.

## Theme file

```
# Queueing delay
Status: active
Level reached: apply
Opened: 2026-09-12

## Core mechanism
Three to five sentences. The causal account in compressed form, written
so a reader who has forgotten everything can reload it in one pass.

## First-principles floor
The givens the derivation starts from, three to six lines.

## Anchor
Source: ...
Tier: 2
Units published: ...
Order used: ...
Departures: ...
Retrieved: 2026-09-12

## Modules
### M1 - Apply: predict delay under a stated arrival rate
Why this level: the formula is memorable, the regime it holds in is not.
Checks:
1. ...
2. ...
Status: passed 2026-09-20

### M2 - Analyse: attribute the non-linear rise near capacity
Why this level: ...
Checks:
1. ...
Status: not started

## Review log
2026-09-20 | apply | pass | recovered the saturation case unprompted
```

`Status` per module is `not started`, `in progress`, or `passed YYYY-MM-DD`.

## Re-diagnose as you go

Diagnose again at each module pass rather than trusting the level recorded at the theme's opening. If the learner clears two rungs in one sitting, delete the intervening module instead of making them sit through it, and note the skip in the review log.

If a module is failed twice, the fault is usually the rung below it, not the module. Drop to the prior level and rebuild its checks before re-attempting.

## Writing the checks

A check moves the situation rather than restating it: different numbers, an inverted constraint, an adjacent case, a boundary the learner has not been shown.

Do not restate item-writing craft here. Where the session offers a skill that builds quizzes or flashcards, hand it the module objectives and the anchor competencies and let it write the items, because item-writing rules belong to that skill and duplicating them guarantees the two copies will drift apart. Where no such skill is present, put the checks to the learner conversationally, one at a time.

Where the theme has an anchor, at least one check per module should map to a competency the anchor names, so that passing the module means something outside this conversation.
