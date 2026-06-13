# Project: Kids Math Game (משחק חשבון לילדים)

## Overview
Educational math game for two children (boy age 4, girl age 6).
Adaptive difficulty, emoji counting mode for the younger child,
and addition/subtraction for the older child.
Single self-contained HTML file, no build step.

## Tech Stack
- Framework: React 18 + Babel via CDN
- Styling: Inline CSS + CSS animations (no external framework)
- Database: none
- Auth: none
- Deployment: Vercel (auto-deploy from GitHub main branch)

## Commands
- dev:    Open index.html directly in browser (no build step)
- deploy: git push origin main → Vercel auto-deploys

## Project Structure
/
└── index.html    → entire game (HTML + CSS + JS in one file)

## Architecture Rules
- All React components live inside index.html
- State: React useState for all game state
- Persistence: localStorage only — no server, no external API
- Components: max 150 lines each. Split into sub-components if larger.

## Coding Conventions
- Variable names, functions, comments, git messages: English
- All user-facing text strings: Hebrew (RTL layout)
- Components: PascalCase
- No external dependencies beyond React / ReactDOM / Babel CDN

## Game Logic Rules
- Profile 1: boy, age 4 — dinosaur theme 🦕
- Profile 2: girl, age 6 — princess/star theme 👸
- Counting mode (Profile 1):
    Show N emoji objects. Ask "כמה?". Multiple choice, 3 options.
    Difficulty range: level 1 = numbers 1–5 | level 5 = numbers 1–15
- Math mode (Profile 2):
    Show equation (e.g. "3 + 4 = ?"). Multiple choice, 4 options.
    Level 1 = sums up to 10 | Level 5 = sums up to 50 + subtraction
- Adaptive difficulty (both modes):
    3 correct in a row → difficulty level +1
    2 wrong in a row  → difficulty level -1 (min level 1)
- Progress per profile saved to localStorage:
    { level, totalStars, correctStreak, wrongStreak }

## Current Status
- [ ] Profile selection screen
- [ ] Counting mode (boy, age 4, dinosaur theme)
- [ ] Math mode — addition + subtraction (girl, age 6, princess theme)
- [ ] Adaptive difficulty engine
- [ ] Visual rewards + animations
- [ ] localStorage progress saving

## Anti-Pattern Reminders
- Single-file project. Never split into multiple files.
- Do not add npm, package.json, or build tools.
- Do not use external CSS frameworks.
- Complete each task fully before reporting done.
- Do not ask for confirmation mid-task.
