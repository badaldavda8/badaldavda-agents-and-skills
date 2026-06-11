# skill-review

Audit Claude SKILL.md files across seven dimensions — get a rating (BROKEN / NEEDS WORK / GOOD / STRONG) with one specific fix per weakness.

## Why this exists

Writing a skill that reads well is not the same as writing one that works. I kept writing SKILL.md files that looked clean but triggered inconsistently or drifted in output. The problem was almost always the same: a vague description, instructions buried in prose, or a step with two reasonable interpretations. This skill checks for those failure modes before Claude does. It encodes exactly what a Claude expert would look for.

## Install

```bash
cp skills/skill-review/SKILL.md ~/.claude/commands/skill-review.md
```

## Usage

```
/skill-review [path to skill file or skills directory]
```

Examples:
```
/skill-review ./skills/my-skill/SKILL.md
/skill-review ./skills/
```

## Example output

```
## Skill Review: debug-deep — GOOD

YAML: ✓
Description: GOOD — clear trigger, but 62 words; trim to under 50
Invocation: CLEAR
Instructions vs prose: NEEDS WORK — "Why the word before matters" is philosophy, not instruction; move to a comment or cut
Ambiguity: LOW
Length: 47 lines — LEAN
Most important fix: Move the prose explanation into a <!-- comment --> or delete it

---

### Cross-skill analysis (3 skills reviewed)
Overlap: None critical
Gaps: No skill for reviewing pull requests or code diffs
Conventions: CONSISTENT
Most urgent fix: Two description fields exceed 50 words
```

## See also

- [doc-review](../doc-review/) — same structured critique applied to written documents
