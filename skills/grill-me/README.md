# grill-me

Break the yes-person dynamic — AI asks relentless clarifying questions one at a time until every assumption in your plan is on the table.

## Why this exists

When AI gives you answers, you can agree without thinking. When AI asks you questions, you have to think. I kept finishing AI sessions feeling like my ideas had been validated, then having them fall apart in the first real conversation. This skill flips the dynamic: no answers, only questions, and they get harder as you go. Andrej Karpathy formalised the same instinct first — credit to his [grill-me](https://github.com/multica-ai/andrej-karpathy-skills).

## Install

```bash
cp skills/grill-me/SKILL.md ~/.claude/commands/grill-me.md
```

## Usage

```
/grill-me [topic or plan]
```

Examples:
```
/grill-me my plan to migrate this monolith to microservices
/grill-me the rollout strategy for this new API version
```

## Example output

> **AI:** You said the migration will take three months. What is that estimate based on?
>
> **You:** Previous migrations of similar size.
>
> **AI:** How similar? Did those systems have the same number of downstream consumers?
>
> **You:** Fewer, actually.
>
> **AI:** You just said this one has more consumers. What happens to the three-month estimate if each consumer team needs two weeks to update their integration?
>
> *(At the end)*
> **Assumptions your plan depends on:**
> - Downstream teams update integrations in parallel, not sequentially
> - No consumer depends on undocumented side-effects of the monolith
> - The team has capacity to support consumers during the transition window

## See also

- [customer-story](../customer-story/) — stress-test assumptions before a customer meeting specifically
