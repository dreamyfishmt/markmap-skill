# Markmap Syntax Skill

A reusable skill for writing, repairing, and explaining Markdown mind maps rendered with Markmap. It helps an AI coding assistant turn content into a clear hierarchy and handle Markmap-specific syntax without losing the user's intended content or structure.

## What it covers

- Topic hierarchies built from headings and nested lists.
- Repairing escaping and broken links introduced by rich-text copying.
- Frontmatter options for branch colors, node width, and initial expansion.
- Rich text, task items, links, math, code blocks, tables, and images.
- Folding nodes with `fold` and `foldAll` comments.
- Source checks and visual verification when a renderer is available.

This skill is for Markmap, not Mermaid or general Markdown formatting. It provides instructions and an example; it does not bundle a renderer.

## Installation

Copy the entire [`skills/markmap-syntax`](skills/markmap-syntax) folder into your assistant's skills directory, keeping the `references` subfolder alongside `SKILL.md`.

For Codex, use `$CODEX_HOME/skills`, or `~/.codex/skills` when `CODEX_HOME` is unset. The installed layout should be:

```text
skills/
└── markmap-syntax/
    ├── SKILL.md
    └── references/
        └── example.md
```

## Usage

Invoke the skill by name in your prompt, for example:

```text
Use $markmap-syntax to turn these project notes into a Markmap mind map.
```

Other example requests:

- "Use $markmap-syntax to repair this Markdown copied from a rich-text editor. Preserve the LaTeX formulas."
- "Use $markmap-syntax to adjust this mind map's hierarchy to match the attached screenshot."
- "Use $markmap-syntax to wrap long node text and fold the detailed branches initially."

The output is Markdown source for a Markmap-compatible renderer. Formula, image, and highlighting support depends on the rendering environment.

## Example

```markdown
---
title: Project Overview
markmap:
  colorFreezeLevel: 2
---

## Goals

- Share reusable knowledge
- Make mind maps easier to maintain

## Tasks

- [x] Define the scope
- [ ] Write documentation
- Details <!-- markmap: fold -->
  - Review examples
  - Check the rendered map
```

For a broader example with formulas, code, tables, and images, see [`references/example.md`](skills/markmap-syntax/references/example.md). The full instructions are in [`SKILL.md`](skills/markmap-syntax/SKILL.md).

## License

[MIT](LICENSE).
