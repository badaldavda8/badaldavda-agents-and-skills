# explain-like-a-story

Explain any concept as a story in a made-up world — and use where the story breaks down to find where your understanding does too.

## Why this exists

Definitions tell you what something is called. Stories force you to follow what it actually does. I kept reading explanations of distributed systems and understanding them right up until I needed to apply them. Putting a concept inside a narrative — with characters who have stakes — means you cannot stay passive. When the story gets vague or strained, that strain is pointing at the gap.

## Install

```bash
cp skills/explain-like-a-story/SKILL.md ~/.claude/commands/explain-like-a-story.md
```

## Usage

```
/explain-like-a-story [concept]
```

Examples:
```
/explain-like-a-story distributed consensus
/explain-like-a-story TLS handshake
/explain-like-a-story eventual consistency
```

## Example output

> **Distributed consensus — in a village that cannot use messengers**
>
> Three elders must agree on the harvest date. A date is confirmed only if two of the three elders announce they heard the same date from at least one other elder. Elder A proposes the 14th. Elder B repeats it. Elder A announces confirmed. Elder C, who was asleep, wakes up and hears two confirmed — that is her quorum.
>
> **The mapping:** Elders are nodes. The two-confirmation rule is the quorum.
>
> **Where the story strains:** What if Elder A dies after proposing but before confirming? That awkwardness is the leader election problem.

## See also

- [narrate-architecture](../narrate-architecture/) — when the concept is a real system to follow through
- [starter-guide](../starter-guide/) — when one story is not enough and someone needs a full onboarding path
