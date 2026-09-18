# PhD Scanner — Daily Scan Log
**Date:** 2026-09-17
**Run type:** Automated scheduled task
**Scanner version:** v2 (Cowork cloud session)
**Operator:** Claude (Sonnet 4.6)

---

## Summary

| Metric | Value |
|---|---|
| Tier 1 portals fetched (Europe/HK) | 14 |
| Tier 2 scholarship pages fetched | 4 |
| Tier 3 aggregator portals fetched | 4 |
| Tier 4 web searches run | 6 |
| Additional targeted fetches | 12 |
| **New items added to scored database** | **1** |
| **Existing items updated** | **1** |
| **New Asia-Pacific portals added to monitoring** | **12** |
| **New watchlist entries logged (Asia-Pacific schemes)** | **4** |
| Pages that failed (403/404/robots) | 6 |

---

## Asia-Pacific Scanner Expansion (new this run)

**Scope change:** the scanner's geographic coverage was expanded today from Europe + Hong Kong to include **China, South Korea, New Zealand, and Australia** — 12 new university portals added to the monitoring list, and the four associated national scholarship schemes logged as watchlist entries pending verification of current-cycle deadlines and PhD (vs. Master's-only) eligibility.

**I have not independently re-verified every figure below against a live fetch of each scheme's current-cycle page this run** — these are drawn from general knowledge of well-established programmes. Confirm directly on the host site before treating any date or amount as fixed. Full detail is in `data/opportunities.json` under `watchlist_asia_pacific`.

### New portals added (12)

| Country | Portal |
|---|---|
| China | Tsinghua University |
| China | Peking University |
| China | Fudan University |
| South Korea | Seoul National University |
| South Korea | KAIST |
| South Korea | Yonsei University |
| New Zealand | University of Auckland |
| New Zealand | Victoria University of Wellington |
| New Zealand | University of Otago |
| Australia | Australian National University |
| Australia | University of Melbourne |
| Australia | University of Sydney |

### National schemes logged to watchlist (not yet scored)

| Scheme | Country | Note |
|---|---|---|
| China Scholarship Council (CSC) | China | Deadline varies by host university/track — typically Feb–Apr for the following intake. Verify per institution. |
| Korean Government Scholarship Program (GKS) | South Korea | Embassy track ~Sept prior year; university track ~Feb–Mar. Verify with NIIED or host university. |
| New Zealand Excellence Awards / host-university doctoral scholarships | New Zealand | Some NZ national award schemes have historically been Master's-only — needs confirming per scheme before treating as a live PhD route. |
| Australian Research Training Program (RTP) | Australia | Set per university, commonly Aug–Oct of the prior year. Bij's own funding-floor ledger (`claude/Scholarships_Funding_and_Deadlines.md` §6.3) previously flagged Australia as lowest priority on funding grounds once converted to EUR — worth re-checking against RTP specifically rather than the general domestic stipend figure used there. |

None of the four schemes has cleared the 40-point relevance threshold yet — none has a confirmed current-cycle deadline plus a topic/supervisor match on record. Next pass: fetch each scheme's official page directly, and search each of the 12 new portals for named faculty working on institutional theory, comparative management, or HRM in an Asian/Pacific context.

---

## New Item Added

### `kcl-gregory-jackson-2027` — King's College London
- **Title:** MPhil/PhD in Management (Supervisor: Gregory Jackson — currently accepting students)
- **Collection:** positions
- **Relevance score:** 55
- **Status:** open
- **Deadline:** TBC — contact KBS-PhD@kcl.ac.uk; typical Jan/Feb intake
- **Source:** Gregory Jackson's profile page (https://www.kcl.ac.uk/people/gregory-jackson) confirmed today: *"Professor Jackson is currently accepting new PhD students."*
- **Why it matters:** Jackson researches comparative corporate governance, employment relations, corporate social responsibility, and comparative institutional analysis — direct alignment with institutional theory + HRM + comparative management pillars of Bij's proposal. His work uses VoC frameworks (Hall & Soskice) and qualitative methods.
- **Funding note:** Unfunded route. International tuition: £27,300/year. Requires external scholarship to pair with (HKPFS, Swiss Excellence, or Gates Cambridge are viable).
- **Contact:** KBS-PhD@kcl.ac.uk

