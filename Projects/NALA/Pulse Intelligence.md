---
aliases: [Pulse Intelligence, NALA Feedback Loop]
tags: [project, pulse, windmill, eys]
---

# Pulse Intelligence

## What this is

Structured capture and analysis of NALA's quarterly "Feedback Loop" pulse surveys run via Windmill. These are the org's primary voice-of-employee channel and drive the public People team roadmap in Notion.

## Pulse architecture

6 department-level pulses, 12-week recurring cycle, anonymous responses. Questions: "What's working well at NALA?" / "What's not working well at NALA?"

| Pulse | Enrolled | Cadence | Streaming to |
|-------|----------|---------|-------------|
| Eng & Prod | 29 | 12-week | - |
| Operations | 64* | 12-week | #team-people-mgmt |
| Finance/Treasury/People/IT/Data | 22 | 12-week | #team-people-mgmt |
| Legal & Compliance | 6 | 12-week | #team-people-mgmt |
| Revenue | 6 | 12-week | - |
| Leadership & Exec | 6 | 12-week | #team-people-mgmt |

*Operations has heavy exclusion list - effective enrolled is lower.

## How to use this note

Each quarterly run gets:
1. A **run analysis** section below (dated, with response rates, themes, and verbatim signals)
2. **Cross-quarter theme tracking** in the Themes Tracker table (trending up/down/new/resolved)
3. **Roadmap actions** linking themes to People team deliverables (with DRI, deadline, status)

When a theme appears 2+ quarters running without action, flag it RED in the next brief.

## Notion Board Integration

The public "You Said, We Did" initiatives board lives in Notion as a child of the April pulse page. All pulse-driven actions are tracked there as the single source of truth.

