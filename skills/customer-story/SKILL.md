---
name: customer-story
description: Understand a customer's business before walking into a room by asking AI to reconstruct the founding story — who saw the problem first, why they could not stop thinking about it, and how it became what it is today. Use when a company overview gives you facts but you need understanding.
---

# customer-story

Get the founding story, not the company profile.

## When to use

- You are preparing for a customer meeting and want to ask better questions than their tech stack
- You are starting a new engagement and need to understand what the business is actually *for*
- You want to know what they are proud of, what they are still trying to prove, and what keeps the founders awake

## How to invoke

```
/customer-story [company name or URL]
```

Example:
```
/customer-story Stripe
```

## What happens

1. User provides a company name, website, or brief description
2. AI researches and constructs the founding story:
   - Who founded it, and what problem did they personally run into?
   - Why did that problem matter enough to leave whatever they were doing?
   - What did the first version of the solution look like?
   - What were the key turns, pivots, near-deaths?
   - The moment it stopped being a bet and started being a business
3. If the founding story is publicly documented — named founder, known origin, documented pivot — AI grounds it there
4. If not, AI reasons backward from the product: what problem does this solve so specifically that someone must have lived it first? AI constructs the most plausible story from the website, product, and services
5. AI closes with two things:
   - What this tells you: what they are proud of, what they are still trying to prove, what failure they never talk about
   - Two specific questions to ask in the room that signal you understand *why* the business exists, not just what it does. Questions that reference the founding problem, not the product features.
6. If multiple origin stories are plausible, rank by evidence and say so — do not present a constructed story as fact

## The prompt to use directly

> "Tell me the real story of how this company came to exist. Who founded it, what problem did they personally run into, why did that problem matter enough to leave whatever they were doing, and what did the first version of their solution look like? Then tell me how it became what it is today — the turns, the pivots, the moment it stopped being a bet and started being a business. If the founding story is not publicly documented, look at their website, their product, their services — and construct the most plausible version of the story that fits what they built. Make it digestible. Tell it like a story, not a profile."

## Why the constructed version is still useful

When AI has to reason from what the product actually solves back to the person who must have needed it first — that reasoning is understanding. A company summary gives you facts. A founding story, real or reconstructed, tells you what the business is *for*.

When you know why something was built, you understand its architecture — technical and organisational — in a way no product page explains. And when you ask the founder about the problem that started everything, watch what happens to the room.
