---
name: debug-deep
description: Break out of a troubleshooting loop by giving AI a structured search order — code first, then official docs, then community forums — before it suggests anything. Use when AI keeps rephrasing the same fix or when you suspect the answer is in documentation that AI skipped.
---

# debug-deep

Force AI to do the reading before it does the talking.

## When to use

- AI has suggested three variations of the same fix and none have worked
- You are debugging a library, framework, or cloud service issue
- You want to know *why* something is broken, not just what to change
- You suspect the issue is a known bug or version-specific behaviour

## How to invoke

```
/debug-deep [describe the problem]
```

Example:
```
/debug-deep Node 20 upgrade broke cold start times in production
```

## What happens

1. User describes the problem — error message, what was changed, what has been tried
2. AI works through the search order before suggesting anything:
   - **Step 1 — The code:** Read the relevant code. What does it actually do? Any obvious mismatches with the expected behaviour?
   - **Step 2 — Official documentation:** Check the official docs for this library/service/version. Is this behaviour documented? Any version-specific notes?
   - **Step 3 — Reddit** *(if accessible):* Search for this error or behaviour pattern. Any community reports of the same issue?
   - **Step 4 — Community forum** *(if applicable):* GitHub Discussions, Stack Overflow, Reddit, or the platform vendor's own forum. Check for known issues and support threads on this exact problem.
   - If the problem is version-specific: repeat steps 1–2 for the previous stable version to determine whether this is a regression.
3. AI reports what it found at each step *before* making a recommendation
4. Recommendation comes last, grounded in what was actually found

## The prompt to use directly

> "Before suggesting another fix: check the actual code first, then the official documentation, then Reddit or the relevant community forum for known issues with this version. Tell me what you find at each step before recommending anything."

## Why the word "before" matters

Without it, AI skips straight to a suggestion. The suggestion is often plausible but ungrounded — it is pattern-matching to similar-sounding problems, not reading the actual code or docs. The word *before* forces the work to happen in the right order. Half the time, the answer is in the documentation that would have been skipped.
