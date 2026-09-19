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
│   └── opportunities.json      ← full database dump (positions + scholarships + supervisors + bibliography + watchlist)
├── scan-logs/
│   └── YYYY-MM-DD-daily-scan.md  ← one log per automated daily scan
├── index.html                  ← PhD Tracker dashboard (Stark Tech dark theme), repo-root copy
└── ui/
    └── phd-tracker-stark.html  ← PhD Tracker dashboard (Stark Tech dark theme), same content as index.html
```

---

## Live opportunity database

The authoritative database lives in a Claude Artifact:
**https://claude.ai/artifact/0c17f819-0f83-4a8e-a627-f359085cbef8**

`data/opportunities.json` is a snapshot generated from that artifact database. It is **not live** — it only reflects the state of the database as of when someone regenerates and commits it (see "Known limitation" below).

---

## Automated scanner

A daily scheduled task (Claude Cowork) runs every day at 11:00 AM Berlin time and:

1. Fetches ~20 European university PhD portals directly
2. Fetches ~12 Asia-Pacific university PhD portals (China, South Korea, New Zealand, Australia) — **added 2026-09-17**
3. Checks scholarship deadline pages (Europe + Asia-Pacific)
4. Scans aggregator portals (Academic Positions, jobs.ac.uk, EURAXESS, scholars4dev)
5. Runs 10 targeted web searches (6 Europe + 4 Asia-Pacific) — **expanded 2026-09-17**
6. Adds any new item scoring ≥ 40 on the relevance rubric to the artifact database
7. Sends a push notification if anything new is found or urgent deadlines are approaching

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

## Geographic coverage

### Europe (primary)
- Norway (NHH Bergen, BI Oslo)
- Sweden (Gothenburg, Stockholm School of Economics)
- Netherlands (RSM/ERIM, Tilburg, Utrecht)
- Germany (MPIfG/IMPRS, LMU Munich, FU Berlin, University of Hamburg)
- Denmark (CBS Copenhagen)
- Switzerland (HSG St. Gallen)
- France (INSEAD)
- UK (King's College London — Gregory Jackson actively accepting)
- Poland (Kozminski University)

### Asia-Pacific (added 2026-09-17)
- **China:** CEIBS Shanghai, Tsinghua SEM, Fudan School of Management
- **South Korea:** SKKU, Korea University, KAIST
- **New Zealand:** University of Auckland, Victoria University Wellington
- **Australia:** University of Melbourne, Monash, University of Sydney, UNSW, ANU

### Already covered (in database, not actively scanned)
- Hong Kong: HKPFS (HKUST, HKU, CUHK)
- Japan: MEXT scholarship (monitored from April 2027)

**Note on Asia-Pacific figures:** I am not fully certain of every stipend amount and deadline listed for the Asia-Pacific watchlist entries in `data/opportunities.json` — they are drawn from general knowledge as of the 2026-09-17 scope expansion, not a freshly verified fetch. Treat them as approximate and verify against the official source before relying on them. A dedicated verification scan across China, Korea, New Zealand, Australia, Japan and Southeast Asia is planned for 2026-09-20.

---

## Key constraints

- **DAAD EPOS:** INELIGIBLE (prior German residency > 15 months)
- **Fulbright Nepal:** opens Feb 2027 — flag only when deadline approaches
- **MEXT Japan:** opens ~April 2027 — flag only when deadline approaches
- **HKPFS:** only one lifetime application permitted across all HK universities

---

## Known limitation

`data/opportunities.json` is a static snapshot. The dashboard (`index.html` / `ui/phd-tracker-stark.html`) tries `window.claude.use('db')` first for live sync — this only works when the page is opened inside claude.ai. On a static host such as GitHub Pages, `window.claude` does not exist, so the dashboard falls back to fetching `data/opportunities.json` instead. That file will not reflect new writes to the artifact database until someone manually regenerates and pushes it, or the existing `.github/workflows/add-firestore-entries.yml` action is extended to do this on a schedule (not yet done).

---

## Last scan

**Date:** 2026-09-17
**New items added:** 1 (`kcl-gregory-jackson-2027` — Gregory Jackson at KCL actively accepting students)
**Items updated:** 1 (`insead-phd-ob-2027` — deadline corrected to 2027-01-04)
**Urgent deadline:** UNU-WIDER closes **30 September 2026**
**Scanner expanded:** China, South Korea, New Zealand, Australia added to scan scope
**Next scan (planned):** 2026-09-20 — verification pass across China, Korea, New Zealand, Australia, Japan and Southeast Asia
