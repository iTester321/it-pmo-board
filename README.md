# IT PMO Project Board

[![CI](https://github.com/iTester321/it-pmo-board/actions/workflows/ci.yml/badge.svg)](https://github.com/iTester321/it-pmo-board/actions/workflows/ci.yml)
[![Deploy](https://github.com/iTester321/it-pmo-board/actions/workflows/pages.yml/badge.svg)](https://github.com/iTester321/it-pmo-board/actions/workflows/pages.yml)

A single-file Kanban board for a fictitious bank's internal IT PMO. It is a demo and training tool built with vanilla HTML, CSS and JavaScript.

**Live demo:** https://itester321.github.io/it-pmo-board/

## Features

- Kanban columns with drag-and-drop, plus a keyboard-accessible "Move" menu
- Add tasks through a dialog, with validation
- Filter by project, category and priority, with a summary bar
- Overdue tasks flagged with a text badge
- Inline delete confirmation
- Optional email notification for new tasks through FormSubmit
- Accessible: colour is never the only signal, and focus is restored after re-render

## Constraints

- No frameworks, bundler, npm, CDN scripts, web fonts or image files
- Works from `file://` with no server
- No persistence: a refresh resets the board to seed data
- No real bank logo or trademarks

## Usage

Open `index.html` in a browser, or run `open index.html` on macOS. There is no build step.

## Configuration

Set `FORMSUBMIT_ENDPOINT` at the top of the script in `index.html` to receive an email when a task is added:

```js
const FORMSUBMIT_ENDPOINT = "https://formsubmit.co/ajax/YOUR_EMAIL@example.com";
```

FormSubmit needs a one-time activation: the first submission sends a confirmation email, and delivery starts after you click its link. If notification fails, the board keeps working.

Do not commit a real personal or corporate email address if the repo is public.

## Project structure

```
index.html                    The whole app (markup, styles, script)
CLAUDE.md                     Architecture notes for Claude Code
.github/workflows/ci.yml      Checks and secret scan
.github/workflows/pages.yml   Deploys to GitHub Pages
```

## Development

State lives in a single `state` object and the board re-renders after every action. See [CLAUDE.md](CLAUDE.md) for the architecture and conventions.

CI checks that `index.html` has no external resources and no `!important`, and runs a secret scan.

## Contributing

Issues and pull requests are welcome. Keep to the constraints above.
