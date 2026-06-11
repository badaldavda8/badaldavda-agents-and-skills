---
name: debug-deep
description: Break out of a troubleshooting loop by giving AI a structured search order — code first, then official docs, then Reddit, then AWS re:Post — before it suggests anything. Use when AI keeps rephrasing the same fix or when you suspect the answer is in documentation that AI skipped.
---

# debug-deep

Force AI to do the reading before it does the talking.

## When to use

- AI has suggested three variations of the same fix and none have worked
- You are debugging a library, framework, or AWS service issue
- You want to know *why* something is broken, not just what to change
- You suspect the issue is a known bug or version-specific behaviour

## How to invoke

```
/debug-deep [describe the problem]
```

Example:
```
/debug-deep Lambda cold starts spiking after upgrading to Node 20 runtime
```

## What happens

1. User describes the problem — error message, what was changed, what has been tried
2. AI works through the search order before suggesting anything:
   - **Step 1 — The code:** Read the relevant code. What does it actually do? Any obvious mismatches with the expected behaviour?
   - **Step 2 — Official documentation:** Check the official docs for this library/service/version. Is this behaviour documented? Any version-specific notes?
   - **Step 3 — Reddit:** Search for this error or behaviour pattern on Reddit. Any community reports of the same issue?
   - **Step 4 — AWS re:Post** *(if AWS service):* Check re:Post for known issues, service-specific quirks, or AWS support threads on this exact problem.
3. AI reports what it found at each step *before* making a recommendation
4. Recommendation comes last, grounded in what was actually found

## The prompt to use directly

> "Before suggesting another fix: check the actual code first, then the official documentation, then Reddit for known issues with this version, then AWS re:Post if this is an AWS service problem. Tell me what you find at each step before recommending anything."

## Why the word "before" matters

Without it, AI skips straight to a suggestion. The suggestion is often plausible but ungrounded — it is pattern-matching to similar-sounding problems, not reading the actual code or docs. The word *before* forces the work to happen in the right order. Half the time, the answer is in the documentation that would have been skipped.
