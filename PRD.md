# PRD — Freelance Time Tracker

## Problem
A freelance designer / communications specialist runs about three client projects at once and
switches between them, often working on more than one at the same time. They need a fast way
to see how much time each project gets.

## MVP (in scope)
- One start/stop button per project. Several can run at once.
- Each run is timed. Each project also shows its total time.
- Stopping a timer asks what was done, then saves that as a log entry.
- Rename projects on the page itself. Add, archive, restore and delete projects at any time.
- The data stays saved between visits and devices (the artifact's `db` store).

## Added beyond the brief (small, kept simple)
- Option to run one timer at a time: starting one stops the others.
- Adjust the duration in the stop prompt, or discard an accidental run.
- Add time by hand for work done away from the tracker.
- Totals for today and this week. Edit or delete log entries. Filter the log by project.
- Optional hourly rate per project, showing the amount earned.
- Export as CSV for invoicing.
- Pause and resume a timer without ending the session.
- Sub-projects per project, picked from chips at the top of the card before starting. The chosen
  sub-project labels the entry, so stopping logs straight away (a note can be added after). Switching
  sub-project mid-session logs the time so far and carries on under the new one.

## Out of scope (suggested only, ask before building)
- Hour budgets or retainer caps per project
- Date-range invoice reports
- Calendar or Google Sheets sync
- Pomodoro or break reminders
- Use by more than one person

## Success metrics
- Starting or stopping a timer takes one click.
- Logging a stop takes one short sentence and Enter.
- Every tracked minute ends up in the log with a label.

## Technical requirements
- One HTML file, published as a claude.ai artifact.
- Uses `db` when it is available. Otherwise falls back to `localStorage`.
- Works at phone width and in both light and dark mode.