- **Board:** [People Team Roadmap: Now / Next / Not Now](https://app.notion.com/p/37556eaacda581c8be0ff3a6b2541d89)
- **Database:** `collection://14e8e8df-0067-4fa8-ae3f-6a158c17f623`
- **Schema:** Initiative (title), Status (Draft/Heard/Planning/In Progress/Live/Not Now), Theme (multi-select), Pulse Cycle (multi-select: Q4 2025, Q1 2026, Q2 2026...), What we heard, What we are doing, Public Notes, Owner, Target/Done
- **Draft workflow:** New items go in as Status=Draft (filtered out of the public board view). Owen reviews, edits, then moves to Heard/Planning/etc. to make visible.
- **Q1 items tagged:** All 8 existing items tagged with `Q1 2026 (Apr)`.
- **Q2 items created (Draft):** Strategic direction, 48hr CS briefing, L&D budget comms, Nairobi office perks.

## Roadmap Actions (vault mirror)

| Theme | Source Run | Notion Status | DRI | Notes |
|-------|-----------|---------------|-----|-------|
| UK benefits (PMI) | Q1 2026 (Apr) | In Progress | [[Me]] | UBO collected Jul 1, Benji announcing Jul 12 |
| Strategic direction / prioritisation | Q1+Q2 | Draft | [[Me]] | Framed as "Heard, being reviewed by leadership". Now 5/11 Eng. Brief Peter Jul 7. |
| Career progression / transparency | Q2 2026 (Jun) | Draft | TBD | New theme: Eng (share value, ownership) + Ops (detailed framework request) |
| Product-CS launch coordination | Q2 2026 (Jun) | Draft | TBD | 48hr pre-launch briefing SLA. Now 3/11 Ops. |
| L&D budget transparency | Q2 2026 (Jun) | Draft | [[Lynnette Mutugi]] | Comms on current policy. Now 2/11 Ops. |
| Nairobi office perks (fruit) | Q2 2026 (Jun) | Draft | [[Lynnette Mutugi]] | Review and reinstate or communicate. Now 3/11 Ops. |
| Internal tools hosting | Q2 2026 (Jun) | - | TBD | New: Ops builds tools but no clear path to hosting (IT/InfoSec/Eng process) |

## Themes Tracker (cross-quarter)

| Theme | Q4 2025 (Jan) | Q1 2026 (Apr) | Q2 2026 (Jun) | Trend |
|-------|:---:|:---:|:---:|-------|
| Strategic direction / prioritisation | - | **Eng 3/10, Fin 1/6, Rev 1/2** | **Eng 5/11** | **CRITICAL -- 2 QUARTERS** |
| Career progression / comp clarity | - | Eng 2/10, Ops 2/12 | Eng 1/11, Ops 1/11 | PERSISTENT |
| Talent attrition / org instability | - | Eng 2/10, Ops 1/12, Fin 1/6, Rev 1/2 | Eng 1/11 | PERSISTENT (broader in Q1) |
| Benefits gap (PMI/dental/pension) | - | Eng 2/10, Fin 1/6 | Eng 1/11 + Actioned | RESOLVING (PMI Aug) |
| Product-CS launch coordination | - | - | Ops 3/11 | NEW in Q2 |
| Nairobi office perks | - | - | Ops 3/11 | NEW in Q2 |
| L&D / training gaps | - | Legal 1/2 | Ops 2/11 | GROWING |
| Equity allocation / transparency | - | Eng 1/10, Fin 1/6 | - | Q1 only (investigate) |
| Too many meetings / ritual bloat | - | Fin 1/6 | - | Q1 only |
| Manager span / 1:1 consistency | - | Fin 1/6 | Fin 1/3 (execution gap) | PERSISTENT |
| Compliance capacity / turnaround | - | Eng 1/10, Ops 1/12 | - | Q1 only |
| Performative internal comms | - | - | Eng 1/11 | NEW in Q2 |
| Cross-team process alignment | - | Ops 1/12 | Eng 1/11 | PERSISTENT |
| Internal tools hosting pathway | - | Ops 1/12 (BAU transition) | Ops 1/11 | PERSISTENT |
| Hybrid work (positive) | - | - | Ops 3/11, Fin 1/3 | POSITIVE |
| Team spirit / collaboration | - | All depts | All depts | POSITIVE -- CONSISTENT |
| AI adoption (positive) | - | Eng 1/10, Ops 1/12, Legal 1/2 | Ops 1/11 | POSITIVE |
| Ownership / trust (positive) | - | Eng 3/10, Ops 3/12 | Ops 2/11 | POSITIVE -- CONSISTENT |

*Q4 2025 data not yet backfilled from Windmill. TODO: pull historical runs and populate.*

---

## Q1 2026 Run (Apr 6) — BACKFILLED Jul 5

### Response Rates

| Department | Responded | Enrolled | Rate |
|------------|-----------|----------|------|
| Eng & Prod | **10** | 29 | **34%** |
| Operations | **12** | ~20 effective | **~60%** |
| Finance/Treasury/People/IT/Data | **6** | 22 | **27%** |
| Legal & Compliance | 2 | 6 | 33% |
| Revenue | 2 | 6 | 33% |
| Leadership & Exec | 0 | 6 | 0% |
| **Total** | **32** | **~89** | **~36%** |

### Eng & Prod (10 responses)

**Working well:** Speed of execution (KES Wallets, Send Money redesign). AI/Cursor/MCP adoption. Strong team spirit, great coworkers. London office culture. Ownership and accountability. Technical process (RFC, demos, shoutouts). Top management effectiveness. Company growth visible year-over-year.

**Not working:**
- **Strategic direction / changing priorities (3/10):** "Hard to tell what is the long term vision as short term goals change frequently." "We're often changing priorities, chasing the next thing... it doesn't give people confidence that leadership know what the plan is." "Prioritisation feels more short-term or reactive."
- **Benefits / compensation (2/10):** "Lack thereof... we need more incentive for high performing individuals to stay on-board (lacking full medical, dental, good pension, lifestyle benefits)." "Benefits are light / non-existent."
- **Career progression / titles / equity (2/10):** "No structure in terms of titles and getting raise or bonuses." "Lack of clear career guidance and progression."
- **Talent attrition / org stability (2/10):** "Layoffs and firing people happen very often. It's hard to feel stable." "The org is very unstable, a lot of key people have left or been let go."
- **Fire-fighting culture (1/10):** "Lack of structure and strategic direction... for the past few years it felt we're fighting fires. The Modulr problem could've been avoided... the Lead bank problem could've been avoided... the Sila problem..."
- **Compliance capacity (1/10):** "Compliance function has experienced high churn and appears to be under sustained pressure."
- **Equity allocation (1/10):** "Lots of people have not been issued their options. Equity allocation is really low, and not at all competitive."
- **Too many meetings (1/10):** "We spend a lot of time in meetings. Key people spend time on decks, sometimes it feels a bit aimless."
- **Ticket readiness inconsistency (1/10):** "Pockets of ambiguity" when moving fast without clear requirements.

### Operations (12 responses)

**Working well:** Team culture and collaboration (strong across all respondents). Cross-functional support. Ownership and autonomy. AI tools accelerating projects. Product iteration impressive given team size. SOPs improving. Learning environment. Mission and impact motivating.

**Not working:**
- **Career progression / compensation clarity (2/12):** "Compensation growth is not descriptive and clear." "Clearer documentation on internal career paths" + specific request for CS-to-Eng transition pathway.
- **Talent attrition (1/12):** "A lot of very good talent and some people that I look up to are constantly leaving NALA for better opportunities."
- **Pay disparity (1/12):** "Pay disparity within teams for teammates working at the same level."
- **Compliance/LOD2 turnaround (1/12):** Tasks stuck on Zazu, unpredictable ETAs, duplicate account deletion inconsistency.
- **Process clarity at scale (1/12):** "Occasional gaps in process clarity, especially as the company scales quickly."
- **Task information quality (1/12):** Insufficient info when tasks assigned, templates not always followed.
- **Manual processes (1/12):** "Some processes are still too manual across markets."
- **Eng support access (1/12):** "Engineering support is not consistently accessible when we need API access or integration help."
- **BAU transition for new tools (1/12):** "Five months later, there hasn't been much movement in operationalising [Reg E Radar]."

### Finance/Treasury/People/IT/Data (6 responses)

**Working well:** Automation and speed of delivery. Structured onboarding. 1:1s and manager support during probation. Demoday and EmpathySzn improving. Cross-functional collaboration. AI adoption. People team building real tools. Peter (CFO) bringing professionalism and directness.

**Not working:**
- **Strategic direction / shifting priorities (1/6):** "We're often changing priorities, chasing the next thing B2B, wallets, kes account, 16 new markets, stable coins, bi lateral flows."
- **Benefits (1/6):** "There are essentially no benefits, everything is statutory."
- **Equity not issued (1/6):** "Lots of people have not been issued their options."
- **Too many meetings (1/6):** "Key people, leaders in the org spend time on decks, sometimes it feels a bit aimless."
- **Management span too wide (1/6):** "Not enough managers... managers had like 15 or 20 reports. Some managers do not do 1:1s consistently."
- **Org instability (1/6):** "A lot of key people have left or been let go in a short space of time. It makes people nervous."
- **Documentation / onboarding gaps (1/6):** Centralized resources for key processes needed.

Note: One respondent was Owen (non-anonymous, employeeId matches). His response included: People team building real tools, Peter CFO as positive addition, benefits light, managers with 15-20 reports, equity not issued, shifting priorities, org instability.

### Legal & Compliance (2 responses)

**Working well:** AI/automation adoption. Strong culture and values. Innovative brand. Best practices aligned with tech.

**Not working:**
- **Training gaps (1/2):** "Lack of trainings... we have to learn by ourselves how to use" new systems/tools/AI.
- **Communication cascade (1/2):** "Key stakeholders are not engaged early enough at the inception stage."

### Revenue (2 responses)

**Working well:** Speed of delivery. Cultural rituals (LKS, EmpathySzn, Demo Day). Growth trajectory. Ownership and autonomy. Collaborative environment. Focus on continuous improvement.

**Not working:**
- **Org instability / turnover (1/2):** "High level of personnel changes... frequent turnover and restructuring can create instability."
- **Shifting priorities (1/2):** "Focus areas change quickly or without sufficient context."
- **Manager churn (1/2):** "Changes in managers every few months can make it difficult to build momentum."
- **Communication gaps (1/2):** "Important information doesn't always cascade down to all relevant teams."
- **Knowledge silos (1/2):** Proposed weekly cross-functional context exchanges.

### Leadership & Exec (0 responses)

No data. Second consecutive cycle with 0%.

### Q1 Cross-Department Analysis

**#1 signal: Strategic direction was already a concern in Q1.** Three Eng respondents + 1 Finance respondent flagged it independently: changing vision, short-term priorities, lack of long-term product thesis, fires that could have been avoided (Modulr, Lead Bank, Sila named specifically). This means the Q2 signal (5/11 Eng) is not new -- it's an escalation of a pattern already present in Q1.

**#2 signal: Benefits gap is a retention risk.** Two Eng + 1 Finance respondents flag lacking medical, dental, pension, lifestyle benefits. This is being actioned (PMI in flight for Aug launch) but was a Q1 concern before it was surfaced.

**#3 signal: Career progression / compensation clarity spans departments.** Eng (titles, bonuses), Ops (comp growth path, internal moves), Finance (equity not issued) all converge on the same gap: people don't understand how to grow, get paid more, or move internally.

**#4 signal: Org instability / attrition is felt across Eng, Ops, Finance, Revenue.** "Layoffs happen often." "Key people leaving." "Manager changes every few months." This is broader than Q2's single Eng attrition signal -- in Q1 it appeared in 4 departments.

---

## Q2 2026 Run (Jun 29) — FINAL (deadline passed Jul 4)

### Response Rates

| Department | Responded | Enrolled | Rate |
|------------|-----------|----------|------|
| Eng & Prod | **11** | 29 | **38%** |
| Operations | **11** | ~20 effective | **~55%** |
| Finance/Treasury/People/IT/Data | **3** | 22 | **14%** |
| Legal & Compliance | 1 | 6 | 17% |
| Revenue | 0 | 6 | 0% |
| Leadership & Exec | 0 | 6 | 0% |
| **Total** | **26** | **~89** | **~29%** |

### Eng & Prod (11 responses)

**Working well:** Technical grooming improving alignment. Good delivery pace. Refactoring time appreciated. Strong team spirit. Mission motivating. Mobile chapter technical excellence (linting, CI/CD). London office culture, relaxed but performing. Hiring push making roadmaps achievable. Company-wide response to Modulr/Banked restrictions. Salary always on time. 1:1 feedback fair and contributing to growth.

**Not working (critical):**
- **Strategic direction (5/11):** "Can't prioritise... trying to do too much, to not a high enough standard." "Plans changing very quickly and very often." "Many bets but we can't stick with one long enough." "It's already Q3 and we have no Q3 plans announced with teams." "Lack of structure and focus makes us slow" -- with specific TrueLayer example: eng finished, partnerships delayed 3 weeks, forced rollout without fallback, "two weeks of significant volume and revenue loss."
- **Career progression + share value (1/11):** "Lack of career progression, ownership, product work and no insights into share value."
- **Talent attrition (1/11):** "Losing great people all the time, due to frustration and lack of direction."
- **Performative comms (1/11):** "Companies that have good morale don't need to tell employees that things are good... being told those things ends up demoralising people."
- **UK benefits gap (1/11):** "Perks are not very good compared with other startups, health care for example, and dental coverage." (PMI in flight -- validates urgency.)
- **Cross-team process alignment (1/11):** "AI cannot solve all of our problems. Writing code is usually not the bottleneck." Process between teams is the constraint.
- **Documentation lag (1/11):** Processes not keeping up with new automations.
- **Fire-fighting culture (1/11):** "We do not take potential fires seriously, until they are massive fires. Then we spend all of our time fire fighting."

### Operations (11 responses)

**Working well:** Collaborative culture, trust, approachable people. Hybrid work (Nairobi) -- very popular (3 respondents). Fraud Ops chargeback win rate up 47 points. AI in customer support (testing). Profitability focus. Kenya corridor funded over heavy weekend without closing. Ownership and trust -- opportunity to build beyond job description (Reg E Radar, OT Helper, Riposte built by Ops). SOPs improving issue resolution. App UX improvements (in-app phone number update). People culture and departmental tools.

**Not working:**
- **Product-CS handoff (3/11):** "CS should know 48 hours before a promotion or new product launch." "Product team will launch without training the support team." "Synchronisation of departments is not flowing well."
- **Nairobi office perks (3/11):** Fruit provision removed -- noticed and missed by multiple people. "We need to bring it back."
- **L&D budget (2/11):** "Communicated when I joined... haven't seen any updates." "If the program has changed, it would be great to have transparent communication."
- **Career progression clarity (1/11):** Detailed request for visible framework -- "how progression works, how internal moves happen, what skills are needed." Especially for technical/cross-functional roles.
- **Internal tools hosting pathway (1/11):** "The process can sometimes feel unclear or overly difficult to navigate." Wants clearer pathway: what checks, who approves, timeline, lighter process for small tools.
- **Cross-functional comms during incidents (1/11):** Updates/ETAs from external partners slow during operational incidents.
- **Contract-to-permanent (1/11):** Hoped for permanent contract but "unfortunately that is not possible."

### Finance/Treasury/People/IT/Data (3 responses)

**Working well:** Employee engagement activities (World Cup). Staff recognition and internal promotions. Hybrid work. Culture and people. Clarity in business direction from leadership.

**Not working:**
- **Manager execution gap (1/3):** "Are managers able to translate [business direction] to action?" -- contrasts with Eng "no direction" signal. Finance sees direction from top but questions middle management execution.
- Systems overlap (but leadership corrects when raised). 1 respondent had nothing to flag.

### Legal & Compliance (1 response)

**Working well:** Teamwork, everyone supports each other.

**Not working:** "A few compliance gaps" (vague, no detail).

### Revenue (0 responses)

No data. 0% response rate -- consider whether this pulse needs restructuring or nudging.

### Leadership & Exec (0 responses)

No data. 0% response rate -- consider whether this pulse needs restructuring or nudging.

### Cross-Department Analysis (FINAL)

**#1 signal: Strategic direction is now critical.** Five of 11 Eng respondents (45%) independently describe the same problem: NALA changes direction too often, starts Q3 with no communicated plan, pushes "made up deadlines" on work that "doesn't end up delivering value," and doesn't take fires seriously until they're massive. The TrueLayer example gives it quantifiable teeth: 3-week delay between eng completion and partnerships readiness caused "two weeks of significant volume and revenue loss." This is corroborated by the attrition signal and the "many bets, can't stick with one" pattern. This is not a People-fixable issue -- it needs CEO/CTO attention.

**#2 signal: Career progression is emerging.** Two independent signals (Eng + Ops) request visible progression frameworks, share value transparency, and clarity on internal moves. The Ops respondent is particularly detailed -- someone who built 3 internal tools and wants to know how that translates to growth. This is a People-addressable theme and connects to EYS.

**#3 signal: Product-CS coordination gap is reinforced.** Now 3/11 Ops respondents (27%). Consistent message: launches happen without CS briefing. Fixable with a 48hr pre-launch SLA.

**#4 signal: Nairobi perks + L&D are reinforced.** Both grew from the partial dataset. Fruit is symbolic (cheap goodwill). L&D is a trust issue -- people were promised something and haven't heard an update.

**New signal: Manager execution gap (Finance).** One Finance respondent sees "clarity in business direction from leadership" but asks "are managers able to translate this to action?" This is a fascinating counter-narrative to the Eng "no direction" signal. It suggests the direction may exist at the top but isn't cascading. Worth investigating: is this a communication problem or a middle-management capability gap?

**Positive signals remain strong:** Team spirit and collaboration are consistent across all responding departments. Hybrid work is a standout positive in Nairobi. Ownership culture in Ops is producing real tools. Technical execution in Eng is healthy despite strategic frustration. The Modulr/Banked crisis response was noticed and appreciated.

### What / So What / Now What / When

**What:** 26 responses across 4 departments (Revenue + Leadership silent, 0%). Strategic direction is now the dominant signal at 45% of Eng respondents. Career progression emerged as a new cross-functional theme. All Q2-partial themes reinforced or grew.

**So What:** The direction signal has moved from "concerning" to "critical." Five independent voices, a specific revenue-loss example, and corroboration from the attrition signal make this the strongest finding in the Q2 dataset. The Finance "manager execution gap" signal complicates the picture -- it suggests direction may exist at exec level but isn't reaching teams. If that's true, the fix is cascade/communication, not strategy itself. Either way, this needs exec conversation urgently.

Career progression is the most People-actionable new theme and connects directly to EYS. The respondents aren't asking for promotions -- they're asking to understand the rules of the game. This is exactly what the EYS framework should deliver.

**Now What:**
1. ~~Complete dataset after Jul 4 deadline~~ DONE (Jul 5)
2. Brief [[Peter Gulliver]] on the direction signal -- framing: "5 of 11 Eng respondents flag strategic direction as the #1 concern, with a specific revenue-loss example. Finance sees direction from top but questions middle-management cascade."
3. Propose Product-CS 48hr briefing SLA to Nico/Josh
4. [[Lynnette Mutugi]] to own L&D comms + Nairobi perks review
5. Add career progression to EYS scope -- this is what the framework should address
6. Investigate internal tools hosting pathway -- surface to Josh or Nico
7. Draft Notion board tickets for career progression + internal tools hosting
8. Backfill Q1 2026 (Apr) data from Windmill for trend comparison

**When:**
- ~~Jul 4: Pull final dataset~~ DONE
- Jul 7 (Monday): Brief Peter on the direction signal + career progression theme
- Jul 7: Lynnette 1:1 -- L&D comms, Nairobi perks, career progression in EYS
- Jul 14: Propose Product-CS SLA in CFO Directorate or via Josh
- Jul 14: Surface internal tools hosting issue to Josh
