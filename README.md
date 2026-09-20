# Key Learning

**A field-agnostic AI tutor skill for Claude that explains how and why from first principles, then remembers what you learned. Personal learning plans built on Bloom's taxonomy, first-principles decomposition and spaced repetition, cached in a plain markdown ledger.**

`claude-skill` · `agent-skill` · `ai-tutor` · `spaced-repetition` · `blooms-taxonomy` · `first-principles` · `learning-plan` · `curriculum-design` · `self-directed-learning` · `pedagogy` · `knowledge-retention` · `personalized-learning`

## What it is

Key Learning is an [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) packaged as a Claude plugin. It turns an ordinary "how does this actually work?" into a durable learning plan, without you having to ask for one.

When you ask how a mechanism works, why one method is used instead of another, or what principle sits underneath something, it answers in the register of a senior colleague showing you the ropes: it names the phenomenon, states the givens the field does not derive further, rebuilds the mechanism forward one causal step at a time, and closes at a boundary where the mechanism stops holding. Then it asks a single question that makes you apply the account rather than recite it.

Every theme is logged. Themes that recur get a curriculum. Themes you have mastered get scheduled for review before you forget them.

It works in any subject. Nothing about the domain is built in, so the same skill serves a clinician, an engineer, a lawyer and a graduate student without reconfiguration.

## Why it exists

Most AI tutoring is amnesiac. You get a good explanation, you close the tab, and six weeks later you ask the same question again with no record that you ever understood it. Most AI study tools solve the opposite half: they drill flashcards you had to write yourself, with no teaching in front of the drilling.

This sits between the two. The teaching is the primary output. The memory is a side effect of the teaching, not a separate chore.

## Installation

Download the `.plugin` file from releases, or clone and copy the skill folder:

```bash
git clone https://github.com/drmismo7/key-learning.git
cp -r key-learning/skills/key-learning ~/.claude/skills/
```

No configuration. On first use it asks once where the learning ledger should live.

## How it works

### Explanation, in four moves

**Phenomenon.** One sentence, with the jargon of your question stripped out.
**Floor.** The givens the field does not derive further, named as givens so you know where the derivation starts.
**Rebuild.** Forward from the floor, one causal step at a time, each step stating what would change if that step were removed. A step whose removal changes nothing is decoration and gets cut.
**Boundary.** One case where the mechanism weakens, reverses or stops applying.

### Bloom-level diagnosis

The skill reads your current level off the shape of your question, without asking: *what is it called* is Remember, *how do I use it here* is Apply, *why does it change when conditions change* is Analyse. It pitches the answer at that level and one rung above, and records the diagnosis so module objectives start where you actually are.

### Curriculum anchoring

A module sequence invented by a language model is a guess. Before writing one, the skill infers your field at runtime and borrows scope and sequence from the highest source it can reach: a standards or certifying body's competency framework, a graduate textbook's contents, a university course outline, or open courseware. Coverage from the source binds. Order is advisory, and every departure is written into the theme file, so you can always see which part of the plan came from the source and which came from the conversation.

Budget is one search and two fetches, once per theme, cached forever.

### Spaced repetition

Passed checks push the next review along an expanding ladder of 1, 3, 7, 16, 35 and 90 days. A failed check pulls it back a rung. Themes that survive the full ladder are archived out of the working index and stop costing anything.

### Two dials

**Trigger** controls how readily it speaks: never unless invoked, mechanism questions only, plus overdue notes, or plus a short drill before answering. Default is conservative, and a hard rule keeps it silent while you are mid-task whatever the dial says.

**Depth** controls how much it assumes: novice, practitioner, expert. Raising it produces shorter answers, so it doubles as a cost control.

Change either by saying so.

## Running cost

Progressive disclosure keeps the per-invocation cost low. The core instructions are roughly 830 words; the module builder, curriculum anchoring and ledger repair live in separate reference files that load only when actually needed, which is rare. The routine ledger check reads one line per active theme, and archived themes are never read at all.

## Ledger layout

```
learning/
  index.md        one line per active theme, plus dial settings
  archive.md      mastered themes, never read on trigger
  themes/
    <slug>.md     mechanism, first-principles floor, curriculum anchor,
                  modules, review log
```

Plain markdown throughout. Readable and editable without any tool, portable between machines, and diffable in git.

## Design choices you may want to argue with

The review intervals, the four-module cap and the module gate thresholds are plausible defaults, not findings. Spaced retrieval has its strongest evidence for discrete facts rather than for mechanism comprehension, which is what this actually teaches. The rung-by-rung climb is a design choice; the revised taxonomy does not claim strict cumulative hierarchy. All of this is stated in [CREDITS.md](CREDITS.md) rather than buried.

## Companion skills

If a quiz or flashcard skill is present, this one hands over the module checks instead of building its own drill. It owns diagnosis, explanation, curriculum design and scheduling, and deliberately nothing else.

## Credits

Frameworks, sources and prior-art convergence are documented in [CREDITS.md](CREDITS.md). Short version: the taxonomy is Anderson and Krathwohl 2001, the spacing ladder descends from Ebbinghaus and Leitner, and the architecture converges with the [`teach`](https://github.com/alexknowshtml/claude-skills) skill, verified at zero shared four-word sequences.

## License and notices

MIT. Framework, author and product names are used for identification and credit only, with no affiliation or endorsement implied. Claude is a trademark of Anthropic, PBC; this project is independent of Anthropic. See [CREDITS.md](CREDITS.md).
