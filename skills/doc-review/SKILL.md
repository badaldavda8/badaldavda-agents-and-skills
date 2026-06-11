---
name: doc-review
description: Review a document, essay, or piece of writing for clarity, structure, accuracy, and purpose. Use when you want a critical editorial eye — not encouragement. Not a grammar check. A review that tells you what is not working and exactly how to fix it.
---

# doc-review

Critical review of any document. What is not working and how to fix it.

## When to use

- You have a draft and want honest feedback before sharing it
- A document exists but readers keep misunderstanding it
- You want to know if the structure serves the purpose
- You suspect something is off but cannot name it

## How to invoke

```
/doc-review [path or paste] [type] [audience]
```

Examples:
```
/doc-review ./essay.md personal-essay general
/doc-review ./architecture-doc.md technical-doc engineering-team
/doc-review ./starter-guide.md onboarding-guide new-engineers
```

Types: `personal-essay` | `technical-doc` | `onboarding-guide` | `talk-script` | `proposal` | `general`

## Opening questions

1. Who is the intended reader? What do they know, what do they care about?
2. What should the reader do or understand after finishing?
3. What is the one thing you are most unsure about in this document?

## What AI checks — by dimension

### 1. Purpose
- Is there one clear job this document does? Or is it trying to do several?
- Does the opening tell the reader why they should keep reading?
- Does the closing confirm what the reader should now know or do?

### 2. Structure
- Does the order of sections follow the reader's logic, not the writer's?
- Is there a section that could move without breaking the document?
- Is there a section that exists only because the writer needed to say it?
- Does each section earn its place — does removing it change anything for the reader?

### 3. Clarity
- Find the three most confusing sentences. What makes them hard?
- Find the three longest paragraphs. Does the length serve the idea or just fill space?
- Are any terms used before they are defined?
- Is any jargon used that the target reader would not know?

### 4. Accuracy (for technical docs)
- Are any claims stated without evidence or sourcing?
- Are any numbers or statistics cited without a reference?
- Are any commands, configs, or code snippets verifiable?
- Is anything stated as fact that is actually an opinion or assumption?

### 5. Voice and trust
- Does it sound like a person or like a document?
- Is there any sentence that sounds generated rather than written?
- Are there any admissions of uncertainty or difficulty — or does it pretend everything is simple?
- Does it name the real cost of anything, or only the benefits?

### 6. What is missing
- What question does the reader have after finishing that the document does not answer?
- What is the most likely misunderstanding a new reader will form?
- Is there a section the writer avoided writing? That is often what the document needs most.

## Output format

```
## Review: [document title or path]
Reader: [who]
Purpose: [what it should do]

### What is working
[2–3 things — specific, not generic praise]

### What is not working
[Each issue: name it → why it matters → one specific fix]

### The most important fix
[Single highest-priority change — the one that changes the document most]

### What is missing
[What the reader will ask that the document does not answer]
```

## Rules

- Rate each dimension: STRONG / GOOD / NEEDS WORK
- Every weakness gets one specific fix — not a general suggestion
- No generic praise ("well-written", "clear structure") — specific observations only
- The most important fix is singular — one thing, not a list
- If a section should be cut, say so directly
