---
date: 2026-07-06
time: "15:28"
timezone: BST
type: weekly
attendees:
  - "[[Christos Petropoulos]]"
  - "[[Edoardo Foco]]"
  - "[[Markus Seebacher]]"
  - "[[Oli Woolf]]"
  - "[[Ryan Bolton-Smith]]"
  - Parth Patel
duration: 1h03m
status: distilled
source: gdrive
source_file: "Eng leads weekly - 2026/07/06 15:28 BST - Transcript"
tags: [meeting]
---

# 2026-07-06 - Eng leads weekly

> [!note] Attribution
> "Simba - Boardroom" is the London office conference room mic capturing Markus and others in-room. Remote participants (Christos, Edoardo) are individually attributed. Owen was NOT in this meeting.

> [!summary] TL;DR
> Markus formally introduced Oli Woolf (Talentful) as engineering's dedicated recruiter, replacing Ryan's coverage. Parth Patel officially joining engineering from data - his first day, first hire at NALA into this role. Hiring pipeline: 4/4 pair programmings failed last week but 3 strong candidates from 90% POE in play. **Critical flag for Owen: Markus is relaxing the 4-day office policy to 3 days for engineering hiring, claiming Benji approval, but acknowledges Owen/People has NOT approved it.** Two significant incidents: API degradation took 2 weeks to detect (no alerts), and Kafka lag from bulk-tagging 85K users nearly took down the platform. Sardinia offsite confirmed Jul 27-30. Ahmed has a health scare (eye nerve damage, elevated heart rate).

## Decisions

- **Oli Woolf takes over engineering recruiting from Ryan (effective now)**
  - *Rationale:* Gradual handoff; Oli reviewed all documentation, Leo's interviews, and hiring guides. Ryan focuses on non-engineering roles.
  - *Source:* "he'll work on from engineering today onwards"

- **Engineering hiring geography opened to all EU/UK remote**
  - *Rationale:* London-only pool too small; following Benji's prior approval
  - *Source:* "the changes that we did is last week we opened the hiring from just in London in Europe"

- **3-day office policy for engineering candidates (DISPUTED)**
  - *Rationale:* Markus wants to relax from 4 to 3 days to attract talent. Claims Benji verbal approval. Owen/People has NOT approved.
  - *Source:* "I told Owen about that or asked them about it and no that's not approved. So I can do another round. I have it on brain from Benji."
  - **Owen action needed: This creates inequity in the London office. Clarify with Benji and Markus.**

- **4-way recommendation added to pair programming interviews**
  - *Rationale:* Forces interviewers to decide (progress/reject) instead of just giving stars. Should reduce false progressions to architecture stage.
  - *Source:* "it's forcing you to decide and second I think it's not only improving the pair programming but also re-lower the rejections on the architecture stuff"

- **Max 2-3 interviews per week per engineer**
  - *Rationale:* James had 4 last week and couldn't finish work. Edoardo had to step in.
  - *Source:* "Ideally, two interviews per week. Absolute maximum is three per week per engineer or else it's just impossible."

## Action items

- [ ] [[Edoardo Foco]] - Find accommodation for Sardinia offsite (Jul 27-30), 4 people + Markus separate
- [ ] [[Christos Petropoulos]] - Write up alerts overhaul proposal for Sardinia session
- [ ] [[Christos Petropoulos]] - Add incident for 400-user feature flag bug, run retrospective (scheduled Jul 7)
- [ ] [[Markus Seebacher]] - Define interviewer rota: EMs decide who goes in. Priority list: Bailey, James, Eric, TD, Wisdom (ready), Martin (to shadow), Simeon (candidate)
- [ ] [[Markus Seebacher]] - Review engineering KPIs doc with Christos and Edoardo (tomorrow morning)
- [ ] [[Markus Seebacher]] - Tell the data team about Parth Patel's move today, then announce in engineering
- [ ] [[Edoardo Foco]] - Get TrueLayer impact data using correct data points (previous numbers were wrong)
- [ ] [[Ryan Bolton-Smith]] / [[Oli Woolf]] - Propose hiring funnel conversion tracking (week-over-week pipeline deltas)
- [ ] **[[Me]] - Clarify 3-day vs 4-day office policy with Benji and Markus. Markus is telling candidates 3 days without People approval.**

## Open questions

