# AGENTS — who does what

## Roles
| Role | Does | Never does |
|---|---|---|
| Owner (Bennett) | Decides scope, names projects, approves publishes | — |
| Claude | Edits `src/time-tracker.html`, republishes the artifact, reads/seeds `db` via ArtifactData | Writes or deletes log entries without being asked |

## Phase gating
Plan against `PRD.md`, implement, check in local mode, then republish to the same artifact URL.

## Handover
The artifact URL is in `CLAUDE.md`. Republish from `src/time-tracker.html` and omit `capabilities`
to keep the stored declaration.

<!-- bmad:context -->
<!-- bmad-project-context manages this block. Not installed in this repo. -->
<!-- /bmad:context -->
