# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

## Repository Purpose

This is a collection of browser-based games and web projects, each delivered as a **single self-contained HTML file** with no build step, no dependencies, and no bundler. Open any `.html` file directly in a browser to run it.

## Projects

| File | Description |
|---|---|
| `tictactoe.html` | 2-player Tic Tac Toe with score tracking |
| `shooter.html` | Top-down shooter "Void Strike" — waves, 3 enemy types, particles, Web Audio |

## Design Conventions

**Visual style** — all projects share a dark-space palette:
- Background: `#1a1a2e` / `#0d0d1a`
- Accent pink: `#e94560`, accent cyan: `#53d8fb`, amber: `#f5a623`
- Deep blue borders/panels: `#0f3460`, `#16213e`

**Single-file structure** — CSS in `<head>`, all JS in one `<script>` tag at the bottom of `<body>`. No external fonts, libraries, or CDN links.

**Canvas games** use `requestAnimationFrame` with a delta-time game loop capped at 100ms (`Math.min(dt, 0.1)`) to prevent spiral-of-death after tab unfocus.

**Audio** — synthesized via Web Audio API (no audio files). Always wrap `AudioContext` creation in try/catch and initialise on first user interaction.

**Persistence** — use `localStorage` for scores/state that should survive page refresh.

## Git Workflow

Every project is tracked in this repo. After each meaningful change:

```bash
git add <file>
git commit -m "descriptive message"
git push
```

GitHub remote: `https://github.com/ZeeshanZafar5572/claude-agents`
Git identity: `ZeeshanZafar5572` / `zeeshan.zafar@seamlessideas.co.uk`

When adding a new project, create it as a new `.html` file and commit it before considering the task done.
