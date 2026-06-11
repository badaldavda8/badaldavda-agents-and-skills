# starter-guide

Read a pile of documentation and produce the onboarding guide a new person actually needs — mental model first, day-one tasks concrete, 20-minute read.

## Why this exists

Documentation grows toward completeness, not toward understanding. The new engineer joins, gets pointed at the wiki, and spends a week reading things in the wrong order. This skill reads all the existing docs and produces a curated path through them — the frame that makes the detail make sense, written for someone who does not yet know what questions to ask.

## Install

```bash
cp skills/starter-guide/SKILL.md ~/.claude/commands/starter-guide.md
```

## Usage

```
/starter-guide [path to docs or folder] [audience] [depth]
```

Examples:
```
/starter-guide ./docs/ "engineer new to the platform, comfortable with backend basics" "day-1 onboarding"
/starter-guide ./architecture/ "technical lead joining mid-project" "full system overview"
```

## Example output

```
## What this system is for
The platform manages the full lifecycle of data ingestion jobs — from scheduled trigger to validated output.

## The mental model
Think of it as a post office that tracks every letter: it does not write the letters, it ensures they arrive, and it keeps a record of every one that did not.

## What you will do on day one
1. Run `make dev-setup` — it will fail on the secrets step; that is expected, follow the error message
2. Open `src/core/state_machine.py` and read the docstring at the top
3. Find one failed run in staging and trace it through the logs
```

## See also

- [doc-review](../doc-review/) — if the existing docs need fixing before the guide is worth writing
- [narrate-architecture](../narrate-architecture/) — if the new person needs to understand system behaviour, not just structure
