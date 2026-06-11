---
name: talk-script
description: Read documents, slides, or notes and produce a professional talk script written as a story. Use when you need to present technical material to an audience — conference talk, internal session, customer briefing — and want the delivery to feel like a narrative, not a slide read-aloud. A good talk script has a spine: one idea the audience should leave with, earned through a story, not a summary.
---

# talk-script

Turn documents into a talk. One spine. Professional delivery. Told like a story.

## When to use

- You have technical docs, architecture diagrams, or notes and need to turn them into a talk
- You have a presentation coming up and the slides exist but the narrative does not
- You want to present complex technical material to a non-technical or mixed audience
- You need a script tight enough to rehearse but natural enough to sound unscripted

## How to invoke

```
/talk-script [path to docs or folder] [topic] [audience] [length in minutes]
```

Examples:
```
/talk-script ./docs/ "how our platform handles multi-region failover" "engineering all-hands" 20
/talk-script ./architecture.md "the case for GitOps over ClickOps" "customer CTO audience" 10
```

## Opening interview — answer before AI reads anything

1. **What is the one thing you want the audience to leave with?** Not a list. One sentence. If they remember nothing else, what should it be?
2. **Who is the audience?** What do they already know? What do they care about? What would make them tune out?
3. **What is the talk length?** And is there Q&A time to plan for?
4. **Is there a moment from your own experience that connects to this topic?** A decision that was harder than it looked, a failure that taught something, a detail that surprised even you. This becomes the opening.
5. **What do you want the audience to do or think differently after this talk?**

Do not skip the personal moment question. A talk without a human moment is a document read aloud.

## What happens

1. AI reads all provided documents in full
2. AI extracts: the core thesis, the three to five supporting ideas, the most surprising or counterintuitive detail, and any decision that has a good story behind it
3. AI drafts the script in five sections:

```
Opening — a personal moment or provocative question that earns attention
The problem — what was broken, hard, or misunderstood before the solution
The journey — how the decisions were made, in narrative order (not chronological if narrative order is better)
The resolution — what was built, chosen, or learned, and why it holds
The close — one sentence the audience keeps, and a concrete invitation (try this, ask this, do this)
```

4. AI marks every slide cue: `[SLIDE: title]` so the script maps to presentation structure
5. AI flags: any place where a live demo, a diagram walk-through, or a pause for questions would land well

## Mixed or non-technical audiences

If the audience is non-technical or mixed: lead every section with *why it matters* before *how it works*. One technical detail per section max. Explain it in business terms first, technical terms second. The audience does not need to understand the mechanism — they need to trust the outcome.

## Rules

- **No customer names, company names, or identifying details.** Refer to "the platform", "the team", "the migration" — never the organisation.
- **Professional but not corporate.** No "synergies", no "leveraging", no "going forward". Real sentences. Real words.
- **Story structure, not bullet structure.** Each section flows into the next. No "and in this section we will cover..."
- **One idea per paragraph when scripted.** The audience cannot re-read. Each idea must land before the next arrives.
- **Mark the moments.** Every place where the speaker should pause, slow down, or make eye contact — mark it `[PAUSE]` or `[SLOW]`.

## Output format

```
## Talk: [Title]
Audience: [who]
Length: [N minutes]
One thing they leave with: [sentence]

---

[SLIDE: Opening]
[PAUSE]
[Script text — first person, natural speech rhythm]

[SLIDE: The Problem]
[Script text]

... and so on
```

## Why story structure, not slide structure

A slide deck is a filing system. A talk is an argument. The same information organised as an argument — with a problem, a journey, a resolution — lands differently than the same information organised as a hierarchy of bullet points. The audience follows a story. They file away a deck.

The script is a rehearsal document, not a teleprompter. If it sounds like reading, rewrite it until it sounds like telling.
