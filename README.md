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

- **DAAD EPOS:** INELIGIBLE (prior German residency > 15 months)
- **Fulbright Nepal:** opens Feb 2027 — flag only when deadline approaches
- **MEXT Japan:** opens ~April 2027 — flag only when deadline approaches
- **HKPFS:** only one lifetime application permitted across all HK universities

---

## Last scan

**Date:** 2026-09-17  
**New items added:** 1 (`kcl-gregory-jackson-2027` — Gregory Jackson at KCL actively accepting students)  
**Items updated:** 1 (`insead-phd-ob-2027` — deadline corrected to 2027-01-04)  
**Urgent deadline:** UNU-WIDER closes **30 September 2026** (13 days)
