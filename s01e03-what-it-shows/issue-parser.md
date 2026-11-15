## Cause

The shared parser reads every date month-first. These tenants write day-first, so a booking for 7 May becomes an invite for 5 July. This is the cause the desk originally recorded in #4471.

## Reports covered

**379** of the 412 unique reports merged into #4471.

- Tenants: 11 — alder.physio, copper.studio, harbour.dental, kettle.books, lantern.row, long.table, morrow.tax, nine.lanterns, pale.harbour, ridge.clinic, stone.and.sons
- Channels: app 204, email 150, form 25
- First seen 2026-04-01, last seen 2026-10-04
- Intake tags: parser 356, hint 23. Intake tags are guesses: 23 of these reports were tagged `hint`, but the tenant and channel make them `parser`.

## Why these channels

App and email always use the shared parser. The 25 form reports here come from booking-v2 tenants, whose form hint is `DD/MM/YYYY`; the input matches the day-first tenant and then the month-first parser flips it.

## One-day move, counted here

Five reports in this group read as a one-day move, not a month/day flip: `R-41202`, `R-41209`, `R-41236`, `R-41344`, `R-41620`. The desk's `desk-notes.json` counts them under `parser` and footnotes them. They stay inside the 379 here. Engineering should decide whether they need their own fix.

## Evidence

Grouping logic: `support-kb/src/lib/kb/causes.ts` (`groupByCause`, `causeOf`), tenant locale and form in `support-kb/src/lib/data/tenants/*.json`, and the 412 unique report IDs from `support-kb/src/lib/data/reports-4471.json`.
