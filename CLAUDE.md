# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview
- Two standalone HTML games in the project root: `topdownshooter.html` (top-down shooter) and `tictactoe.html` (3x3 Tic Tac Toe).
- No build system — open any file directly in a browser or use a local web server. Git tracks both files in the `main` branch on GitHub at https://github.com/JakubKap/tictactoe-shooter.

## Common Git Workflows
- Start work: ensure you're on `main` and run `git pull origin main`.
- Create feature work: make a descriptive branch (`git checkout -b feature/...`), commit with clear messages, and push with `git push -u origin <branch>`.
- Share changes: open a PR via GitHub UI; avoid interactive rebase/amend on shared branches.
- Save progress: commit often with concise messages; push to keep a remote backup.

## Rule while working
- As you do work, always commit changes to Git with clean, descriptive messages and push to GitHub immediately so we never lose status or work.

## Recent Activities
- Fixed multiple syntax errors in topdownshooter.html (missing parentheses, incorrect closure)
- Added README.md with run instructions and icons
- Created local web server on port 8000
- Removed unnecessary FIX_SUMMARY.md file
- Renamed game.html to topdownshooter.html
- Updated index.html and CLAUDE.md to reflect new filename
- All files committed and pushed to GitHub

## Running / Testing
- Open any `.html` file in a modern browser (double-click or `start <file>` on Windows).
- Or run local server: `python -m http.server 8000` then visit `http://localhost:8000`
- No automated tests; verify behavior manually in-browser (e.g., start game, move player, shoot, advance levels, reset).

## Architecture Notes (big picture)
- `topdownshooter.html`: single-file app with separate game states (MENU, PLAYING, LEVEL_COMPLETE, GAME_OVER). Uses Canvas 2D for rendering; game loop via `requestAnimationFrame`.
  - Player input: keyboard (Arrow/WASD) + mouse for aiming/shoot.
  - Entities: bullets (array), enemies (array with types basic/fast/tank), particles (decals/explosions), screen shake on hit.
  - Level progression: config-driven spawn counts/rates; increasing difficulty with tanks.
- `tictactoe.html`: classic 3x3 board with DOM-driven UI, win/draw detection, and restart.

## Conventions
- Always commit changes with clean, descriptive messages; push to GitHub after each meaningful step.
- Use descriptive branch names; prefer small, focused commits.
- Coordinate with Git when making larger refactors to avoid merge conflicts.