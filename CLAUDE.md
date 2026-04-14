# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Marp presentation** about Compound Engineering (Every Inc.'s AI-native development methodology). It is not a software project — it contains slides, not application code.

## Files

- `slides.md` — Source presentation in Marp markdown format (French)
- `slides.html` — Generated HTML presentation (do not edit directly)

## Build

Generate the HTML from the markdown source using Marp CLI:

```bash
npx @marp-team/marp-cli slides.md -o slides.html
```

Preview with live reload:

```bash
npx @marp-team/marp-cli slides.md --preview
```

## Editing Guidelines

- All slide content is in French
- Slide separators are `---`
- Custom theme is defined in the YAML frontmatter (dark theme: `#1a1a2e` background, `#e94560` accent)
- After editing `slides.md`, regenerate `slides.html` before committing
