@AGENTS.md

# Freelance Time Tracker — project guide

**Contracts:** `PRD.md` · `ARCHITECTURE.md` · `SCHEMA.md` · `DESIGN.md` · `RULES.md` · `SKILLS.md`.
If anything here contradicts them, this file is stale.

## What this is
A single-page time tracker, `src/time-tracker.html`, published as a claude.ai artifact.
Artifact URLs — one copy per person, each owned by them, with its own data:
- Bennett: https://claude.ai/artifact/E8Yvjh88EpZjyvByErSH7A
- Evangeline: https://claude.ai/artifact/ArUsqd9S489gx34RKuJkB8

Republish to the copy you own. Code changes go out to each copy separately; logged time never moves between copies.

## How to work on it
Edit the HTML. Preview with the `tracker` server in `.claude/launch.json` (localhost:4317), where it runs in `localStorage` mode. Republish to the same URL; omit `capabilities` to keep the owner-only `db` rules.

## Gotchas
None observed yet.
