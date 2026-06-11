---
name: storyteller
description: Turn lived experience into a structured personal essay with honest voice, research, and a fable. Use when you have a story to tell — a lesson from a failure, a habit that solved a new problem, a moment that changed how you work. Not when you want to summarise an idea.
---

# `/storyteller` — A Claude Skill for Writing Personal Essays

*A skill for turning lived experience into structured, honest, personal essays — with a fable at the start, research at the end, and your real voice in between.*

---

## Why this exists

I have been writing personal essays about technology, learning, and the habits that have quietly shaped how I work. The process I use has become repeatable enough that I turned it into a Claude skill.

Every essay I write starts the same way: I have something I want people to *feel*, not just read. A lesson that came from a specific moment, not a general observation. An old habit that turned out to solve a new problem.

Getting from that raw feeling to a 1500-word essay that doesn't sound like it was generated takes a specific sequence. This skill encodes that sequence — validated against how ten celebrated storytellers describe their own process. You can use it for your own story.

---

## What it does

You bring a rough idea, a lived experience, or even just a feeling you want to write about.

The skill starts by interviewing you — not jumping into writing. Four questions, one at a time:

1. **Why are you writing this?** Not the topic — the real reason. Who do you want to read it? What do you want them to feel? Why are *you* the right person to tell this story?
2. **What actually happened?** The unpolished version, chronologically. Where were you, what went wrong, who was there, what did you almost do instead?
3. **What sentence are you most reluctant to write?** The one that feels too exposed, too small, or too honest. That sentence is almost always the center of the essay.
4. **How do you want this to feel?** A confession? A lesson? A question you still haven't answered? Your instinct about how it should feel almost always contains the structure.

Only after that conversation does the skill move into building the essay.

The full process then walks you through:

1. **Find the avoided sentence** — the thing you are most reluctant to say is almost always what the essay is really about. This comes before everything else.
2. **Metacognition** — the real insight underneath the topic, the specific moment it became true, and what you stood to lose if it had not arrived
3. **Finding the anchor story** — a fable, myth, or historical moment where the same insight hides in the part nobody talks about
4. **Building your personal arc** — origin → carried forward → tested → named → new application, each stage grounded in a physical scene
5. **Research validation** — the vocabulary and evidence for what you were doing instinctively, run via a research agent
6. **Structuring like a storyteller** — the arc that opens with a question and pays off in the closing image, with a reader-first test at every section break
7. **Editing like an editor** — structural, line-level, and length passes; checking that the avoided sentence made it back in
8. **Postscripts over footnotes** — the main essay stays personal and tight; research and side-stories reward curious readers at the end

Target output: ~1500 words / ~7 min read for the main essay, with optional postscripts.

---

## The essay arc

```
Opening — the anchor story, the overlooked detail, the question nobody asks
Bridge — "I have been thinking about this. I think I finally understand why."
Origin — the earliest personal memory, grounded in a physical scene
Built — how the habit or belief was carried forward
Tested — a new context that challenged it
The new problem — what the essay is really about
The solution — the old insight applied to the new problem
Closing — return to the opening image, one final punch, no summary
```

---

## The voice principles

- **Find the avoided sentence first.** The essay is almost always about the thing you did not plan to say.
- **Confessions are features, not bugs.** Failures told cleanly are what make readers trust writers.
- **Specifics over generals.** Not "a difficult meeting" — name the people, the stakes, the moment.
- **Physical scenes, not just mental observations.** One sensory detail — a smell, a light, a specific sound — grounds the reader in your body, your moment.
- **Real speech where it happened.** Paraphrase keeps readers outside. Direct speech puts them in the room.
- **Short sentences at turning points.** Save long sentences for building context.
- **Reader first at every structural decision.** At each section break: why should a stranger keep reading here?
- **The metaphor does not need explaining.** Trust the reader.
- **Humor is one line, self-aware, and never a setup.**
- **The ending does not summarize.** It lands on one image or one direct instruction.
- **Research confirms instinct. It does not replace it.**

---

## How to install

Copy `storyteller.md` into your `~/.claude/commands/` directory:

```bash
mkdir -p ~/.claude/commands
cp storyteller.md ~/.claude/commands/storyteller.md
```

Then invoke it in Claude Code:

```
/storyteller
```

Or pass your idea directly:

```
/storyteller I want to write about how I stopped trusting my own judgment when AI arrived and had to find my way back to it.
```

---

## How this skill was built

This skill was built during the writing of ["Everyone Remembers the Thumb. Nobody Asks About the Clay Statue."](https://medium.com/@badaldavda) — a personal essay about note-taking as a way to stay genuinely engaged when working with AI.

The process we used:
- Raw idea about note-taking and AI
- Deep research agent to find the right anchor story (Ekalavya, from the Mahabharata — specifically the part nobody discusses)
- Mapped personal arc: school notebooks I despised → IIT prep → COVID Zoom meetings → AI over-trust
- Research agent to find vocabulary I didn't have: context anchoring, AI sycophancy, the jagged frontier problem, active recall
- Structured, edited, cut from ~2500 to ~1500 words, moved research to postscripts
- Validated the skill against the writing process of ten storytellers, found four universal gaps, updated accordingly

The four principles that appear across most celebrated storytellers and were missing from earlier versions:
1. **Reader experience as a structural criterion** — not just "have I said what I wanted to say?" but "why would a stranger keep reading?"
2. **Stakes** — what the narrator stood to lose. Without cost, there is no story, only a reflection.
3. **The avoided sentence** — the thing the writer is most reluctant to include is usually the center
4. **Physical/sensory grounding** — readers inhabit a body in a place, not an idea in the abstract

Validated against: Anne Lamott, Joan Didion, Malcolm Gladwell, Morgan Housel, Paul Graham, Tim Urban, James Clear, Brené Brown, Chimamanda Ngozi Adichie, Kurt Vonnegut, Mary Karr, Robert McKee, John McPhee, Gay Talese.

---

## A note on what this is and is not

This skill helps you write *your* story. It asks questions, finds the anchor, structures the arc, and edits the draft. But the memories are yours. The failures are yours. The avoided sentence is yours.

The skill will push you to be specific and honest. It will not let you stay general. It will suggest cuts that might sting. That is the point.

A personal essay that reads like it could have been written by anyone is not a personal essay.

---

## What's next

Someday I will also write about how I learned to build these Claude skills, and how a very old note-taking habit turned out to be the most useful thing I brought into the age of AI.

That story is still being written.

---

*Published by [Badal Davda](https://www.linkedin.com/in/badaldavda/). If you use this skill and it helps you write something, I would genuinely like to read it.*
