# debug-deep

Force AI to read the code and docs before suggesting another fix — structured search order, evidence before recommendation.

## Why this exists

AI is good at pattern-matching to plausible-sounding fixes. It is less good at stopping to read what is actually there. I kept getting three variations of the same wrong answer, and the real answer was in the documentation the AI had skipped. The word "before" in the prompt is the whole mechanism — it changes the order of operations.

## Install

```bash
cp skills/debug-deep/SKILL.md ~/.claude/commands/debug-deep.md
```

## Usage

```
/debug-deep [describe the problem]
```

Examples:
```
/debug-deep Node 20 upgrade broke cold start times in production
/debug-deep Python requests library silently swallowing connection errors after version bump
```

## Example output

> **Step 1 — Code:** The HTTP call passes a `timeout` parameter. The parameter signature changed in `requests` 2.28 — it now expects a tuple, not an integer. No error is raised on invalid input; the timeout is silently ignored.
>
> **Step 2 — Official docs:** The `requests` 2.28 changelog documents the signature change. No deprecation warning was added.
>
> **Step 3 — Community forums:** Multiple Stack Overflow threads describe this exact silent failure after a `requests` version bump. One links to the upstream issue.
>
> **Recommendation:** Update the timeout call to pass a tuple `(connect_timeout, read_timeout)`. The connection errors will surface correctly.

## See also

- [narrate-architecture](../narrate-architecture/) — when the bug is in the system design, not the code
