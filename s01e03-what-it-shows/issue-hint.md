## Cause

The booking-v3 form prints `MM/DD/YYYY` under its date field. For these day-first tenants, people type month-first as the hint says, and the form reads the date day-first. The result is a month/day flip in the opposite direction from the shared parser. The parser fix does not touch this.

## Reports covered

**33** of the 412 unique reports merged into #4471.

- Tenants: alder.physio, copper.studio, pale.harbour — all on booking-v3
- Channel: form 33
- First seen 2026-04-17, last seen 2026-09-22
- Intake tags: parser 15, hint 18. Intake tags are guesses: 15 of these reports were tagged `parser`, but the tenant, form and channel make them `hint`.

## Why it needs its own ticket

The subject-line triage merged these into #4471, which is marked `known` as a parser issue. If #4471 closes on the parser fix alone, these 33 reports stay broken. The form's hint and the form's reading disagree, so this needs its own fix and its own count.

## Evidence

`support-kb/src/lib/kb/causes.ts` (`causeOf`, `DATE_HINT`) and the tenant files `support-kb/src/lib/data/tenants/alder.physio.json`, `copper.studio.json`, `pale.harbour.json`.