- How do we define engineering KPIs that aren't cross-functional? (payments success rate depends on partnerships, providers, Rafiki)
- Who attends Sardinia offsite - does Ali need accommodation? (1.5-2 hours from his place, so yes)
- Ahmed's health - eye nerve damage + elevated heart rate. Christos monitoring. Probation review delayed to next week.

## Key discussion points

### Hiring pipeline -- brutal market, strong candidates emerging

> [!quote]- Source
> "the market is pretty brutal however there is some good news"

Ryan reported 7 talent screens booked for Senior/Lead Backend this week, 2 technical stages for Platform (with Christos and Edoardo). All 4 pair programmings last week failed -- not for catastrophic reasons but because candidates are close but not clearing NALA's bar. One Microsoft intern accepted a return offer 1 hour after screening. 5 platform candidates dropped out. However, 3 strong candidates from 90% POE (maritime company with large engineering team) are now in pipeline -- all senior, and NALA has previously offered people from there.

### 3-day office policy -- Markus pushing without People approval

> [!quote]- Source
> "I told Owen about that or asked them about it and no that's not approved. So I can do another round. I have it on brain from Benji. So I'm not going to go again and ask him again."

Markus wants one fully co-located London team (around Wisdom and Leo) and argues he can't build it with a 4-day requirement. He's telling candidates 3 days. He acknowledges Owen hasn't approved this but claims Benji gave verbal approval. This is a direct tension: Markus is prioritizing team-building over policy consistency. Owen needs to address this before it becomes a fait accompli.

### Incidents -- two weeks to detect API degradation

> [!quote]- Source
> "my issue is not so much that we introduced some bugs... It's more the fact that it took us two weeks to actually detect it which is bad"

Three compounding incidents: (1) API/DP degradation from query bugs took 2 weeks to detect because dashboards exist but alerts don't. (2) Kafka lag from tagging 85K users simultaneously nearly crashed the platform the next day -- only survived because of fixes from incident #1. (3) Feature flag bug blocked 400 users from creating cash wallets for a month -- Bailey left a future version gate during handover, someone accidentally turned the feature on. Comms sent to affected users.

Christos is advocating hard for a Sardinia offsite session to overhaul alerting infrastructure in one day -- move Grafana to Terraform, standardize templates, set up core alerts. Markus supportive. New metric proposed: "30-day percentage of action items closed coming out of an incident."

### Interviewer calibration -- building the rota

Interviewers assessed as ready: Bailey, James, Eric, TD, Wisdom. To shadow/onboard: Martin (Christos rates him highly -- "solid, very German in his approach"). Simeon in brackets (busy). Markus flagged a candidate who shouldn't have passed pair programming -- added to the hiring doc for review.

### Parth Patel joins engineering from data

Markus formally welcomed Parth Patel (first day in engineering). His priority: shift data from a finance-reporting function to impacting the product side of the business. First direct hire joining Jul 27. Team announcement planned for today. HiBob change needed.

## Candidate Knowledge notes

- "Self-inflicted incidents that take weeks to detect cost more in trust than in revenue" -- the 2-week API degradation and 1-month feature flag bug are both process failures, not engineering failures
- "Interview capacity has a hard ceiling at 3 per engineer per week before delivery suffers" -- Edoardo's observation, backed by James's week

## Propagation

### People notes
- **[[Christos Petropoulos]]:** Advocating for alerts overhaul at Sardinia offsite. Monitoring Ahmed's health (eye nerve damage, hospital). Bailey assessment: "already good" at hiring. Martin: "solid" candidate for interviewer rota.
- **[[Edoardo Foco]]:** Struggling with cross-functional KPI definition. Managing incident response. Owns Sardinia logistics. Max 2-3 interviews/week per engineer.
- **[[Oli Woolf]]:** Formally introduced as engineering recruiter. From Talentful, 14 years in recruitment (since 2012). Reviewed all NALA hiring documentation and Leo's interviews.
- **[[Ryan Bolton-Smith]]:** Handing off engineering to Oli. 3 strong candidates from 90% POE. Pipeline stats: 7 screens, 4 failed pair progs, 5 dropouts.
- **[[Markus Seebacher]]:** Pushing 3-day office without People approval. Parth Patel's first hire. Wants one fully co-located London team. New hiring funnel metrics requested. Offsite budget approved but "spend less."

> [!info]- Raw transcript
> Full transcript at `/tmp/transcripts/gdrive/Eng leads weekly - 2026／07／06 15:28 BST.md`
