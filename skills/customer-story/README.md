# customer-story

Get the founding story of a business before you walk into the room — real if documented, reconstructed from first principles if not.

## Why this exists

A company profile gives you facts. A founding story gives you understanding. Before I had this skill I'd walk into customer meetings knowing the product but not the *reason* — and my questions showed it. The skill reasons backward from what a company built to who must have needed it first, then closes with two questions that signal you understand why the business exists, not just what it does.

## Install

```bash
cp skills/customer-story/SKILL.md ~/.claude/commands/customer-story.md
```

## Usage

```
/customer-story [company name or URL]
```

Examples:
```
/customer-story Stripe
/customer-story https://www.hashicorp.com
```

## Example output

> **The story of Stripe**
>
> Patrick and John Collison were developers who ran into the same wall anyone building on the internet hit in 2010: accepting payments required weeks of bank paperwork and hundreds of lines of bespoke integration code. The problem was personal.
>
> **What this tells you:** Stripe is still, fundamentally, a company that believes infrastructure should not require lawyers. They are proud of the API. They are still trying to prove that a genuinely good developer experience can exist inside financial services.
>
> **Two questions to ask in the room:**
> 1. "When you first tried to move payment processing in-house, what surprised your team most about what had to be rebuilt from scratch?"
> 2. "What is the last thing your developers had to ask finance to unblock?"

## See also

- [grill-me](../grill-me/) — pressure-test your own assumptions before walking in
