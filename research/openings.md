# Phase 4a: Openings (before kill tests)

Built 2026-10-03 for the 8 strongest patterns (P1 to P7 and P9; see `patterns.md`). P8, P10, P11 and P12 were left out: P8 and P10 are medium and overlap others, P11's openings need pharmacy regulation, and P12 is the user's employer's market (conflict of interest).

Rule applied: **favour selling a finished job over selling a tool.** "Job" = the customer gets a result and does little. "Tool" = the customer does the work in software.

| ID | Pattern | Opening | Job or tool | Who pays |
|---|---|---|---|---|
| O1 | P1 | Companies House ID-verification chase-and-track service for small accountancy practices (track every client director's status, send chasers, report) before 17 Nov 2026 | Job | Accountancy practices |
| O2 | P1 | "Probation-proofing" for GB small employers before 1 Jan 2027: audit of staff under 2 years' service, probation schedule, review packs, manager prompts; then a monthly run-the-reviews service | Job | Employers with 10 to 100 staff |
| O3 | P1 | Done-for-you sexual-harassment prevention pack (risk assessment, policy, training record, third-party risks) for the 30 Oct 2026 duty | Job | Small employers |
| O4 | P1 | Fixed-price DMCC subscription-rules audit and fix for small subscription merchants (Shopify/Stripe): reminders, easy cancel, cooling-off, before Jan 2027 | Job | Subscription boxes, small SaaS |
| O5 | P1 | Martyn's Law "standard tier" pack for venues of 200 to 799 capacity (procedures, staff training log), UK-wide incl. NI, before spring 2027 | Job | Pubs, churches, halls, small venues |
| O6 | P2 | AI receptionist for independent hospitality and trades, billed per handled enquiry or booking (outcome pricing) | Job (run by software) | Restaurants, trades |
| O7 | P2 | Sponsor-licence compliance admin for small UK visa sponsors (right-to-work records, reporting duties, audit readiness) | Job | Small sponsors |
| O8 | P2 | Labour-cost and rota optimiser for pubs squeezed by NICs and the living wage | Tool | Pubs |
| O9 | P2 | Apprenticeship evidence and off-the-job-hours admin done for SME employers and small training providers | Job | Training providers, SMEs |
| O10 | P2 | Funded-childcare (30 hours) billing and council-claim admin for small nurseries | Tool/job | Nurseries |
| O11 | P3 | Rescue and hardening of "vibe-coded" apps (Lovable/Replit/Bolt prototypes) onto production Supabase + React: auth, security, tests, fixed price | Job | Non-technical founders, small firms |
| O12 | P3 | EU AI Act Article 50 transparency kit (chatbot disclosure, AI-content labels) for small EU-facing sites | Tool | Small firms selling into EU |
| O13 | P3 | Done-for-you B2B newsletter for expert firms losing Google traffic ("Google zero"): we write, send and grow an owned list | Job | Consultancies, B2B firms |
| O14 | P3 | "Verified human" provenance badge and audit trail for creators and brands | Tool | Creators, craft brands |
| O15 | P3 | Fixed-price AI workflow set-up for 5 to 50 person firms (one workflow, live in 2 weeks, then a monthly care plan) | Job | Small firms |
| O16 | P4 | Shortlisting-as-a-service for small employers flooded with AI applications: we screen, run a short work-sample test and deliver a top-10 shortlist per role, fixed fee | Job | SMEs hiring without HR. **Overlaps Nudge** |
| O17 | P4 | Candidate identity and interview-fraud check per candidate for remote hiring | Job | SMEs, agencies |
| O18 | P4 | Graduate job-search service: tailored applications, practice assessments, for the 140-applicants-per-job market | Job | Graduates, parents |
| O19 | P4 | AI-in-hiring compliance audit (bias, transparency, EU AI Act high-risk from Dec 2027, ICO) for recruitment agencies and HR tech | Job | Agencies, HR tech vendors |
| O20 | P5 | NI/ROI solar and battery payback checker that sells qualified leads to installers | Tool + leads | Installers |
| O21 | P5 | Grant and grid-paperwork done for small MCS/SEAI installers (MCS certificates, DNO forms, grant claims, handover packs) | Job | Small installers |
| O22 | P5 | Battery and tariff optimiser for the 2m+ homes with solar | Tool | Homeowners |
| O23 | P5 | EPC C by 2030 plan per rented property (likely upgrades, cost vs £10k cap, grants) for landlords | Job | Landlords (England & Wales) |
| O24 | P5 | Small-business energy bill audit and contract renegotiation, paid from savings | Job | Small firms |
| O25 | P6 | Gift and estate record-keeper for the April 2027 pension-IHT change (7-year gift log, estate snapshot), white-labelled to IFAs | Tool | IFAs, families |
| O26 | P6 | Care-fee runway and funding-options report for adult children (self-funding, council thresholds, NHS CHC), referral income | Job | Families / care-fee advisers |
| O27 | P6 | Estate-admin task service for executors (non-legal: closing accounts, notifications, tracking), per-estate fee | Job | Executors |
| O28 | P6 | Equity-release lead generation | Leads | Lenders/advisers |
| O29 | P6 | Downsizing and house-clearance concierge for older NI homeowners | Job | Older owners, families |
| O30 | P7 | Cross-listing and repricing tool for resellers on Vinted/eBay/Depop | Tool | Part-time resellers |
| O31 | P7 | White-label buy-back/resale storefront for small fashion labels | Tool/job | Small labels |
| O32 | P7 | "Sell my wardrobe for me": done-for-you resale (we photograph, list, ship, take a cut) | Job | Busy people |
| O33 | P7 | TikTok Shop / live-selling operations for small UK brands | Job | Small brands |
| O34 | P7 | Landed-cost and duty checker for UK sellers shipping to the EU under the €3 per item duty | Tool | UK e-commerce sellers |
| O35 | P9 | Defence-supplier readiness done for NI SMEs: Cyber Essentials Plus prep, capability statement, supplier registrations, tender shortlist | Job | NI engineering SMEs |
| O36 | P9 | AI-summarised defence and public tender alerts for NI engineering firms | Tool | NI SMEs |
| O37 | P9 | Windsor Framework dual-market compliance helper for NI exporters (green/red lane, UKCA/CE, VAT) | Tool | NI exporters |
| O38 | P9 | Supplier quality-document portal for prime contractors' NI supply chains | Tool | Primes / tier-2 suppliers |

## Desk kills (before the subagent checks)
- **O28 Equity-release lead generation:** killed on check 5 (licence). Introducing people to equity release is a regulated activity in the UK and needs FCA authorisation or an appointed-representative arrangement. Recorded in `killed.md`.

All others (37) go to one subagent each for the 7 checks. Results in `research/checks/`.
