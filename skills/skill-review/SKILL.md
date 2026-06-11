---
name: skill-review
description: Review Claude skill files for correctness, clarity, and invocability. Use when you have written new skills and want to know if they will actually work — not just read well. Checks YAML structure, description trigger quality, instruction vs prose ratio, ambiguity, length, and cross-skill coherence.
---

# skill-review

Review Claude skills the way a Claude expert would. Find what breaks before Claude does.

## When to use

- You have written one or more SKILL.md files and want them reviewed
- A skill is not triggering when you expect it to
- A skill is producing inconsistent or off-target output
- You want to audit a full skill set for gaps and overlap

## How to invoke

```
/skill-review [path to skill file or skills directory]
```

Examples:
```
/skill-review ./skills/my-skill/SKILL.md
/skill-review ./skills/
```

## What AI checks — seven dimensions

### 1. YAML frontmatter (structural correctness)
- Does the file start with `---`?
- Does it have `name` and `description` fields?
- Without these, Claude cannot detect the skill. This is checked first.

Signals a broken skill:
```
# My Skill        ← starts with heading, not YAML → invisible to Claude
```

Correct:
```yaml
---
name: my-skill
description: ...
---
```

### 2. Description quality (trigger signal)
Claude uses the description field to decide when to invoke a skill automatically. Good descriptions have three properties:

- **Specific trigger condition** — "Use when X" not "Useful for many things"
- **Under 50 words** — longer descriptions dilute the trigger signal
- **Contrast** — states what the skill is NOT for, making the boundary clear

Rate as:
- STRONG: specific, concise, clear trigger, includes contrast
- GOOD: clear trigger but too long or missing contrast
- WEAK: vague, generic, no trigger condition, or missing entirely

### 3. Invocation clarity
- Is the invoke command obvious?
- Are arguments named and typed?
- Is there at least one concrete example?
- Could a user invoke this cold, without reading the full skill?

### 4. Instructions vs prose ratio
Claude follows instructions better than prose explanations. Check:
- Are steps numbered and actionable?
- Is the word "should" used where Claude needs a directive?
- Are paragraphs explaining *why* longer than paragraphs telling Claude *what to do*?
- Would replacing prose with a bullet list lose anything?

Matt Pocock's benchmark: a skill should be invocable by someone who reads only the headings and examples.

### 5. Ambiguity — where Claude will go off-rails
Find every step where Claude has more than one reasonable interpretation. Flag:
- Vague outputs ("summarise the key points" — how many? what format?)
- Unconstrained loops ("keep asking questions" — when does it stop?)
- Missing fallbacks ("if the founding story is not documented..." — what then?)
- Subjective judgements with no criteria ("make it professional" — by whose standard?)

### 6. Length and density
Benchmarks from strong public skills:
- Under 50 lines: lean, likely strong
- 50–100 lines: acceptable if content-dense
- 100–150 lines: review each section — is every line earning its place?
- Over 150 lines: split the skill or move philosophy to REFERENCE.md

Check: is the philosophy/reasoning longer than the instructions? If yes, move it to REFERENCE.md.

### 7. Cross-skill coherence (for a skill set)
When reviewing a directory:
- Any two skills that do the same job? Name the overlap.
- Any obvious gap — a job the user clearly does that no skill covers?
- Do the skills share consistent conventions (same argument order, same output format headers)?
- Do skills that often run together reference each other?

## Output format

```
## Skill Review: [skill name or directory]

### [skill-name] — STRONG / GOOD / NEEDS WORK / BROKEN

**YAML**: ✓ / ✗ [reason if broken]
**Description**: STRONG / GOOD / WEAK — [one line explanation]
**Invocation**: CLEAR / UNCLEAR — [one line]
**Instructions vs prose**: STRONG / NEEDS WORK — [one line]
**Ambiguity**: LOW / MEDIUM / HIGH — [specific step that could go wrong]
**Length**: [N lines] — LEAN / ACCEPTABLE / OVER-SPECIFIED
**Most important fix**: [one sentence, one specific change]

---
[repeat per skill]

### Cross-skill analysis (if reviewing a directory)
**Overlap**: [any]
**Gaps**: [any]
**Conventions**: CONSISTENT / INCONSISTENT — [what differs]
**Most urgent fix across the set**: [one sentence]
```

## What makes a skill BROKEN vs NEEDS WORK

**BROKEN** — will not work at all:
- Missing YAML header (Claude cannot detect it)
- `description` field missing (no trigger signal)
- No invoke example (user cannot call it)
- Circular instructions (skill instructs Claude to "do what makes sense")

**NEEDS WORK** — will work but produce inconsistent output:
- Ambiguous steps
- Missing fallbacks for edge cases
- Instructions buried in prose
- Too long (Claude may lose track of earlier steps)

**GOOD** — works reliably, has room to tighten:
- Minor ambiguity in one step
- Slightly over-specified
- One weak section that could be cut

**STRONG** — works well, would not change without a reason:
- Clear, concise, specific
- All steps actionable
- Fallbacks exist for the obvious edge cases
