# doc-review

Critical editorial review across six dimensions — what is not working and exactly one fix per weakness.

## Why this exists

AI feedback defaults to encouragement. "Great structure, clear writing" — useless. I wanted something that reads a document the way a good editor does: a specific problem and a specific fix, not a general observation. I kept finishing drafts not knowing what was actually wrong until someone else told me two weeks later.

## Install

```bash
cp skills/doc-review/SKILL.md ~/.claude/commands/doc-review.md
```

## Usage

```
/doc-review [path or paste] [type] [audience]
```

Types: `personal-essay` | `technical-doc` | `onboarding-guide` | `talk-script` | `proposal` | `general`

Examples:
```
/doc-review ./draft.md personal-essay general-reader
/doc-review ./runbook.md technical-doc on-call-engineers
```

## Example output

```
## Review: draft.md
Reader: general reader
Purpose: explain why note-taking matters when working with AI

### What is working
- Opening scene is specific and earns attention immediately
- The turn in paragraph four lands — the contrast is real

### What is not working
- Purpose (NEEDS WORK): Two arguments, not one. Pick one.
  Fix: Cut the sycophancy section to one paragraph or move to postscript.
- Voice (NEEDS WORK): Paragraph seven sounds generated. "It is worth noting that..."
  Fix: Delete the sentence. The paragraph works without it.

### The most important fix
The closing summarises instead of landing. Cut everything after "That is the habit."

### What is missing
The reader finishes not knowing what to do differently tomorrow.
```

## See also

- [skill-review](../skill-review/) — same editorial discipline applied to SKILL.md files
- [storyteller](../storyteller/) — if the doc is a personal essay that needs a full rewrite
