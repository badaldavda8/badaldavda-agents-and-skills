---
name: starter-guide
description: Read documents and produce a starter guide for someone picking up this system, topic, or codebase for the first time. Use when onboarding a new team member, handing off a project, or making complex technical material accessible to someone with no prior context. A starter guide is not a reference doc. It is a curated path through existing knowledge, written to answer the questions a new person will ask before they know the right questions to ask.
---

# starter-guide

Read the docs. Write the guide a new person actually needs.

## When to use

- A new engineer is joining the team and the docs exist but nobody has time to walk them through it
- You are handing off a project and want the next person to get up to speed without you
- You have comprehensive technical documentation but no entry point for someone unfamiliar with the system
- You want to test your own understanding of a system by having AI produce an explanation you can review

## How to invoke

```
/starter-guide [path to docs or folder] [audience] [depth]
```

Examples:
```
/starter-guide ./docs/ "engineer new to the platform, comfortable with backend basics" "day-1 onboarding"
/starter-guide ./architecture/ "technical lead joining mid-project" "full system overview"
```

## Opening interview

1. **Who is this guide for?** What do they already know? What can you assume, and what must be explained?
2. **What should they be able to do after reading it?** Answer questions in a meeting? Make a change safely? Review a PR? Be specific.
3. **What are the three questions every new person asks?** These become the guide's spine.
4. **What is the most common mistake a new person makes?** The guide should prevent it without making the reader feel warned.
5. **What can be left out?** A starter guide is not the full docs. What is not needed on day one?

## What happens

1. AI reads all documents in full
2. AI identifies: the mental model someone needs before any detail makes sense, the three to five concepts that explain everything else, the most confusing part (where the docs assume knowledge the reader does not have), and the most common failure mode for a new person
3. AI produces a starter guide in this structure:

```
## What this system is for
One paragraph. The job of the system in plain language. No jargon until it is introduced.

## The mental model
The one picture or analogy that makes the rest make sense.
Not a diagram — a sentence or two that frames everything that follows.

## The three things to understand first
Each explained in plain language, with why it matters before how it works.

## How the pieces fit together
A walk-through of the system as a story — what happens when something enters, what decisions are made, where it ends up.

## What you will do on day one
Concrete. Specific. Ordered. Not "explore the codebase" — "read these three files in this order, then run this command, then you will understand X."

## What to do when something goes wrong
The two or three most common problems a new person hits, and what to check first.

## Where to go next
Pointers to the deeper docs, by question — "if you need to change X, read Y".
```

## Rules

- **No customer names, organisation names, or identifying details.** Refer to "the platform", "the system", "the team".
- **Jargon must be introduced before it is used.** Every acronym spelled out once. Every concept named before it is assumed.
- **The mental model comes before the detail.** A new person cannot absorb detail without a frame. The frame goes first.
- **Day one tasks are concrete.** "Read the README" is not a task. "Run `make dev-setup` and read the output" is a task.
- **The guide earns trust by being honest about what is hard.** "This part is confusing until you have seen it once" is more useful than pretending it is simple.
- **Length target: readable in 20 minutes.** A starter guide that takes an hour to read is not a starter guide. It is the docs with a different title.