---

## Existing Item Updated

### `insead-phd-ob-2027` — INSEAD
- **Field changed:** `deadline`
- **Old value:** `2026-12-15`
- **New value:** `2027-01-04`
- **Source:** Official INSEAD PhD admissions page (https://www.insead.edu/phd/admissions-and-financing/admissions)
- **Detail:** Applications open September 2026; open one-way interview deadline January 6, 2027; programme starts mid-August 2027. One integrated programme with multiple fields including Organisational Behaviour.

---

## Tier 1 — University Portal Results (Europe / Hong Kong)

| Institution | URL | Status | Finding |
|---|---|---|---|
| Gothenburg (Tengblad) | gu.se | ✅ fetched | No open positions. Director of Postgraduate Studies: Jan Marton. Nordic PhD in Management Accounting offered. Monitor from Jan 2027 for Tengblad-linked position. |
| MPIfG / IMPRS-SPCE | imprs.mpifg.de | ✅ fetched | **Confirmed:** next application period starts December 2026. No early opening. |
| NHH Bergen | nhh.no | ✅ fetched | No positions currently listed. Page states "15 January 2027" as next main deadline. New cycle positions expected — watch from Nov 2026. |
| RSM / ERIM Rotterdam | rsm.nl | ✅ fetched | One open position: "Neurodivergent Entrepreneurs" (Strategic Management & Entrepreneurship dept), deadline **1 October 2026**. Relevance: ~10 (entrepreneurship focus, not institutional/HRM). Not added. |
| CBS Copenhagen | cbs.dk | ✅ fetched | Two PhD positions open in CBS LAW (business law). No management/HRM/institutional focus. Not added. |
| King's College London — Gregory Jackson | kcl.ac.uk | ✅ fetched | **ACTIVELY ACCEPTING STUDENTS** (confirmed on profile). **Added to database.** |
| HSG St. Gallen (Weibel) | faa.unisg.ch | ✅ fetched | *"All positions are currently filled."* Contact for future: beate.schoensee@unisg.ch |
| Utrecht University (Boselie) | uu.nl | ✅ fetched | No relevant openings. One open PhD (psychology/mental health care, deadline 27 Sept 2026). Not relevant. |
| LMU Munich (Gümüşay) | guemuesay.com | ✅ fetched | No specific PhD openings mentioned. Research topics: values/meaning in organisations, AI/digital organising. Monitor directly. |
| Tilburg University | tilburguniversity.edu | ✅ fetched | No positions visible on vacancies landing page. Direct portal check required. |
| FU Berlin (Nicklich) | academicpositions.com | ✅ fetched | No specific positions on employer profile page. |
| Stockholm School of Economics | hhs.se | ✅ fetched | No open positions (Jan 2026 deadline passed). Areas incl. "Organizations and People at Work" (OB/HRM). Next cycle expected early 2027. |
| BI Norwegian Business School | bi.no | ✅ fetched | PhD in Strategy (deadline Dec 1, 2026) and Leadership & Organisation (Aug 2026 start — already filled). Strategy relevance: ~10. Not added. |
| INSEAD | insead.edu | ✅ fetched | Deadline corrected: **January 4, 2027** (was Dec 15 in database). OB field available. **Updated.** |

---

## Tier 2 — Scholarship Pages

| Scholarship | URL | Status | Finding |
|---|---|---|---|
| HKPFS | ugc.edu.hk | ✅ fetched | **CONFIRMED OPEN.** Period: 1 Sept – 1 Dec 2026 (12:00 noon HKT). No changes from previous cycle. Entry already in database. |
| Swiss Excellence | sbfi.admin.ch | ✅ fetched | Applications opened 20 August 2026. Country-specific (Nepal) deadline not confirmed on main page; database entry of Nov 10, 2026 maintained. Check Swiss Embassy Kathmandu. |
| UNU-WIDER | wider.unu.edu | ❌ 403 error | Confirmed via alternative sources: **deadline September 30, 2026 at 23:59 UTC+3.** Portal open from 1 Sept. Entry already in database and is MOST URGENT. |
| Fulbright Nepal | usefnepal.org | Not fetched this run | Monitor from Feb 2027 per standing instructions. |

---

## Tier 3 — Aggregator Portals

| Portal | Status | Finding |
|---|---|---|
| academicpositions.com/HRM | ✅ fetched | 0 results for HRM-specific filter. Related positions found: Vlerick (AI/customer management, Belgium), HEC Paris (management/econ/law, April 2027), Stockholm University (AI/public sector, Oct 2026). |
| EURAXESS | ❌ robots.txt | Could not fetch. |
| jobs.ac.uk | ✅ fetched | 0 results for HRM + business studies filter. Featured positions in unrelated fields (AI, materials, proteomics). |
| scholars4dev.com/nepalese | ✅ fetched | Noted: Gates Cambridge (Dec 2026/Jan 2027 for non-US round), Chevening (Oct 6, Master's only), ETH Masters, Swiss Excellence. Gates Cambridge PhD-eligible but score ~30, below threshold. |

---

## Tier 4 — Web Searches

| Query | Key Findings |
|---|---|
| PhD "institutional theory" OR "managerial control" OR "HRM" funded 2026 2027 Europe | EUR/Erasmus OMT position (closed Jan 2026), LSE Employment Relations (Jan 2026 deadline — new cycle expected Jan 2027), Toulouse School of Management doctoral programme |
| PhD fellowship "organizational behavior" "developing economies" 2027 | No directly relevant new positions. Generic programme listings only. |
| PhD scholarship management "South Asia" OR "Nepal" OR "emerging economy" 2027 | Australia Awards Nepal (Master's only, no PhD). Fulbright link. Mittal South Asia Institute (Harvard — Raghunathan Fellowship, not PhD). |
| PhD vacancy "contingency theory" OR "organisational structure" Europe 2027 | No funded positions found. Academic papers only. |
| PhD "comparative management" OR "Nordic management" OR "Varieties of Capitalism" 2026 2027 | No open positions. NHH Economics PhD (finn.no) found — closed Jan 2026 deadline, economics only. |
| site:academicpositions.com PhD management Norway Sweden Germany Netherlands 2027 | Jönköping University Business Admin (Oct 1, 2026 — entrepreneurship/family business focus, score ~10). BI Norwegian Strategy (Dec 1, 2026, score ~10). HEC Paris (Apr 2027, score ~35, below threshold). |

---

## Additional Targeted Investigations

| Target | Outcome |
|---|---|
| EUR/Erasmus OMT-specific position | **CLOSED** — deadline was Jan 15, 2026. People & Organisations dept, supervisors incl. Greetje Corporaal, Jochem Kroezen. General ERIM fellowship (rsm-erim-2027, Jan 15, 2027) still active. |
| University of Göttingen — Future of Work / Int'l HRM | **CLOSED** — deadline Feb 22, 2026 (past). Supervisor: Prof. Fabian Jintae Froese. Research: Future of Work, AI, virtual/hybrid work, global mobility. TV-L E13 salary, 75%. Good topical fit but too late. |
| Kozminski University | 2026 cycle closed (June 15, 2026). 2027 cycle not yet announced. Entry in database (kozminski-2027, May 2027 deadline) maintained. |
| Gates Cambridge | Oct 14 deadline is US-only. Non-US (Nepal eligible) round: Dec 8, 2026 or Jan 6, 2027 depending on course. PhD-eligible. Score ~30, below threshold. Not added. |
| Australia Awards Nepal 2027 | Applications will reopen early 2027. **Master's only — no PhD.** Not relevant. |
| HEC Paris PhD Management | April 20, 2027 deadline. 5 years, €26,000/year + tuition waiver. "Organisational theory, OB, HRM, cross-cultural and international business" in dept. Score: ~35. Below threshold. Monitor. |

---

## Current Deadlines — All Open Items (scored database)

| Deadline | Item | Days Remaining | Urgency |
|---|---|---|---|
| **30 Sept 2026** | UNU-WIDER Visiting PhD Fellowship | **13** | 🔴 CRITICAL |
| **~10 Nov 2026** | Swiss Government Excellence Scholarships | ~54 | 🟠 URGENT |
| **1 Dec 2026** | HKPFS | 75 | 🟡 Watch |
| **15 Jan 2027** | RSM / ERIM Fellowship | 120 | 🟢 Active |
| **4 Jan 2027** | INSEAD PhD (OB field) | 109 | 🟢 Active |
| **15 Feb 2027** | Gothenburg doctoral (expected) | ~151 | 🔵 Monitor |
| **~1 Feb 2027** | IMPRS-SPCE (opens Dec 2026) | ~137 | 🔵 Monitor |
| **20 Apr 2027** | HEC Paris PhD Management | 215 | 🔵 Not in DB (score ~35) |
| **31 May 2027** | Kozminski University | 256 | 🟢 Active |
| **30 Jun 2027** | Tilburg University | 286 | 🟢 Active |

Asia-Pacific watchlist entries are not in this table — their deadlines are not yet confirmed for the current cycle (see the expansion section above).

---

## Pages That Failed to Load

| URL | Error | Workaround |
|---|---|---|
| wider.unu.edu/opportunity/visiting-phd-fellowship | 403 Client Error | Confirmed deadline via globalsouthopportunities.com (1 Sept 2026 post) |
| euraxess.ec.europa.eu | robots.txt blocked | Web search used instead |
| omt.aom.org (AOM OMT boards) | 403 Proxy Rejected | ApplyKite used to confirm EUR OMT position status |
| eur.nl/en/working-at-eur/vacancies/phd-position-organization-and-management-theory | 404 Not Found | Confirmed via ApplyKite — position closed Jan 2026 |
| globalsouthacademia.com | robots.txt ConnectTimeout | Alternative sources used |
| academicpositions.com (employer/FU-Berlin) | No listings on page | University direct site check recommended |

---

## Recommended Actions for Bij

1. **TODAY or this week (before Sept 30):** UNU-WIDER application — portal is open, deadline in 13 days. Developing-economy PhD research, priority for researchers from developing countries. Funding: EUR 2,100/month + travel + insurance for 3 months in Helsinki.

2. **By early November:** Swiss Excellence Scholarship — apply via Swiss Embassy Kathmandu. Covers PhD at Swiss universities (St. Gallen, ETH, EPFL, Lausanne). Nepal is an eligible country.

3. **By late November:** Lock HKPFS strategy — choose one HK university, confirm referees (only Prof. Flavio confirmed so far), finalise application. One lifetime application only.

4. **Gregory Jackson (KCL) — contact now:** He is actively accepting students. Draft a short, targeted supervisor contact email referencing his comparative institutional analysis work and Bij's Nepal institutional environment research. If HKPFS or Swiss Excellence funding materialises, KCL becomes a practical route.

5. **Watch from November:** NHH Bergen and Gothenburg for new 2027 cycle positions (both expected Jan–Mar 2027).

6. **New, lower priority — Asia-Pacific:** no immediate action needed. Before investing effort here, verify (a) whether the NZ and Australian schemes actually fund PhD study at a level clearing Bij's funding floor once converted to EUR, and (b) whether any of the 12 new portals has a named faculty member working on institutional theory, comparative management, or HRM. Neither check was completed this run.

---

*Generated by: Claude automated PhD scanner (scheduled task)*
*Next scheduled run: daily*
*Artifact database:* https://claude.ai/artifact/0c17f819-0f83-4a8e-a627-f359085cbef8
