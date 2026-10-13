# bijneshwor-phd-tracker

Personal PhD opportunity tracker for **Bijneshwor Shrestha** (Berlin, Nepal-origin researcher).

**Research topic:** Institutional environment and organisational practice in developing economies — specifically, how managerial control mechanisms shape work process clarity and operational effectiveness in domestic Nepalese service-sector firms.

**Theoretical pillars:** North (1990) institutional framework · Tosi & Slocum (1984) contingency theory · Mintzberg (1979/1983) coordinating mechanisms · Hall & Soskice (2001) Varieties of Capitalism.

---

## Repository structure

```
bijneshwor-phd-tracker/
├── README.md                   ← this file
├── data/
│   └── opportunities.json      ← full database dump (positions + scholarships + watchlist)
└── scan-logs/
    └── YYYY-MM-DD-daily-scan.md  ← one log per automated daily scan
```

---

## Live opportunity database

The authoritative database lives in a Claude Artifact:  
**https://claude.ai/code/artifact/0c17f819-0f83-4a8e-a627-f359085cbef8**

`data/opportunities.json` is a snapshot generated each day by the automated scanner.

---

## Automated scanner

A daily scheduled task (Claude Cowork) runs every day and:
1. Fetches ~20 university PhD portals directly
2. Checks scholarship deadline pages
3. Scans aggregator portals (Academic Positions, jobs.ac.uk, EURAXESS, scholars4dev)
4. Runs 6 targeted web searches
5. Adds any new item scoring ≥ 40 on the relevance rubric to the artifact database
6. Sends a push notification if anything new is found or urgent deadlines are approaching

---

## Relevance scoring rubric

| Criterion | Points |
|---|---|
| Institutional theory / North / informal institutions | +25 |
| HRM / managerial control / work organisation | +20 |
| Developing economy / emerging markets / South Asia | +20 |
| Nepal / South Asia explicit mention | +15 |
| Qualitative / mixed-methods / ethnographic approach | +10 |
| Comparative institutional / VoC / Nordic management | +10 |

Items scoring **40+** are saved. Items below 40 may appear in the scan log watchlist.

---

## Key constraints

- **DAAD (any programme, incl. DAAD EPOS):** INELIGIBLE — status `ineligible` in the database. Prior
  German residency caps at 15 months before application; Bij has lived in Germany 3+ years. Never
  re-flag as open.
- **United States — excluded entirely, at Bij's instruction (22 Sept 2026):** no US-based position,
  university, or US-government scholarship (Fulbright included) is a "go". `fulbright-nepal-2027`
  status is `ineligible`. Never re-flag as open.
- **MEXT Japan:** `mext-japan-2027`'s 2027-cycle embassy deadline was 31 May 2026 — already passed,
  status corrected to `closed`. Watch for the next intake's deadline announcement.
- **HKPFS:** only one lifetime application permitted across all HK universities.
- **Pre-existing PhD enrolment required — excluded entirely, added 24 Sept 2026:** any listing
  that requires the applicant to already be enrolled in a PhD programme (a visiting fellowship,
  visiting scholar post, research residency, ABD/"dissertation phase" requirement) does not
  qualify, however well it scores on topic. `unu-wider-visiting-2026` is `ineligible` for this
  reason. Never re-flag it, or anything like it, back to open.

---

## Last scan

**Date:** 2026-09-17 (automated scan; scanner has been disabled since and has not run since this date)  
**New items added:** 1 (`kcl-gregory-jackson-2027` — Gregory Jackson at KCL actively accepting students)  
**Items updated:** 1 (`insead-phd-ob-2027` — deadline corrected to 2027-01-04)

## Last manual update

**Date:** 2026-10-13 — deadline status pass.
- `cbs-strategy-innovation-2026` (deadline 28 Sept) and `jibs-family-business-2026` (deadline 1 Oct)
  set to `closed`: both passed with no application submitted.
- `unu-wider-visiting-2026` set to `ineligible` in the JSON snapshot to match the 24 Sept eligibility
  decision (it was still `open` in the file).
- Active list as of 13 Oct 2026, by deadline: UEF Market 4.0 (15 Oct), Tampere Doctoral Researcher
  (16 Oct, strongest fit, supervisor must be contacted first), VU Amsterdam (18 Oct), TU Delft
  Paradoxical Leadership (18 Oct or 3 Nov, unverified), KU Leuven BPM & IoT (23 Oct), Swiss Government
  Excellence Scholarships (10 Nov), HKPFS (1 Dec), INSEAD (4 Jan 2027), ERIM/RSM (15 Jan 2027),
  IMPRS-SPCE (15 Feb 2027), Gothenburg (15 Mar 2027), Kozminski (fails funding floor), Tilburg (30 Jun 2027).

**Nearest live deadline as of 13 Oct 2026:** UEF Business School (15 Oct). Tampere (16 Oct) is the strongest fit.

Note: deadlines were carried forward from the 27 Sept data; confirm each on the official page before relying on it.

Previous update (2026-09-24, see `scan-logs/2026-09-24-update-log.md`): fixed inconsistent
countdown/urgency display on the Scholarships list, added an always-on live timer, set DAAD and
Fulbright Nepal to `ineligible` and MEXT to `closed`, and corrected the UNU-WIDER Visiting PhD
Fellowship to `ineligible` (it requires pre-existing PhD enrolment, which Bij does not have).

**Nearest live deadlines as of 27 Sept 2026:** CBS Strategy & Innovation (28 Sept — pay falls
short of Copenhagen's funding floor) and JIBS (1 Oct — ECTS eligibility unconfirmed) are the two
soonest; the strongest genuine fit, Tampere, closes 16 Oct 2026.
