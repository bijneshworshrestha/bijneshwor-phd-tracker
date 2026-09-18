# bijneshwor-phd-tracker

Personal PhD opportunity tracker for **Bijneshwor Shrestha** (Berlin, Nepal-origin researcher).

**Research topic:** Institutional environment and organisational practice in developing economies — specifically, how managerial control mechanisms shape work process clarity and operational effectiveness in domestic Nepalese service-sector firms.

**Theoretical pillars:** North (1990) institutional framework · Tosi & Slocum (1984) contingency theory · Mintzberg (1979/1983) coordinating mechanisms · Hall & Soskice (2001) Varieties of Capitalism.

---

## Repository structure

```
bijneshwor-phd-tracker/
├── README.md                   ← this file
├── index.html                  ← live dashboard (Stark Tech dark theme, reads/writes the artifact DB)
├── data/
│   └── opportunities.json      ← snapshot dump (positions + scholarships + watchlist + scope metadata)
└── scan-logs/
    └── YYYY-MM-DD-daily-scan.md  ← one log per automated daily scan
```

---

## Live opportunity database

The authoritative database lives in a Claude Artifact:
**https://claude.ai/artifact/0c17f819-0f83-4a8e-a627-f359085cbef8**

`data/opportunities.json` is a snapshot generated from that database each time the scanner or this repo is refreshed. Treat the artifact as the source of truth and this file as a point-in-time export.

---

## Automated scanner

A daily scheduled task (Claude Cowork) runs every day and:
1. Fetches university PhD portals directly
2. Checks scholarship deadline pages
3. Scans aggregator portals (Academic Positions, jobs.ac.uk, EURAXESS, scholars4dev)
4. Runs targeted web searches
5. Adds any new item scoring ≥ 40 on the relevance rubric to the artifact database
6. Sends a push notification if anything new is found or urgent deadlines are approaching

### Geographic scope

| Region | Status | Portals monitored |
|---|---|---|
| Europe (Nordic, DACH, Benelux, UK) | Active since launch | ~14 university portals + 4 scholarship pages |
| Hong Kong | Active | HKPFS + HKU/CUHK/HKUST |
| **Asia-Pacific (China, South Korea, New Zealand, Australia)** | **Expanded 2026-09-17** | **12 new university portals** (see below) |

**Asia-Pacific portals added 2026-09-17:**

| Country | Portals |
|---|---|
| China | Tsinghua University, Peking University, Fudan University |
| South Korea | Seoul National University, KAIST, Yonsei University |
| New Zealand | University of Auckland, Victoria University of Wellington, University of Otago |
| Australia | Australian National University, University of Melbourne, University of Sydney |

This first pass added the portals to the monitoring list and logged the associated national scholarship schemes (China Scholarship Council, Korean Government Scholarship Program, New Zealand Excellence Awards, Australian Research Training Program) as **watchlist** entries — none has yet cleared the 40-point relevance threshold with a verified current-cycle deadline, so none is in the scored database yet. See `scan-logs/2026-09-17-daily-scan.md` for detail and I am not fully certain of every deadline/funding figure below — verify before relying on them.

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

Items scoring **40+** are saved to the scored `positions`/`scholarships` collections. Items below 40, or with an unconfirmed current-cycle deadline, are logged as **watchlist** entries instead.

---

## Key constraints

- **DAAD EPOS:** INELIGIBLE (prior German residency > 15 months)
- **Fulbright Nepal:** opens Feb 2027 — flag only when deadline approaches
- **MEXT Japan:** opens ~April 2027 — flag only when deadline approaches
- **HKPFS:** only one lifetime application permitted across all HK universities
- **Asia-Pacific national schemes (CSC, GKS, NZ Excellence, Australian RTP):** funding figures and deadlines below are drawn from general public knowledge of these programmes, not a fresh page fetch — confirm directly on the host university/agency site before treating any date as fixed.

---

## Last scan

**Date:** 2026-09-17
**New items added to scored database:** 1 (`kcl-gregory-jackson-2027` — Gregory Jackson at KCL actively accepting students)
**Existing items updated:** 1 (`insead-phd-ob-2027` — deadline corrected to 2027-01-04)
**Scope change:** Asia-Pacific scanner expansion — China, South Korea, New Zealand, Australia added; 12 new university portals now monitored; 4 national scholarship schemes logged to the watchlist pending verification
**Urgent deadline:** UNU-WIDER closes **30 September 2026** (13 days as of last scan)
