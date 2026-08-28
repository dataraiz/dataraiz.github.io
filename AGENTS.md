# AGENTS.md

## What this is

Static HTML site for **DATARAIZ** (dataraiz.github.io), hosted on GitHub Pages. No build step, no bundler, no package manager, no linter, no tests.

## Key files

- `index.html` — Main event page ("Ciclo Negro"). All content lives here.
- `maqueta-update.html` — Draft/staging page for prototyping new sections from Figma. Marked `noindex,nofollow`.
- `styles/ciclo-negro.css` — Primary stylesheet (~5700 lines, exported from Webflow or similar).
- `styles/fonts.css` — Font-face declarations.
- `styles/site.css` — Additional site styles (used by `maqueta-update.html`).
- `styles/maqueta-update.css` — Draft page-specific styles.
- `assets/images/` — All images; `assets/images/raw/` for source files.
- `mcp.json` — Figma MCP server integration.

## Bilingual system

Content is bilingual (Spanish default, English). Controlled via CSS, not multiple files:

- `body[data-lang="es"]` hides `.lang-en`, shows `.lang-es`.
- `body[data-lang="en"]` hides `.lang-es`, shows `.lang-en`.
- Language toggle is inline JS at the bottom of `index.html` (button `.lang-switch__btn`).

**When adding content**, wrap text in both `<span class="lang lang-es">` and `<span class="lang lang-en">` elements. Both must be present even if identical.

## Content pattern

Sections use a consistent structure: `.cintillo-title-cn` (eyebrow + heading), then descriptive content. CSS class names are Webflow-style (verbose, non-semantic). Match existing patterns when adding sections.

## Gotchas

- CSS was likely exported from a design tool — class names are non-descriptive and extremely long. Don't rename them; add new classes for new elements.
- No `.editorconfig` or formatting config — match the indentation of the file you're editing (2-space indent).
- `maqueta-update.html` is not linked from the main site and is not indexed. Use it freely for iteration.
- The Figma MCP server in `mcp.json` is available for design-to-code workflows.
