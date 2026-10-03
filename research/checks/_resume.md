# Resume instructions (for the follow-on session)

Original brief: wide research study for a solo builder in Belfast; phases 1-3 are done (`research/scan/`, `patterns.md`, `predictions.md`). Phase 4 is half done: `openings.md` lists 38 openings, `killed.md` has 20 kills. These 18 were NOT tested because search ran out: O20-O27, O29-O38.

## Step 1: Phase 4, finish kill tests
For each untested ID, launch one subagent with `checks/_brief.md` plus the hint below. Run at most 10 subagents at once. Each may use **at most 8 searches**. Update `killed.md` (move each from "Not tested" to the kill table or a survivors list).

| ID | Check especially |
|---|---|
| O20 | NI/ROI solar calculators and lead-gen (SEAI calculator, GreenMatch, Checkatrade, Bark, Solar Together); price per lead; data-protection rules on selling leads |
| O21 | OpenSolar, easyMCS, Spruce, DNO/ENA connections portal, MCS umbrella schemes, outsourced installer admin services; prices |
| O22 | Octopus Flux/Intelligent built-in optimisation, Predbat (free), GivEnergy/Tesla apps, Axle Energy, Solar Assistant |
| O23 | Kamma, Sero, Hestia, Furbnow, Domna, EPC register recommendations, PAS 2035 retrofit coordinators; whether a DEA accreditation is needed |
| O24 | Ofgem broker/TPI rules 2024-26, Energy Ombudsman TPI scheme, Bionic, Love Energy Savings, Make It Cheaper, Zenergi |
| O25 | Octopus Legacy, Farewill, Kinherit, IHT gift tracker apps, adviser platforms (Intelliflo, Voyant, Timeline); FCA advice/promotion boundary |
| O26 | Which? Later Life Care, Age UK, Paying for Care, MoneyHelper, Lottie, Autumna, CHC claims firms; FCA introducer rules for care-fee annuities |
| O27 | Legal Services Act reserved probate activities (E&W and NI); Settld, Life Ledger, Tell Us Once, Death Notification Service, Farewill, Exizent |
| O29 | UK senior move managers (ASMM), Belfast clearance firms, prices; operational fit for someone with a day job |
| O30 | Vendoo, List Perfectly, Crosslist, Dotb, Primelister; Vinted ToS on automation and enforcement |
| O31 | Archive, Trove, Recurate, Reflaunt, Treet, Shopify resale apps; minimum brand size |
| O32 | Vinted/eBay rules on selling for others; HMRC platform reporting; Thrift+, Reskinned, consignment commission rates |
| O33 | UK TikTok Shop Partner agencies with retainers; Kalodata/FastMoss/Euka prices; TikTok's free seller tools |
| O34 | Zonos, Avalara, SimplyDuty, Shopify Markets, Global-e, carrier duty calculators |
| O35 | Free support (Invest NI, ADS NI, Catalyst, DASA, Defence Office for Small Business Growth), Cyber Essentials prep rules (IASME), consultancy prices |
| O36 | Tussell, Stotles, Tracker, BiP/DCI, Tenders Direct, free Find a Tender alerts; prices |
| O37 | Trader Support Service (free) and its future, InterTradeIreland, customs intermediaries; whether customs-agent status is needed |
| O38 | Exostar, Ideagen Q-Pulse, Qualio, Net-Inspect, prime-mandated portals; Cyber Essentials Plus / export-control requirements |

## Step 2: Phase 5, critic
One subagent attacks every survivor: missed rivals, weak evidence, reasons it would fail. Drop or downgrade. Reserve about 30 searches for this.

## Step 3: Phase 6, rank
Score each survivor out of 100: proof people pay 25, how empty the field is 20, timing 20, size of prize 10, speed to first sale 10, fit 15. If fewer than 5 survive, include the best near-misses from `killed.md` (O13 narrow HR newsletter, O19 vendor bias audits), clearly labelled as near-misses, and say plainly that fewer than 5 survived.

## Step 4: research/REPORT.md
1. One-page plain-English summary. 2. Simple diagram of patterns (reuse `patterns.md`). 3. Predictions table (from `predictions.md`). 4. Top 5 openings: what, evidence links, who pays and how much, biggest risk, one-week test using real money. 5. Kill list with reasons. 6. Monthly watchlist of early signs. 7. Full source list with dates (collect links from all scan and check files).

Rules: never invent a number; every claim needs a link and date or "not found"; plain English; no questions to the user, log assumptions in `assumptions.md`. Note: this environment blocks direct fetches of gov.uk/ons.gov.uk and most sites, so cite search-result sources and flag them as not checked at the original page. If WebSearch hits its limit, stop, write what you have into REPORT.md with a clear "incomplete" banner, commit and push.

Commit and push to branch `research/world-scan-2026-10` after each step.

## Status (2026-10-03, follow-on session)
All steps done. Phase 4: all 18 killed (38 of 38 in total). Phase 5: `critic.md`. Phase 6: `ranking.md`. Report: `REPORT.md`. Sources: `SOURCES.md`.
