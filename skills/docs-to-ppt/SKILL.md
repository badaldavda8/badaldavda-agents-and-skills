---
name: docs-to-ppt
description: Read documents and produce a presentation. Marp for simple internal slides. HTML for complex, visual, or high-stakes presentations — especially when Mermaid diagrams are needed. Use when you have technical content that needs to become slides without opening PowerPoint.
---

# docs-to-ppt

Turn documents into slides. Format follows purpose.

## Format decision

| Use Marp when | Use HTML when |
|---|---|
| Internal audience | Customer, leadership, or external audience |
| Fast turnaround | Visuals and aesthetics matter |
| No diagrams, or simple ones | Mermaid diagrams needed |
| Content changes frequently | High-stakes or formal presentation |
| Slides live in Git with code | You want full design control |

If unsure, pass `auto` — AI recommends based on audience and purpose.

## How to invoke

```
/docs-to-ppt [path] [purpose] [audience] [format: marp|html|auto]
```

Examples:
```
/docs-to-ppt ./docs/ "platform overview for new engineers" "internal team" marp
/docs-to-ppt ./architecture.md "architecture review" "customer CTO" html
/docs-to-ppt ./docs/ "conference talk on GitOps" "external" auto
```

## Opening questions

1. What is the purpose? (inform / persuade / onboard / review)
2. Who is the audience? What do they already know?
3. How many slides? (target — fewer is better)
4. Are there diagrams or flows that need to be shown? → HTML
5. What should the audience do or understand after the last slide?
6. Anything to exclude? (customer names, in-progress work)

---

## Marp track

Simple, fast, version-controlled.

### Output structure

```markdown
---
marp: true
theme: default
paginate: true
size: 16:9
---

# Title
Subtitle or context

---

## Section title

- Point — fragment, not a sentence
- Point
- Point

> Callout for the single most important detail

<!-- Speaker note: what to say, not what the slide repeats -->
```

### Rules

- One idea per slide
- Bullets are fragments — speaker completes them
- Diagram placeholders: `<!-- DIAGRAM: describe what it shows -->`
- Speaker notes for the speaker, not a repeat of the slide

### Install

```bash
# VS Code: "Marp for VS Code" extension → open .md → Marp icon
npm install -g @marp-team/marp-cli
marp slides.md --pdf
marp slides.md --html
```

---

## HTML track

For visuals, diagrams, and high-stakes presentations.

### Why HTML over Marp for diagrams

Mermaid renders in HTML via `mermaid.js`. A self-contained `.html` file embeds the library, renders diagrams at load time, and runs in any browser with no dependencies. Marp requires a separate rendering step and does not natively support interactive or animated diagrams.

### Output structure

A single self-contained `.html` file. Slide types:

```
Title slide      — headline, subtitle, speaker name
Divider slide    — one word or phrase, full-bleed colour, signals new section
Content slide    — headline + 2–3 bullets max, or one diagram
Callout slide    — one sentence, large, centred — for the most important moment
Diagram slide    — full-slide Mermaid diagram with a one-line caption
Closing slide    — one takeaway + what to do next (not "thank you")
```

### Mermaid diagrams

AI renders Mermaid inline using the CDN-free embedded library:

```html
<div class="mermaid">
flowchart LR
    A[Input] --> B{Decision}
    B -->|Yes| C[Outcome A]
    B -->|No| D[Outcome B]
</div>
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs'
  mermaid.initialize({ startOnLoad: true, theme: 'dark' })
</script>
```

For fully offline use, AI will inline the Mermaid library as a base64 data URI.

### Design rules

- One focal point per slide — if the eye has nowhere to land, simplify
- One accent colour, used sparingly
- Dark or light theme — pick one, stay consistent
- Animations only if they add meaning — reveals are fine, spinning logos are not
- Code blocks get syntax highlighting via embedded `highlight.js`

### Navigation

```html
<!-- Arrow keys + spacebar, built into every HTML output -->
<script>
  document.addEventListener('keydown', e => {
    if (e.key === 'ArrowRight' || e.key === ' ') nextSlide()
    if (e.key === 'ArrowLeft') prevSlide()
  })
</script>
```

Presenter mode: open `index.html?presenter` in a second window for speaker notes.

---

## Rules for both formats

- No customer names, organisation names, or identifying details — use "the platform", "the team"
- Story arc, not document structure — opening → problem → journey → resolution → close
- One idea per slide
- Closing slide: a concrete next action or a question worth carrying away — not "thank you"
