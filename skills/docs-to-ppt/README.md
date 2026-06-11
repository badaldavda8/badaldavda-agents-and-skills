# docs-to-ppt

Turn documents into slides — Marp for fast and internal, HTML for visual, complex, or high-stakes.

## Why this exists

I kept opening PowerPoint to do something that is fundamentally a text transformation problem. The format decision was always the same: simple content and internal audience means Marp, anything with Mermaid diagrams or a customer in the room means HTML. This skill encodes that decision and does the conversion.

## Install

```bash
cp skills/docs-to-ppt/SKILL.md ~/.claude/commands/docs-to-ppt.md
```

## Usage

```
/docs-to-ppt [path] [purpose] [audience] [format: marp|html|auto]
```

Examples:
```
/docs-to-ppt ./docs/ "platform overview for new engineers" "internal team" marp
/docs-to-ppt ./architecture.md "architecture review" "customer CTO" html
/docs-to-ppt ./notes/ "conference talk on GitOps" "external audience" auto
```

Pass `auto` and the skill recommends format before producing anything.

## Example output (Marp)

```markdown
---
marp: true
theme: default
paginate: true
size: 16:9
---

# Platform Overview
Internal engineering onboarding

---

## How a request moves through the system

- Entry via the API layer — auth checked here, not downstream
- Routed to the correct service by path prefix
- State written to the database; object store for files over 400KB

> Every component is independently deployable.

<!-- Speaker note: pause here — this is what people always ask about -->
```

## See also

- [talk-script](../talk-script/) — when the slides need a full narrative script alongside them
- [narrate-architecture](../narrate-architecture/) — when you need to understand the system before turning it into slides
