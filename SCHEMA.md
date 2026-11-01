# SCHEMA — Freelance Time Tracker

Artifact `db` store (JSON documents). In the UI, `projects` are **clients** and `sub` is a **project**. Collections below; the field contracts are fixed. Add
new fields at the end.

## projects/{id}
| field | type | notes |
|---|---|---|
| name | string | editable inline |
| color | string | one of the palette keys (`cobalt`, `teal`, …) |
| order | number | sort order |
| archived | boolean | hidden from the main grid |
| runningSince | number \| null | epoch ms while running |
| rate | number \| null | hourly rate, optional |
| createdAt | number | epoch ms |
| subs | string[] | sub-project names |
| sub | string | selected sub-project, "" for none |
| sessionStart | number \| null | epoch ms the current session began (running or paused) |
| banked | number | seconds logged before the last pause |
| bufferDays | number | default review buffer for new deadlines (working days) |

## entries/{id}
| field | type | notes |
|---|---|---|
| projectId | string | → projects/{id} |
| start | number | epoch ms |
| end | number | epoch ms |
| seconds | number | billable duration (may differ from end-start if edited) |
| note | string | "" means needs a label |
| tag | string | optional work type |
| sub | string | sub-project, "" for none |

## deadlines/{id}
| field | type | notes |
|---|---|---|
| projectId | string | → projects/{id} (the client) |
| sub | string | project, "" for any |
| title | string | what's due |
| due | string | go-live date, `YYYY-MM-DD` |
| bufferDays | number | working days before `due` to send for review |
| estimateSec | number \| null | estimate |
| createdAt | number | epoch ms; time counts from the start of this day |
| doneAt | number \| null | epoch ms when marked done |
| actualSec | number \| null | time logged when marked done; feeds the suggested estimate |

## settings/main
| field | type | notes |
|---|---|---|
| single | boolean | one timer at a time |
| currency | string | symbol shown with earnings |

## Off-store state
- `localStorage["ftt-v1"]` holds the full state when `db` is unavailable (signed out, local preview).
  It is never merged into `db`.

## Access control
`capabilities.db.rules = [{path: "", read: "owner", write: "owner"}]`

## Capacity
The cap is 25,000 documents per artifact, with one document per log entry. At about 15 entries a day that lasts years.
