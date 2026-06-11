# Badal's Agents and Skills

> Skills and essays for working with AI intentionally — not just efficiently.

I am a Senior Delivery Consultant at AWS ProServe. I have been building around myself with agents and skills for two years. This repo is where I publish what I have learned — as skills you can install, and essays that explain the thinking behind them.

The skills are practical. The essays are personal. Both are about the same thing: staying genuinely engaged when AI is doing the work, rather than watching from the treeline.

---

## Quick Start

### Claude Code

```bash
# Clone the repo
git clone https://github.com/badaldavda8/badaldavda-agents-and-skills.git

# Install all skills at once
cd badaldavda-agents-and-skills
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  cp "$skill" ~/.claude/commands/${name}.md
done
```

Then invoke any skill in Claude Code:

```
/storyteller
/explain-like-a-story distributed consensus
/grill-me my migration plan
/debug-deep Node 20 upgrade broke cold start times
/narrate-architecture the order service
/customer-story Stripe
```

---

## Skills

### Writing

| Skill | What it does | Invoke |
|---|---|---|
| [`storyteller`](skills/storyteller/) | Turn lived experience into a structured personal essay — interview, anchor story, arc, edit, postscript. Validated against 10 master storytellers. | `/storyteller` |

### Understanding

| Skill | What it does | Invoke |
|---|---|---|
| [`explain-like-a-story`](skills/explain-like-a-story/) | Explain any concept as a story in a made-up world. Where the story breaks down is where your understanding has a gap. | `/explain-like-a-story` |
| [`narrate-architecture`](skills/narrate-architecture/) | Understand a system by following a single request through it, narrated flow by flow. Diagrams show structure. Narration shows behaviour. | `/narrate-architecture` |
| [`customer-story`](skills/customer-story/) | Get the founding story of a customer's business — real if documented, reconstructed if not. Walk in knowing what they are proud of and what they are still trying to prove. | `/customer-story` |

### Thinking

| Skill | What it does | Invoke |
|---|---|---|
| [`grill-me`](skills/grill-me/) | Break the yes-person dynamic. AI asks questions, you answer, until every assumption is on the table. Credit: inspired by Andrej Karpathy. | `/grill-me` |
| [`debug-deep`](skills/debug-deep/) | Break out of a troubleshooting loop with a structured search order: code first, then official docs, then community forums — before any suggestion. | `/debug-deep` |

### Presenting

| Skill | What it does | Invoke |
|---|---|---|
| [`talk-script`](skills/talk-script/) | Read docs and produce a professional talk script written as a story — one spine, professional delivery, told like a narrative not a bullet list. | `/talk-script` |
| [`docs-to-ppt`](skills/docs-to-ppt/) | Read docs and produce a presentation — Marp (Markdown) for fast internal slides, HTML for high-stakes visual presentations. Format follows purpose. | `/docs-to-ppt` |
| [`starter-guide`](skills/starter-guide/) | Read docs and produce the onboarding guide a new person actually needs — mental model first, day-one tasks concrete, pointers to deeper material at every step. | `/starter-guide` |

### Reviewing

| Skill | What it does | Invoke |
|---|---|---|
| [`doc-review`](skills/doc-review/) | Critical review of any document — essay, technical doc, onboarding guide, talk script. Purpose, structure, clarity, accuracy, voice. What is not working and one specific fix per issue. | `/doc-review` |
| [`skill-review`](skills/skill-review/) | Review Claude SKILL.md files for correctness and invocability. Checks YAML structure, description trigger quality, ambiguity, length, and cross-skill gaps. | `/skill-review` |

---

## Essays

Essays built using these skills. Each one links back to the skill that helped write it.

| Essay | What it's about | Skill used |
|---|---|---|
| [How to Actually Be a Human in the Loop](essays/ekalavya-and-the-ai-loop.md) | Note-taking as active human-in-the-loop practice, Ekalavya, AI sycophancy | `/storyteller` |

---

## How the Skills Work

Each skill is a structured conversation, not a magic prompt. It asks you questions before it does anything. It interviews you, pushes for specifics, finds the thing you are most reluctant to say, and only then builds.

The anatomy of every skill:

- **What it does** — one clear statement of purpose
- **Opening interview** — questions the skill asks before starting
- **The process** — step-by-step, with the reasoning behind each step
- **Voice principles** — what makes the output sound like you, not like AI
- **Closing conventions** — the things that appear in every finished piece

The goal is not to replace your thinking. It is to make your thinking visible so you can push back on it.

---

## The Philosophy

I started building skills the same way I started taking notes during IIT prep — not because someone told me to, but because doing nothing while something else worked felt like the opposite of learning.

The problem with AI is that it is very agreeable. It validates your assumptions, carries your bad premises forward, and produces beautiful output that reads like understanding. Note-taking — and its AI equivalent, asking AI to build a mind map of its own reasoning — is how I stay in the conversation rather than just receiving it.

That is what these skills are built on. Not productivity. Presence.

---

## What's Next

Skills I am building:

- `/deep-work-review` — reviewing AI-generated work the way an editor would, not a rubber stamp
- `/assumption-audit` — surface every assumption in an AI conversation before they compound
- `/weekly-brief` — the scheduled agent that writes my weekly status report (open-sourcing the prompt and structure)

### Presenting

| Skill | What it does | Invoke |
|---|---|---|
| [`talk-script`](skills/talk-script/) | Read docs and produce a professional talk script written as a story — one spine, professional delivery, told like a narrative not a bullet list. | `/talk-script` |
| [`docs-to-ppt`](skills/docs-to-ppt/) | Read docs and produce a presentation — Marp (Markdown) for fast internal slides, HTML for high-stakes visual presentations. Format follows purpose. | `/docs-to-ppt` |
| [`starter-guide`](skills/starter-guide/) | Read docs and produce the onboarding guide a new person actually needs — mental model first, day-one tasks concrete, pointers to deeper material at every step. | `/starter-guide` |

### Reviewing

| Skill | What it does | Invoke |
|---|---|---|
| [`doc-review`](skills/doc-review/) | Critical review of any document — essay, technical doc, onboarding guide, talk script. Purpose, structure, clarity, accuracy, voice. What is not working and one specific fix per issue. | `/doc-review` |
| [`skill-review`](skills/skill-review/) | Review Claude SKILL.md files for correctness and invocability. Checks YAML structure, description trigger quality, ambiguity, length, and cross-skill gaps. | `/skill-review` |

---

## Essays in Progress

- *How I learned to build these skills* — the note-taking habit that turned out to be the most useful thing I brought into the age of AI
- *The Kamadhenu Question* — on agents, intensity, and what you actually ask for when something gives everything

---

## About

Badal Davda — Senior Delivery Consultant, AWS ProServe.

[LinkedIn](https://www.linkedin.com/in/badaldavda/) · [Medium](https://medium.com/@badaldavda)

*These are personal projects and personal opinions. Not AWS or Amazon positions.*

---

## License

MIT — use freely, build on it, share what you make.
