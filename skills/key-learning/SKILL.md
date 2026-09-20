---
name: key-learning
description: "Use when someone asks how a mechanism actually works, why one method was chosen over another, or what principle underlies something, and on 'teach me', 'walk me through', or 'what is due for review'."
---

# Key Learning

Explain mechanisms from first principles, remember what was asked, build a curriculum only for themes that recur.

## Fire or stay silent

Fire on: how a thing works internally, why one approach is used over another, what principle sits underneath an observation, explicit "teach me" or "review".

Never fire on: task instructions, debugging, factual lookup, or a clarifying question inside a job already underway.

**Hard rule, overriding every dial: stay silent while a multi-step task is in progress.** Answer normally and do not open the ledger.

Test: would a correct answer transfer to a different instance of the same problem? If not, it is ordinary work.

## Dials

Read from the index header, change on request, write back.

`Trigger`: **0** explicit invocation only. **1** mechanism questions outside an active task (default). **2** adds a one-line overdue note after the answer. **3** adds a short drill before the answer.

`Depth`: **novice** defines every term and uses analogy. **practitioner** assumes field vocabulary and goes straight to the derivation (default). **expert** covers only the non-obvious step, the contested part, the boundary. Higher depth means shorter output.

## Ledger

Lives at `learning/` in the working directory, or the path recorded in a prior index header. If none exists, ask once, then record it. With no file tools, explain, say once that nothing is cached, stop.

Read `index.md` and nothing else. Open a theme file only when a review or module build actually runs.

```
Root: learning/ | Trigger: 1 | Depth: practitioner
Ladder: 1, 3, 7, 16, 35, 90

slug | level | seen | last | rung | due | miss
queueing-delay | apply | 3 | 2026-09-20 | 3 | 2026-09-27 | 1
```

Theme files are always `themes/<slug>.md`, so paths are never stored.

Validate on read: header present, seven fields per line, no duplicate slug, dates parseable. On any failure do not write, say in one line that scheduling is paused, and read `references/ledger-repair.md`.

## Diagnose the Bloom level from the question's shape

remember (what is it called), understand (what does it mean), apply (how do I use it here), analyse (why does it change when conditions change), evaluate (is this better, is this sound), create (how would I build one).

Pitch at the diagnosed level and one rung above, never more. At `Depth: expert`, floor the diagnosis at analyse: an expert asking a remember-level question is checking a detail, not regressing.

## Explain

Write as connected prose. A causal chain rendered as bullets loses the causation.

1. **Phenomenon.** One sentence, the jargon of the question stripped out.
2. **Floor.** Name the givens the field does not derive further, and say that they are the givens, so the learner knows where the derivation starts.
3. **Rebuild.** Derive forward one causal step at a time, each step stating what would change if that step were removed. A step whose removal changes nothing is decoration; cut it.
4. **Boundary.** One case where the mechanism weakens, reverses, or stops applying.

Define each technical term at first use. Retire every analogy by naming where it breaks.

## Check, then score

Ask one question, applied rather than recall: change the numbers, invert a constraint, move to an adjacent case. On a wrong answer, repair the single failed step rather than re-explaining the account.

Advance a rung on a pass. On a fail, drop one rung, floor of 1, and increment `miss`. Set `due` to today plus the new interval. Write the index back on every fire so `seen` and `last` stay honest.

Archive on a pass at rung 6: move the line to `archive.md`, never read on fire. A returning archived theme reopens at rung 3.

## Module gate

Build a module set only when one holds: the theme already shows `seen` of 2 or more; the check was failed; the learner asked to be taught the subject rather than asking one question; the mechanism runs past roughly five derivation steps. Otherwise log the theme and stop.

When the gate opens, read `references/curriculum-anchor.md`, then `references/module-design.md`.

## Standing rules

Never assert a figure, date, effect size, or attribution from memory. Take the learner's source, or ask before retrieving one.

Flag a contested or model-dependent claim inside the sentence that makes it, not as a trailing disclaimer. State plainly where reliable knowledge stops.

Voice: a senior colleague showing someone the ropes. Answer first. No filler openers, no praise inflation, no rhetorical questions standing in for explanation. Name where the confusion is reasonable, and dismantle the common misconception rather than routing around it. Follow any writing register the session already holds for this user.

If the session offers a skill that builds quizzes, flashcards, or spaced-repetition artifacts, hand it the module checks rather than building a drill here.
