# talk-script

Read documents and produce a professional talk script written as a narrative — five-section story arc, slide cues, pause markers, built to rehearse.

## Why this exists

A slide deck is a filing system. A talk is an argument. I kept watching people present technical material by reading their slides aloud — not because they did not know their topic, but because nobody had turned the information into a narrative with a spine. This skill does that: one idea the audience leaves with, earned through a story rather than a summary.

## Install

```bash
cp skills/talk-script/SKILL.md ~/.claude/commands/talk-script.md
```

## Usage

```
/talk-script [path to docs or folder] [topic] [audience] [length in minutes]
```

Examples:
```
/talk-script ./docs/ "how our platform handles multi-region failover" "engineering all-hands" 20
/talk-script ./architecture.md "the case for GitOps over ClickOps" "customer CTO" 10
```

The skill asks five questions before reading anything — including one about a personal moment from your own experience. Do not skip it.

## Example output

```
## Talk: Why We Stopped Clicking and Started Committing
Audience: customer CTO and engineering leadership
Length: 10 minutes
One thing they leave with: Infrastructure that lives in Git is infrastructure you can reason about at 2am.

---

[SLIDE: Opening]
[PAUSE]
Eighteen months ago, one of our engineers got paged at 2am. The alarm said the load balancer configuration had drifted. He logged in and found three rules nobody remembered adding. They had been there for four months.

[SLOW]
Nobody had done anything wrong. But there was no record. No review.

[SLIDE: The Problem]
That is what ClickOps costs you — not the clicks, but the memory.
```

## See also

- [docs-to-ppt](../docs-to-ppt/) — when the talk needs slides alongside the script
- [storyteller](../storyteller/) — when the talk is a personal essay, not a technical presentation
