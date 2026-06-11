---
name: grill-me
description: Break the yes-person dynamic by having AI ask relentless clarifying questions instead of giving answers. Use when you want to pressure-test an idea, surface hidden assumptions, or think through something you have not fully worked out yet. When AI asks you a question, you have to think. When AI gives you an answer, you often do not.
---

# grill-me

AI asks you questions. You answer. Repeat until every assumption is on the table.

## When to use

- You have an idea or plan you want to stress-test before committing
- You suspect you have assumptions you have not named yet
- You keep getting answers that feel too agreeable
- You are about to start a long AI session and want to set the right dynamic from the start

## How to invoke

```
/grill-me [topic or plan]
```

Example:
```
/grill-me my plan to migrate this monolith to microservices
```

## What happens

1. User describes the idea, plan, or topic in a sentence or two
2. AI asks one clarifying question — just one, not a list
3. User answers
4. AI asks the next question, drilling into whatever the answer revealed
5. Continue until the user says stop, or until AI has surfaced the core assumptions
6. At the end, AI summarises: "Here are the assumptions your plan depends on..."

## Rules

- AI asks questions. It does not give advice, suggestions, or answers unless asked.
- One question at a time. Lists of questions let the user skip the hard ones.
- Questions get harder as the session goes on — start broad, narrow toward the thing the user is least certain about.
- If the user's answer reveals a contradiction or a gap, name it as a question: "You said X earlier and just said Y — which is the one you are more confident in?"
- If an answer is vague or evasive, do not move on. Reframe: "Let me ask that differently..." — stay on the same branch until it resolves.

## The prompt to use directly

> "Keep asking me clarifying questions about [topic] until I tell you to stop. One question at a time. Do not give me answers or suggestions — only questions. Make them harder as we go."

## Credit

I used a version of this for years before I found out Andrej Karpathy had formalised it as a skill with the same name. His version is cleaner. The instinct was the same: when AI asks you a question, you have to think.

Karpathy's version: [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills). His implementation is tighter and worth reading alongside this one.
