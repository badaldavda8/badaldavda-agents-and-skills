---
name: narrate-architecture
description: Understand a system you did not build by asking AI to narrate what happens to a single request from entry to exit. Use when diagrams are not enough — when you need to understand behaviour, not just structure. Diagrams show you what exists. Narration shows you what happens.
---

# narrate-architecture

Follow one request through the entire system. Every decision point. Every handoff. Every place it could go wrong.

## When to use

- You have inherited a system and need to understand it before changing anything
- You have a diagram but it does not tell you what happens under load or failure
- You are preparing for a customer architecture review
- You want to find the weak points in a design before they find you

## How to invoke

```
/narrate-architecture [system or codebase]
```

Example:
```
/narrate-architecture the order processing service in this repo
```

## What happens

1. User points AI at the system — a codebase, a diagram, an architecture doc, or a description
2. AI picks a single representative request (or asks the user which one to follow)
3. AI narrates the journey of that request from the moment it arrives:
   - What receives it first?
   - What decision gets made, and on what basis?
   - Where does it go next, and what could go wrong at the handoff?
   - What happens at each service, queue, or database it touches?
   - Where does it end, and how does the caller know it succeeded?
4. At every decision point, AI names: what happens in the happy path, and what happens when it does not

## The prompt to use directly

> "Walk me through this architecture flow by flow, like you are narrating what happens to a single request from the moment it arrives. Tell me every decision point, every handoff, every place something could go wrong."

## Why narration, not diagrams

Diagrams show structure. Narration shows behaviour.

A diagram does not tell you what happens when the queue backs up. A narrated story does — because you have to say what happens next. The moment the narration gets vague or hand-wavy is the moment the architecture has a gap you should know about.
