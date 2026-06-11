---
name: explain-like-a-story
description: Explain any concept as a story in a made-up world. Use when you want to actually understand something, not just know it. Textbook summaries tell you the definition. A story forces you to follow the shape of the idea — and when the story breaks down, that is where your understanding has a gap.
---

# explain-like-a-story

Explain a concept by building a story around it in a fictional world, with characters and stakes that mirror the real mechanics.

## When to use

- You have read the definition three times and it still does not stick
- You need to explain a technical concept to a non-technical stakeholder
- You want to find the edges of your own understanding (where the story breaks down = where the gap is)

## How to invoke

```
/explain-like-a-story [concept]
```

Or describe it in plain language:

```
/explain-like-a-story distributed consensus
```

## What happens

1. Ask the user what concept they want to understand
2. Ask: "Any world or setting that would make this fun? (space, village, restaurant kitchen, medieval kingdom — anything goes)"
3. If no preference, pick a setting that maps naturally to the concept's mechanics
4. Tell the story — characters, problem, the mechanics of the solution playing out through the narrative
5. At the end, surface the mapping: "The strangers trying to agree on dinner = the nodes. The moment two of them confirm with a third = the quorum..."
6. Ask: "Where did the story feel shaky or forced? That is probably where you want to dig next."

## The prompt to use directly

> "Explain [concept] as a story in a made-up world. Give it characters, a problem they have to solve, and let the mechanics of [concept] be the way they solve it. If the metaphor breaks down at any point, tell me where and why."

## Why it works

The made-up world forces the model to find the actual shape of the idea rather than recite the definition. Following a narrative is harder to do passively than scanning a list — you have to track what is happening. And when the story stops making sense, that is a signal, not a failure. That is where the next question lives.
