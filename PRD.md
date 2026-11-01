# PRD — Freelance Time Tracker

## Problem
A freelance designer / communications specialist works for about three clients at once, each with
several projects, and switches between them, often more than one at a time. They need a fast way
to see how much time each client and project gets, and to plan deadlines, including the buffer
a client needs to review work before it goes live.

**Wording:** a *client* is a card (stored as `projects`); a *project* is a chip on that card (stored as `sub`).

## MVP (in scope)
- One start/stop button per client. Several can run at once.
- Each run is timed. Each client also shows its total time.
- Stopping a timer asks what was done, then saves that as a log entry.
- Rename clients on the page itself. Add, archive, restore and delete clients at any time.
- The data stays saved between visits and devices (the artifact's `db` store).

## Added beyond the brief (small, kept simple)
- Option to run one timer at a time: starting one stops the others.
- Adjust the duration in the stop prompt, or discard an accidental run.
- Add time by hand for work done away from the tracker.
- Totals for today and this week. Edit or delete log entries. Filter the log by client.
- Optional hourly rate per client, showing the amount earned.
- Export as CSV for invoicing.
- Pause and resume a timer without ending the session.
- Projects per client, picked from chips at the top of the card before starting. The chosen
  project labels the entry, so stopping logs straight away (a note can be added after). Switching
  project mid-session logs the time so far and carries on under the new one.
- Deadlines: a go-live date plus a review buffer in working days gives a "send for review by" date,
  with an Overdue / Send today / Send tomorrow status. Each client remembers its last buffer.
  An optional estimate is tracked against time logged on that client and project, and finished
  deadlines suggest an estimate for the next one ("past ones took about 2h 30m").

## Out of scope (suggested only, ask before building)
- Hour budgets or retainer caps per client
- Recurring deadlines (e.g. a post every Tuesday)
- Daily-capacity planning ("start by" dates from hours available per day)
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
