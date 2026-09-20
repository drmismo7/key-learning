# Ledger integrity and repair

Read this only when the validation check in `SKILL.md` has failed. Do not write to the ledger until the fault is resolved.

## What the check tests on every read

The header line carries `Root`, `Trigger` and `Depth`. Every data line splits into exactly seven pipe-separated fields. No slug appears twice. `last` and `due` parse as dates. `level` is one of the six taxonomy levels. `rung` is an integer from 1 to 6. `miss` is a non-negative integer.

Anything else is a fault. A fault suspends writing, not reading: the explanation still runs, and the learner is told in one line that scheduling is paused.

## Faults and their repairs

**Malformed line.** Repair from the matching theme file, which holds the authoritative record. `Level reached` supplies `level`, the last dated entry in the review log supplies `last`, and the count of log entries supplies `seen`. Recompute `due` from `last` plus the interval at the recorded `rung`. If `rung` is unrecoverable, set it to 1, which schedules an early review rather than losing the theme.

**Duplicate slug.** Keep the line with the later `last` date and delete the other. If both carry the same date, keep the one with the higher `seen`. Never merge two lines by adding their counters.

**Line with no theme file.** The theme was logged but never developed. Keep it. This is the normal state of a theme below the module gate.

**Theme file with no index line.** The line was lost. Rebuild it from the theme file as above and say so.

**Header missing or unreadable.** Restore it with the defaults `Trigger: 1` and `Depth: practitioner`, and tell the learner the dials were reset, because a silently restored dial is worse than a lost one.

**Index unreadable or absent entirely.** Rebuild it from the theme files in `themes/`, one line each. Say how many themes were recovered. Themes that existed only as index lines, having never reached the module gate, are unrecoverable; say that too rather than implying a clean restore.

## After any repair

Report what was wrong and what was changed, in one or two sentences. Never repair silently. A learner who does not know their schedule was rebuilt will trust a due date that was reconstructed rather than recorded.

Resume normal writing only once the check passes.
