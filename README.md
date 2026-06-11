# Badal's Agents and Skills

> An attempt to share the way I prompt — using the skills framework.

---

## Who this is for

Anyone who has been using AI long enough to notice that the quality of your output is mostly a function of how you set up the context — not how smart the model is.

---

## My journey to here

I started with **prompt engineering**. Writing clever prompts, chaining outputs, trying to get consistent results through wording alone. That still matters, but thinking models have absorbed a lot of that burden. You do not need to tell a 2026 model to think step by step.

Then I got into **context engineering** — working with Kiro, figuring out how to give an AI model the right persona and background with as few tokens as possible. Less is more. A dense, well-structured context window beats a long rambling one every time.

Then came **Kiro's steering docs and hooks**. A structured way to describe how you work, what you care about, and what you want the agent to do automatically at the edges of a session. Same idea as context engineering, but persistent and composable.

Now I am here — **Claude's skills framework**. Reusable, invokable prompts that ask you questions before they do anything, carry a process, and produce consistent output across sessions. It is context population I was doing manually before, but in a more structured, shareable form.

Each step was the same move: taking something I was doing by hand and making it explicit enough that an AI could follow it reliably.

---

## Tomorrow this might not matter either

Anthropic's engineering team published a piece on [harness design for long-running applications](https://www.anthropic.com/engineering/harness-design-long-running-apps) that points at where this is going.

A harness is the orchestration layer around a model — the structure of agents, context, tools, and feedback loops that scaffolds what the model cannot yet do alone. They built one with a planner, a generator, and an evaluator. The planner consumed a skills document to embed visual standards into specs. The evaluator negotiated contracts and caught gaps. The whole thing outperformed a single agent dramatically on complex, long-running tasks.

The interesting line is this: better models reduce scaffolding needs. Opus 4.6 eliminated decomposition steps that 4.5 required. The harness got lighter as the model got better.

Which means the skills framework — this repo — is probably a transitional layer. Not permanent infrastructure. A way of making tacit knowledge explicit enough to survive a context switch, until models are good enough that the knowledge does not need to be stated at all.

That is fine. I would rather publish what I know now than wait for the version that does not need it.

---

## Quick Start

### Claude Code

```bash
git clone https://github.com/badaldavda8/badaldavda-agents-and-skills.git
cd badaldavda-agents-and-skills
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  cp "$skill" ~/.claude/commands/${name}.md
done
```

### Kiro

```bash
git clone https://github.com/badaldavda8/badaldavda-agents-and-skills.git
cd badaldavda-agents-and-skills
for skill in skills/*/SKILL.md; do
  name=$(basename $(dirname "$skill"))
  mkdir -p ~/.kiro/skills/${name}
  cp "$skill" ~/.kiro/skills/${name}/SKILL.md
done
```

Then invoke in Claude Code or Kiro:

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
| [`talk-script`](skills/talk-script/) | Read docs and produce a professional talk script written as a story — one spine, told like a narrative not a bullet list. | `/talk-script` |
| [`docs-to-ppt`](skills/docs-to-ppt/) | Read docs and produce a presentation — Marp for fast internal slides, HTML for high-stakes visual presentations with Mermaid diagrams. | `/docs-to-ppt` |
| [`starter-guide`](skills/starter-guide/) | Read docs and produce the onboarding guide a new person actually needs — mental model first, day-one tasks concrete. | `/starter-guide` |

### Reviewing

| Skill | What it does | Invoke |
|---|---|---|
| [`doc-review`](skills/doc-review/) | Critical review of any document. Purpose, structure, clarity, accuracy, voice. What is not working and one specific fix per issue. | `/doc-review` |
| [`skill-review`](skills/skill-review/) | Audit SKILL.md files for correctness and invocability. Checks YAML structure, description trigger quality, ambiguity, length, cross-skill gaps. | `/skill-review` |

---

## Essays

| Essay | What it's about | Skill used |
|---|---|---|
| [How to Actually Be a Human in the Loop](essays/ekalavya-and-the-ai-loop.md) | Note-taking as active human-in-the-loop practice, Ekalavya, AI sycophancy | `/storyteller` |

---

## What's Next

Skills I am building:

- `/assumption-audit` — surface every assumption in an AI conversation before they compound
- `/weekly-brief` — the scheduled agent that writes my weekly status report

Essays in progress:

- *How I learned to build these skills* — the note-taking habit that turned out to be the most useful thing I brought into the age of AI
- *The Kamadhenu Question* — on agents, intensity, and what you actually ask for when something gives everything

---

## About

Badal Davda — Senior Delivery Consultant, AWS ProServe.

[LinkedIn](https://www.linkedin.com/in/badaldavda/) · [Medium](https://medium.com/@badaldavda8)

*Personal projects and personal opinions. Not AWS or Amazon positions.*

---

## License

MIT — use freely, build on it, share what you make.
