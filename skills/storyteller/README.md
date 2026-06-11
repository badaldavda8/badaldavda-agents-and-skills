# storyteller

Turn lived experience into a structured personal essay — interview first, anchor story, personal arc, research, edit, postscripts.

## Why this exists

I have been writing personal essays about technology and learning long enough that the process became repeatable. Interview before writing. Find the sentence you are most reluctant to say — that is usually what the essay is really about. Anchor the idea in a story from history or myth, then map your own experience onto that arc. This skill encodes that sequence, validated against how ten celebrated storytellers describe their own process.

## Install

```bash
cp skills/storyteller/SKILL.md ~/.claude/commands/storyteller.md
```

## Usage

```
/storyteller
```

Or pass your idea directly:

```
/storyteller I want to write about how I stopped trusting my own judgment when AI arrived and had to find my way back to it
```

The skill will interview you first — four questions, one at a time — before writing anything.

## Example output

*(After the interview — the opening of a draft essay)*

> Nobody talks about what Ekalavya did with his right hand after he gave away his thumb.
>
> The Mahabharata tells you about the thumb. Every retelling stops there — the dedication so complete that a student cut off his own finger to satisfy a teacher who had refused to teach him. That is the part that travels.
>
> What the text mentions briefly, almost as an afterthought: he kept practicing. With nine fingers. He became a better archer than he had been before.

## See also

- [doc-review](../doc-review/) — when the draft exists and needs an editorial pass
- [talk-script](../talk-script/) — when the story needs to become a talk, not an essay
