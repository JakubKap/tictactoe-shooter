# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview
- Two standalone HTML games in the project root: `game.html` (top-down shooter) and `tictactoe.html` (3x3 Tic Tac Toe).
- No build system — open any file directly in a browser. Git tracks both files in the `main` branch on GitHub at https://github.com/JakubKap/tictactoe-shooter.

## Common Git Workflows
- Start work: ensure you’re on `main` and run `git pull origin main`.
- Create feature work: make a descriptive branch (`git checkout -b feature/...`), commit with clear messages, and push with `git push -u origin <branch>`.
- Share changes: open a PR via GitHub UI; avoid interactive rebase/amend on shared branches.
- Save progress: commit often with concise messages; push to keep a remote backup.

## Running / Testing
- Open any `.html` file in a modern browser (double-click or `start <file>` on Windows).
- No automated tests; verify behavior manually in-browser (e.g., start game, move player, shoot, advance levels, reset).

## Architecture Notes (big picture)
- `game.html`: single-file app with separate game states (MENU, PLAYING, GAME_OVER). Uses Canvas 2D for rendering; game loop via `requestAnimationFrame`.
  - Player input: keyboard (Arrow/WASD) + mouse for aiming/shoot.
  - Entities: bullets (array), enemies (array with types basic/fast/tank), particles (decals/explosions), screen shake on hit.
  - Level progression: config-driven spawn counts/rates; increasing difficulty with tanks.
- `tictactoe.html`: classic 3x3 board with DOM-driven UI, win/draw detection, and restart.

## Conventions
- Keep changes focused; prefer editing existing files over adding new ones.
- Use descriptive commit messages; prefix with scope when helpful (e.g., `game: add enemy tank`).
- Coordinate with Git when making larger refactors to avoid merge conflicts.