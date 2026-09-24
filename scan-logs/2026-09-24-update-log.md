# PhD Tracker — Manual Update Log
**Date:** 2026-09-24
**Run type:** Manual bug-fix/feature session (not an automated scanner run)
**Operator:** Claude (Cowork session, at Bij's request)

---

## Summary

Bij reported: *"the nearest deadline is 8 [days] and yet a deadline of 2 months is highlighted. I
need timer running in all of the deadlines. DAAD is no go because I am in Germany. and anything
that is in USA is no go."* Two days later, followed up asking to make the timer auto-run and to
check for updates.

This was a diagnosis-and-fix session against `index.html` and the live artifact database, not a
scan for new opportunities.

---

## Bug found and fixed: inconsistent countdown display on the Scholarships list

The Dashboard's main countdown card and "Upcoming Deadlines" widget were checked first and were
already correct (both showed UNU-WIDER / 8 days, matching what Bij described as the true nearest
deadline). The actual bug was in the separate **Scholarships tab list** (`renderScholarships()`):

1. **Sort bug** — the comparator did a raw `new Date(a.deadline) - new Date(b.deadline)`
   subtraction, which evaluates to `NaN` for the placeholder-text deadlines DAAD and Fulbright
   store (e.g. `"2027 cycle TBD — typically Oct–Nov..."`), making sort order for those rows
   unreliable.
2. **Silent "Open" on an expired item** — `mext-japan-2027` (deadline 2026-05-31, ~114 days past
   as of 22 Sept) was still `status: 'open'`, so it sorted to the very front of the list
   chronologically and displayed a plain "Open" badge with **no day-count at all** — the code only
   showed a day-count when `days >= 0`, silently hiding "Expired" instead of saying so.
3. **"Invalid Date" rendered literally** — `fmtDate()` would print the literal string
   `"Invalid Date"` for any non-ISO placeholder deadline string instead of falling back to
   something readable.

### Fix (applied to `index.html`, mirrored to `ui/phd-tracker-stark.html`)

- Every scholarship card now shows a consistent `Expired` / `Today` / `Nd left` label next to its
  due date, matching what the Positions list already did.
- Sort now ranks by live urgency: open items with a real, non-negative day-count first (soonest
  first); everything else — expired, ineligible, or unparseable-date — pushed to the bottom,
  deterministically. No more `NaN`-driven ordering.
- `fmtDate()` now falls back to showing the raw placeholder text instead of `"Invalid Date"` when
  a deadline string isn't a real date.
- Added a new `ineligible` status value + grey badge to `statusBadge()` and to the Scholarships
  status filter dropdown.

---

## Feature added: live auto-running timer

Bij asked for the countdown to update itself automatically rather than only on page load/refresh.

Added to `index.html`'s init block:

```js
setInterval(() => { renderCurrent(); }, 60000);
document.addEventListener('visibilitychange', () => { if (!document.hidden) renderCurrent(); });
```

- The visible section (dashboard countdown/stat tiles, Scholarships list, Positions list, Passed
  Deadlines, etc.) now re-renders every 60 seconds from data already in memory — cheap, no network
  call, just recomputing `daysUntil()`/`urgencyClass()` and redrawing.
- Also re-renders immediately whenever the tab regains focus (`visibilitychange`), so a tab left
  open overnight catches up to the new day instantly instead of waiting up to a minute.
- Deadlines are day-granularity, so this is enough to keep every countdown live without ever
  needing a manual refresh.

---

## Standing exclusion rules implemented

Per Bij's explicit instruction (22 Sept 2026): DAAD is a confirmed no-go (prior German residency
caps at 15 months; Bij has lived in Germany 3+ years), and the United States is excluded entirely
as a region.

**Artifact database changes** (mirrored into `data/opportunities.json`):

| Record | Field | Old | New | Reason |
|---|---|---|---|---|
| `daad-epos-2027` | `status` | `open` | `ineligible` | Standing DAAD exclusion — the record's own `notes` field had already documented this since it was added, but `status` had never been updated to match |
| `fulbright-nepal-2027` | `status` | `open` | `ineligible` | Standing USA exclusion (the one US-based scholarship in the database) |
| `mext-japan-2027` | `status` | `open` | `closed` | Deadline (31 May 2026) already passed — unrelated to the two exclusion rules, caught during the same pass |

**Positions collection checked too** — no USA-based position found (`insead-phd-ob-2027` is
France/Singapore, not the US), so nothing needed changing there.

**Scheduled task updated:** the `PhD Position & Scholarship Auto-Scanner`'s prompt
(`trig_01KquS712L3FzfzGdDbM1Wn4`, currently `enabled: false`) now has an explicit
"STANDING EXCLUSION RULES" section: never fetch, log, or re-add DAAD or any US-based item; never
revert `daad-epos-2027` or `fulbright-nepal-2027` back to `open`; correct any other passed-deadline
item still marked `open` to `closed` when found.

---

## Update check (24 Sept 2026)

Checked the full live artifact database (all 10 scholarships, all 5 positions) against the 22 Sept
state — **no new items, no other deadlines quietly expired while still marked `open`.** Nothing for
the scanner to have caught even if it were running.

**Scanner status:** still disabled (`enabled: false`), last successful run 17 Sept 2026. It will
not check any portal or aggregator for new positions/scholarships until it's manually re-enabled or
fired once.

**Nearest live deadline as of 24 Sept 2026:** UNU-WIDER Visiting PhD Fellowship, closes
**30 September 2026 — 6 days out.**

---

*Generated by: Claude (manual session, not the automated scanner)*
*Artifact database:* https://claude.ai/code/artifact/0c17f819-0f83-4a8e-a627-f359085cbef8
