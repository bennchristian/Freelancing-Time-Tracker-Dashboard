# RULES — coding and implementation

## Principles
1. **SOLID.** One responsibility per function. The UI calls the store adapter, never a backend.
2. **DRY at 4.** Extract a helper only once the same logic appears 4+ times. The wrong
   abstraction couples callers that had no reason to be coupled.
3. **KISS.** This is a single-file tool. No frameworks, no build, no libraries.

## Page rules
- Every color is a token on `:root` with dark-mode overrides. No literal colors in components.
- Wrap all `localStorage` access in try/catch.
- `db`: write only on a user action, one write at a time per doc, and never from render or the ticker.
- Set user text with `textContent`, never `innerHTML`.

## Data rules
Field contracts live in `SCHEMA.md`. When the data changes, update it in the same change.

## Process rules
- `PRD.md` is the scope contract. Work outside it stops and asks first.
- Check: open `src/time-tracker.html` in a browser. Starting, stopping, logging, renaming and
  archiving must all work in local mode before publishing.
