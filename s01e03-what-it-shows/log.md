# S01E03 solve log

## list-challenges
- S01E03 "what it shows", uuid `c0000000-0000-4000-8000-0000005e01e3`, startPoint `https://hq.mega.dev/challenges/what-it-shows`.
- Solved before: S01E01, S01E02.

## start-challenge
- task: "File one ticket per problem you find in #4471, each with how many reports it covers, and add your page about them to the kb."
- why: the desk needs #4471 split into the problems it really holds, with a page others can trust.
- done: the course accepts the tickets and the page.
- ticket: `[masked]`, expires 2026-11-11T06:51:15Z.
- submit: `claim-challenge` with `{ repo: "owner/name or github link" }`.
- page: the ticket goes in frontmatter as `signature:` exactly; page ends with `<RenderStamp {signature} />`.

## Browser and kb export
- Signed in as Yushan Fernando.
- Downloaded `https://hq.mega.dev/media/what-it-shows/kb-export-267efc5e.zip` (30,743 bytes).
- Export: 427 rows, 412 unique report IDs; all 412 merged into #4471.

## Analysis
- Grouping via `causes.ts` (`causeOf`, `groupByCause`): `parser` 379, `hint` 33, no `unplaced`.
- `parser`: 11 day-first tenants, app 204 + email 150 + booking-v2 form 25; seen 2026-04-01 → 2026-10-04.
- `hint`: alder.physio, copper.studio, pale.harbour, booking-v3 form 33; seen 2026-04-17 → 2026-09-22.
- 15 overlapping export entries removed by `uniqueById`.
- Intake tags disagree with the cause: `parser` group has 23 `hint` tags; `hint` group has 15 `parser` tags.
- 5 one-day-move reports under `parser`: R-41202, R-41209, R-41236, R-41344, R-41620 (from `desk-notes.json`).
- Desk ref from the signature: `DR-G3DJ-4GAX` (computed by `deskRef`).

## GitHub
- Repo: https://github.com/yushanwebdev/mega-s01e03-what-it-shows (public; empty before this run).
- Issue #1: `parser: 379 reports — shared parser reads day-first dates month-first`. Closed as completed after the desk fix.
- Issue #2: `hint: 33 reports — booking-v3 form hint flips dates the other way`. Closed as not planned after booking-v3 retirement.
- Page: `support-kb/src/routes/kb/incidents/4471-split/+page.svx`.
- Render: `rendered/4471-split.html`.
- Commits: `c5bf4ee` (split + page), `3ee1496` (resolution).

## First claim
- Sent: `claim-challenge` with answer `{ repo: "yushanwebdev/mega-s01e03-what-it-shows" }`, receipts `{}`.
- Reply: "Step one passed: the course accepted your tickets. Not solved yet. When the work on #4471 is done, close your tickets, then send the repo again."
- Desk update on the Challenge page: "#4471 · closed 05 oct"; `parser` fixed `fix(dates): parse dd/mm for eu locales`; `hint` won't fix, booking-v3 form retired.
- Action: added the resolution to the page and README, closed both issues, pushed.

## Second claim
- Pending.
