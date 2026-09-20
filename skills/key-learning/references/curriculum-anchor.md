# Curriculum anchoring

Read this only when the module gate has opened. It runs once per theme, ever.

## Purpose

Module sequence built from the model's own sense of a field is a guess. Anchoring borrows the scope and sequence from a body that has already had to defend one. What is wanted is the **ordering authority**, not the content: what is taught, in what order, to what stated competency.

## Infer the field first

Read the field from the question, the session context, and any material the learner has supplied. Do not assume a field from an earlier theme. If two fields are genuinely plausible and they would sequence differently, ask in one line and stop; do not search on a guess.

## Source tiers, in order

1. A **certifying, examining, or standards body's** competency framework or published syllabus for the field.
2. The **table of contents of a widely adopted graduate-level textbook or reference handbook**.
3. A **published course outline** from a recognised university department.
4. A **major open courseware index** entry for the subject.

Take the highest tier obtainable within budget. Stop at the first usable result; do not compare sources.

## Budget

One search and at most two fetches, at module-build time only. Never on a plain explanation, never on a due review, never twice for the same theme.

If nothing usable is found inside that budget, stop searching. Write `Tier: none`, build the sequence from first principles, and tell the learner in one line that the sequence is unvalidated.

## Cache it in the theme file

```
## Anchor
Source: <body or work>, <what it is>, <year if stated>
Tier: 1
Units published: <unit names, in the source's own order>
Order used: <the order actually built>
Departures: entered at unit 3 (diagnosed at apply); pulled unit 7 forward
  (the learner's question sits there); dropped unit 9 (credentialing only)
Retrieved: 2026-09-20
```

`Units published` and `Order used` are separate fields on purpose. A single `Sequence` field would let a model-generated order inherit the source's authority, which is the failure this design exists to prevent.

Never re-fetch. Later module builds for the theme rebuild from this cached sequence. Re-anchor only if the learner asks, or if the learner's goal for the theme has changed.

## What the anchor binds

**Coverage binds. Order does not.**

The unit list is a coverage claim. The modules may not silently omit a unit the source names. Dropping one is allowed and is recorded in `Departures` with its reason.

The order is advisory, because a published sequence is built for a cohort starting at zero and this learner is not. Enter at the unit nearest the diagnosed level, and reorder where the learner's original question sits in a unit the source defers. Every reordering is recorded.

Never reproduce the source's wording at length. Take its units and its competency statements; write the objectives fresh.

The recording is the whole mechanism. A reader of the theme file must be able to see which part of the plan came from the source and which part came from the conversation. An anchor that permits silent overrides lends borrowed authority to a model-generated sequence, which is worse than having no anchor at all.

## Judge the anchor out loud

A tier 1 syllabus reflects what is **examined**, which is not always what is most useful. When the anchor is tier 1 and the learner's goal is practical rather than credentialing, say so in one line and record the units reordered or dropped as a result.

A textbook's contents reflect what is **teachable in sequence**, which tends to defer the hardest and most load-bearing ideas. When a deferred unit is the one the learner actually asked about, pull it forward and record the departure.
