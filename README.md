# Badal's Agents and Skills

> Skills and essays for working with AI intentionally — not just efficiently.

I am a Senior Delivery Consultant at AWS ProServe. I have been building around myself with agents and skills for two years. This repo is where I publish what I have learned — as skills you can install, and essays that explain the thinking behind them.

The skills are practical. The essays are personal. Both are about the same thing: staying genuinely engaged when AI is doing the work, rather than watching from the treeline.

---

## Quick Start

### Claude Code

```bash
# Clone into your Claude commands directory
git clone https://github.com/badaldavda8/badaldavda-agents-and-skills.git

# Copy skills to Claude commands
cp badaldavda-agents-and-skills/.claude/commands/*.md ~/.claude/commands/
```

Then invoke any skill in Claude Code:

```
/storyteller
```

---

## Skills

| Skill | What it does | Invoke |
|---|---|---|
| [`storyteller`](skills/storyteller.md) | Turn lived experience into a structured personal essay — interview, anchor story, arc, edit, postscript | `/storyteller` |

*More skills coming. See [what's next](#whats-next).*

---

## Essays

Essays built using these skills. Each one links back to the skill that helped write it.

| Essay | What it's about | Skill used |
|---|---|---|
| [Everyone Remembers the Thumb. Nobody Asks About the Clay Statue.](essays/ekalavya-and-the-ai-loop.md) | Note-taking as active human-in-the-loop practice, Ekalavya, AI sycophancy | `/storyteller` |

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

---

## Essays in Progress

- *How I learned to build these skills* — the note-taking habit that turned out to be the most useful thing I brought into the age of AI
- *The Kamadhenu Question* — on agents, intensity, and what you actually ask for when something gives everything

---

## About

Badal Davda — Senior Delivery Consultant, AWS ProServe.

[LinkedIn](https://www.linkedin.com/in/badaldavda/) · [Medium](https://medium.com/@badaldavda)

*These are personal projects and opinions, not AWS or Amazon positions.*

---

## License

MIT — use freely, build on it, share what you make.
