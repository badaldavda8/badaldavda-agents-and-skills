# Skills

Each skill lives in its own folder with up to three files:

| File | Purpose |
|---|---|
| `SKILL.md` | The skill itself — install this into `~/.claude/commands/` |
| `EXAMPLES.md` | Real examples with notes on what needed multiple passes |
| `REFERENCE.md` | Supporting research, comparisons, deeper reading |

---

## Available Skills

### Writing

| Skill | Description | Invoke |
|---|---|---|
| [`storyteller`](storyteller/) | Turn lived experience into a structured personal essay — interview, anchor story, arc, edit, postscript. Validated against 10 master storytellers. | `/storyteller` |

### Understanding

| Skill | Description | Invoke |
|---|---|---|
| [`explain-like-a-story`](explain-like-a-story/) | Explain any concept as a story in a made-up world. Where the story breaks down is where your understanding has a gap. | `/explain-like-a-story` |
| [`narrate-architecture`](narrate-architecture/) | Understand a system by following a single request through it, narrated flow by flow. Diagrams show structure. Narration shows behaviour. | `/narrate-architecture` |
| [`customer-story`](customer-story/) | Get the founding story of a customer's business — real if documented, reconstructed if not. Walk in knowing what they are proud of and what they are still trying to prove. | `/customer-story` |

### Thinking

| Skill | Description | Invoke |
|---|---|---|
| [`grill-me`](grill-me/) | Break the yes-person dynamic. AI asks questions, you answer, until every assumption is on the table. Credit: inspired by Andrej Karpathy. | `/grill-me` |
| [`debug-deep`](debug-deep/) | Break out of a troubleshooting loop with a structured search order: code first, then official docs, then Reddit, then AWS re:Post — before any suggestion. | `/debug-deep` |

---

## Installing a skill

```bash
# Install one skill
cp skills/storyteller/SKILL.md ~/.claude/commands/storyteller.md

# Install all skills at once
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname $skill))
  cp "$skill" ~/.claude/commands/${name}.md
done
```

Then in Claude Code, invoke any skill:
```
/storyteller
/explain-like-a-story distributed consensus
/grill-me my migration plan
/debug-deep Lambda timeout after Node 20 upgrade
/narrate-architecture the order service
/customer-story Stripe
```
