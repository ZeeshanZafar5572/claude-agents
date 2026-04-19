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

**Commit and push continuously throughout every session — never leave work uncommitted.**

Rules:
- Commit after every meaningful unit of work (new file, feature added, bug fixed, content updated).
- Always push immediately after committing so the remote reflects current state.
- Never batch up multiple sessions of work into one commit.
- A task is not done until the commit is pushed to GitHub.

```bash
git add <changed-files>
git commit -m "short present-tense summary of what changed and why"
git push
```

Commit message format: one concise subject line describing *what* and *why* (not *how*). Examples:
- `Add snake game with high score persistence`
- `Fix bullet collision not registering on tank enemy`
- `Update colour palette to match dark-space theme`

GitHub remote: `https://github.com/ZeeshanZafar5572/claude-agents`  
Git identity: name `ZeeshanZafar5572`, email `zeeshan.zafar@seamlessideas.co.uk`

When adding a new project, create the `.html` file, commit, and push before reporting the task as complete.
