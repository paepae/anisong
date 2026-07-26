---
name: lean-writing
description: Read before the first write, not after — the snapshot contract every artifact follows. Covers creating or editing any file a future reader reads: code, comments, docs, READMEs, agent instruction files, config, skills, plans, agent briefs. Retrofitting a finished draft to the contract costs more than drafting to it.
---

# Lean Writing

Every artifact is a **snapshot**: it describes the current state of the system,
written as if it had always been this way. The story of how it got this way
already has homes — git history, the ticket, the plan file, your closing
summary. Write the story there, in full detail; write the snapshot here.

## The snapshot contract

An artifact (code, comment, doc section, config) contains exactly two things:

1. **Current state** — what the thing is and does, in present tense. A reader
   who never saw any previous version understands it completely.
2. **Still-binding whys** — a reason stays only while it constrains the
   reader's next action ("Node stays on 20 — the native addon breaks on 22").
   A reason that only justifies a past decision belongs in the commit message
   or ticket.

And it holds to the reader's standard: unambiguous, internally consistent,
matching sibling entries in weight and shape, complete enough that nothing
forces a cross-reference, and no wordier than its content demands — every
sentence earns its keep.

Code follows the same contract: replaced code is deleted (git keeps it), names
describe what things are now (`load_config`, not `load_config_v2` or
`new_loader`), and comments state constraints the code cannot show.

## Updating

Rewrite the stale passage in place so the section reads as freshly written
today. The previous text's archive is git, not an appended "Update:" layer.

The update is done when the **whole file** is true, not just the section you
came for: check every other claim the file makes against the system's current
state (read the code it describes), and give any stale one the same in-place
rewrite. An artifact that contradicts the system is worse than a missing one.

The sweep is **repo-wide** — every file that describes the changed system, not
only the directories you edited. Two categories stay out, because they are
story-homes by design:

- **Applied migrations**, where a dated changeset describes what it introduced.
- **Planning artifacts** — plans, specs, design docs, RFCs — which record what a
  change was going to do, and are read as history the moment it ships.

## Where the story goes

"What changed and why", migration notes, verification records ("verified
from off-box, exit codes confirmed"), dates, ticket ids — route them to the
commit message, ticket comment, plan file, or your reply summary, where they
keep full fidelity and the reader who wants them finds them via git blame or
the ticket. One artifact carries a ticket id by design: that ticket's plan or
spec file, which is its record.

When the task itself says "document what changed and why" or "don't lose
anything from this session", satisfy it through those homes: snapshot in the
artifact, story in the summary/commit/ticket. Both requests are met in full —
just never both in the artifact.

## The sentence test

Before saving, read each sentence and ask: **does a reader who never saw the
old version act on this?** A sentence about a previous version, a past event,
or your own process fails the test — move it to a story-home and delete it
here.

The reliable **tell** is comparative language with no referent in the artifact —
*now, still, old, new, previously, formerly, no longer, used to* lean on a
before/after the reader can't see. Treat each as a story sentence until you
justify it as timeless. ("A new value takes effect from the next login" guides
any future editor and survives; "expect one more re-auth on the old cadence
before the new one takes hold" narrates this change and goes.)

Grep for the high-precision half:

```bash
grep -rnE --exclude-dir=.git '\b(previously|formerly|no longer|used to)\b' .
```

The word boundaries carry the weight — unbounded, `used to` matches *refused
to*. Read the rest by eye: *now*, *still*, *old* and *new* carry legitimate
senses often enough ("the file is now on disk") that grepping them returns
mostly noise, and a noisy check gets turned off.

## Subagents

Quote this block verbatim into any brief that produces text. Paraphrasing it from
memory drops the whole-file rule first — the rule that catches the most defects.

```
Write every artifact as a snapshot: it describes the system's current state, as if it
had always been this way. It contains exactly two things — what the thing is and does
in present tense, and any reason that still constrains the reader's next action.

Verify the whole file, not just the section you came for: check every other claim the
file makes against the code it describes, and rewrite any stale one in place. A file
that contradicts the system is worse than a missing one.

Every comparative word — previously, formerly, no longer, used to, now, still, old,
new — needs a referent the reader can see in the artifact itself. Keep the ones that
guide a future editor ("a new value takes effect from the next login"); route the ones
that narrate this change into your report back, along with what changed and why,
migration notes, verification records, dates and ticket ids.
```
