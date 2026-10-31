# SCHEMA — Freelance Time Tracker

Artifact `db` store (JSON documents). Collections below; the field contracts are fixed. Add
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

## entries/{id}
| field | type | notes |
|---|---|---|
| projectId | string | → projects/{id} |
| start | number | epoch ms |
| end | number | epoch ms |
| seconds | number | billable duration (may differ from end-start if edited) |
| note | string | "" means needs a label |
| tag | string | optional work type |

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
