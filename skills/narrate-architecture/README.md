# narrate-architecture

Understand a system by following a single request through it — every decision point, every handoff, every place it could go wrong.

## Why this exists

Diagrams show structure. They do not show behaviour. I kept inheriting systems where the diagram was accurate and still not enough — it did not tell me what happened when the queue backed up, which service did the auth check, or why a specific failure mode was silent. Following one real request through the whole system reveals what no box-and-arrow diagram does.

## Install

```bash
cp skills/narrate-architecture/SKILL.md ~/.claude/commands/narrate-architecture.md
```

## Usage

```
/narrate-architecture [system or codebase]
```

Examples:
```
/narrate-architecture the order processing service in this repo
/narrate-architecture [paste architecture description]
```

## Example output

> **Request: a customer submits a new order**
>
> Arrives at API Gateway. First decision: is the JWT valid? If not, 401 — no downstream call is made. This is the only auth check in the path.
>
> The API server forwards to the order service. It writes to the database with status `PENDING`, publishes an event to the message queue, and returns 202 immediately — accepted, not yet processed.
>
> The queue routes to the fulfillment service. **Decision point:** inventory available? Yes → `CONFIRMED`. No → `BACKORDER`. The caller already received 202. They will not know the order is in backorder unless they poll. That is a silent failure from the customer's perspective.

## See also

- [debug-deep](../debug-deep/) — when the narration reveals a bug and you need to dig into it
- [explain-like-a-story](../explain-like-a-story/) — when the system is abstract and needs a conceptual frame first
