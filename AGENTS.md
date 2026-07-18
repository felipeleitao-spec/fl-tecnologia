# Repository Guidelines

## Project Structure & Module Organization

This repository currently contains a static, single-page website for FL Tecnologia.

- `src/index.html` contains semantic markup, navigation anchors, copy, and links.
- `src/css/styles.css` contains global styles, CSS custom properties, responsive rules, and component classes.
- No separate `assets/`, `js/`, `tests/`, or build directories exist yet. If images or scripts are added, place them under `src/assets/` or `src/js/` and reference them from `index.html`.
- `.codex/` and `.agents/` are local agent metadata directories and should not be treated as application source.

## Build, Test, and Development Commands

There is no package manager or build pipeline configured. Use simple static-site commands:

- `python3 -m http.server 8000 -d src` starts a local server at `http://localhost:8000`.
- `xdg-open src/index.html` opens the page directly on Linux desktops.
- `find . -maxdepth 2 -type f` quickly confirms the small project layout.

Add `package.json` only when introducing Vite, linting, formatting, or automated tests.

## Coding Style & Naming Conventions

- Keep HTML semantic and readable: use sections, descriptive headings, and meaningful anchor IDs such as `#contato` and `#como`.
- Preserve two-space indentation in HTML and CSS.
- Keep CSS custom properties in `:root` for shared colors, spacing, and sizing.
- Use lowercase, hyphenated class names for new CSS selectors, for example `.contact-list` or `.offer-box`.
- Keep styling in `src/css/styles.css`; avoid inline `<style>` blocks unless an external embed requires it.
- The site content is Portuguese (`lang="pt-BR"`), so new visible copy should also be Portuguese unless there is a product reason to differ.

## Testing Guidelines

No automated tests are configured. Before submitting changes:

- Preview the page locally with `python3 -m http.server 8000 -d src`.
- Check desktop and mobile widths, especially the hero, cards, CTA buttons, and contact links.
- Validate that all internal anchors and external links still work.
- For larger changes, consider adding a lightweight browser test setup such as Playwright.

## Commit & Pull Request Guidelines

This checkout does not expose usable Git history, so no existing commit convention can be inferred. Use concise, imperative commit messages, for example `Update contact CTA copy` or `Add responsive asset styles`.

Pull requests should include a short description, screenshots for visual changes, notes on manual browser checks, and any linked issue or requested business context.

## Agent-Specific Instructions

Keep changes focused. Do not introduce frameworks, build tooling, or new directories unless the task clearly requires them.
