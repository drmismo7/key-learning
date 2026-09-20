# Credits and provenance

## Frameworks this skill uses

**Bloom's taxonomy.** The six level names used here (Remember, Understand, Apply, Analyse, Evaluate, Create) are the revised taxonomy of Anderson and Krathwohl, not Bloom's original 1956 categories, which were Knowledge, Comprehension, Application, Analysis, Synthesis and Evaluation. The Analyse verbs `differentiate` and `attribute` are two of the three cognitive processes that revision names for that level (differentiating, organizing, attributing).

- Bloom, B. S., Engelhart, M. D., Furst, E. J., Hill, W. H. and Krathwohl, D. R. (1956). *Taxonomy of Educational Objectives: The Classification of Educational Goals. Handbook I: Cognitive Domain.* New York: David McKay.
- Anderson, L. W. and Krathwohl, D. R. (eds.) (2001). *A Taxonomy for Learning, Teaching, and Assessing: A Revision of Bloom's Taxonomy of Educational Objectives.* New York: Longman (later printings by Allyn and Bacon).

**Expanding review intervals.** The review ladder descends from the spacing effect and from graduated-interval flashcard scheduling. It is not SuperMemo's SM-2 and carries no ease factor.

- Ebbinghaus, H. (1885). *Über das Gedächtnis.*
- Leitner, S. (1972). *So lernt man lernen. Der Weg zum Erfolg.* Freiburg im Breisgau: Verlag Herder.

**Analogy retirement.** The instruction to name where an analogy breaks reflects standard practice in analogical-reasoning pedagogy. No single source is claimed for it.

## Convergence with prior work

The architecture of this skill converges with the `teach` skill in https://github.com/alexknowshtml/claude-skills, which was read in summary before this skill was designed. A mechanical comparison against its full text found zero shared four-word sequences across every file here, so no text was taken. What is shared is generic agent-loop practice that predates both: keep state in a file, re-read it before acting, ask one question at a time, write back immediately rather than batching.

That skill credits its own core to a "Learn Quiz" prompt, attributed in that repository's README to its original author and to the person who shared it, and states that its own contribution is session sourcing, checklist tracking and incremental mastery confirmation. None of those three appear here. This skill does not read session transcripts, keeps no concept checklist and has no completion gate. It is prospective rather than retrospective, auto-triggering rather than explicitly invoked, and models decay rather than completion.

No file named LICENSE was found at the root of that repository when it was checked, and its README invites copying folders. That is an informal invitation rather than a stated license, so attribution is the safe course, which is the reason for this section.

## Parameters are defaults, not findings

The following numbers were chosen for plausibility and are not derived from evidence. Treat them as adjustable defaults: the review ladder of 1, 3, 7, 16, 35 and 90 days; re-entry at rung 3 for a returning archived theme; the cap of four modules per build; and the module gate thresholds of two prior sightings and roughly five derivation steps.

Two assumptions underneath the design are also open, and are stated here rather than hidden. Spaced retrieval has its strongest evidence for discrete items rather than for mechanism comprehension, which is what this skill actually teaches. And the revised taxonomy does not claim strict cumulative hierarchy, so the rung-by-rung climb is a design choice rather than something the framework requires.

## Notices

Names of frameworks, authors, publications and products in this repository are used only to identify them and to credit their sources. No affiliation with, or endorsement by, any of them is claimed. No text from the cited works is reproduced. Claude is a trademark of Anthropic, PBC; this project is independent and is not affiliated with Anthropic. This repository is provided as is and is not legal advice.
