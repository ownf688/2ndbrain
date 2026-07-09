---
date: 2026-07-08
time: "14:45"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - Kapil Pau
interviewer: "[[Ryan Bolton-Smith]]"
candidate: Kapil Pau
role: "Senior Backend Engineer"
duration: 32m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/460596586"
tags: [meeting, interview, metaview]
---

# 2026-07-08 - Kapil Pau - Senior Backend Engineer Screen

> [!summary] TL;DR
> Ryan screened Kapil Pau for Senior Backend Engineer. Kapil was laid off from Meta in January 2026 and is actively looking for smaller companies with more ownership. Previously at IBM and AWS. At AWS he was cherry-picked by his director to lead a new engineering function in London, growing a team from 0 to 1 (6-18 engineers using an OAT lending model). Go is his preferred language (5/5 self-rating). Strong answers on idempotency (transaction IDs), distributed vs local locking, and AI usage (treats Claude as a junior engineer). Salary is the blocker: Meta total comp was 220-250k GBP, cash base ~120k, and Kapil needs 140-150k cash to cover mortgage. Ryan was transparent that NALA base caps around 120k but suggested lead/principal leveling could unlock more if Kapil performs exceptionally in interviews. UK citizen, immediately available. Wants to do 5 days in office. Progressing to next stage.

## Decisions

- **Decision:** Progress Kapil to next stage (Go-based live coding exercise)
  - *Rationale:* Strong technical profile, leadership experience, Go proficiency, good cultural signals (wants impact + ownership)
  - *Source:* "I'll be able to let you know by tomorrow afternoon because I'm catching up with the engineering managers in the morning"

## Action items

- [ ] [[Ryan Bolton-Smith]] - Discuss Kapil's salary expectations with engineering managers - flag the 140-150k cash ask vs. 120k cap
- [ ] [[Ryan Bolton-Smith]] - Send Kapil next-stage scheduling (Go live coding exercise, 30 min prep time)

## Open questions

- Salary gap: Kapil needs 140-150k cash, NALA caps at ~120k base. Can equity + lead/principal leveling bridge the gap?
- Large company pattern: IBM, AWS, Meta - all massive orgs. Can Kapil actually thrive in an 18-person engineering team with less structure?
- Go proficiency: self-rated 5/5 but primary professional use was at IBM. Live coding will validate.

## Key discussion points

### Career trajectory and motivation

Kapil was part of Meta's January 2026 layoffs. He had internal transfer options but chose to exit, seeking "somewhere smaller where I can have a bit more impact and ownership and leadership." At AWS (his longest role), he was cherry-picked by his director to lead a new engineering function in London. Started with just him, his manager, and a PM. Grew the team to 5-6 FTEs plus an OAT (Other-As-a-Team) model lending engineers from other managers, managing 6-18 people. At Meta he worked on Quest for Business and Meta Horizon (VR developer portal).

> [!quote]- Source
> "I sort of chose to exit the business, try and go somewhere smaller where I can have a bit more impact and ownership and leadership as well."

### Technical screening

Ryan ran through scenario questions:
- **Unique users report (Postgres):** Kapil gave a simple SQL answer (select distinct where date > 7 days). Correct but basic.
- **Idempotency (duplicate sends):** Strong answer. Proposed generating transaction IDs at intent-creation, then rejecting duplicate sends. Good understanding of the funnel tracking benefit.
- **Distributed vs local locking:** Clean explanation of why local locks fail across load-balanced servers. Understood the core concept well.
- **Kafka message ordering:** Identified the use case (balance checks before sends) and discussed authoritative order ID providers, limitations of timestamps and incremental IDs at scale. Solid.
- **Go testing:** Pragmatic view - "100% test coverage is a false metric." Uses AI to write tests from specs before building, then tests against actual implementation. Smart approach.

> [!quote]- Source
> "I treat it as a junior engineer, so I don't sort of blindly trust it to do everything."

### AI usage philosophy

Kapil uses Claude for code (treats it as a junior engineer - gives it implementation plans, reviews its output, never blindly trusts) and Gemini for data/search. Gets AI to write tests from spec before he builds, then validates against implementation. This is a mature, thoughtful approach.

> [!quote]- Source
> "Before I give it a task, I get it to sort of detail an implementation plan for me, say what it's going to build me, and then let it build."

### Salary and logistics

- Meta total comp: 220-250k GBP (base ~120k, rest was stock)
- Minimum cash need: 140-150k (mortgage obligation)
- Ryan transparent: NALA base probably caps at 120k, but exceptional interview performance could unlock lead/principal territory
- UK citizen, immediately available (with potential August holiday)
- Wants to come in 5 days a week - very strong office-culture signal
- Location: Stratford, East London - Jubilee line to Canary Wharf

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | No strong signal |
| Play to Win | Positive | Chose to leave Meta rather than take a safe internal transfer - wants ownership |
| Speed Wins | Positive | Wants 5 days in office, immediately available, no friction on process |
| Understand Why | Positive | Mature AI philosophy - doesn't blindly trust, reviews everything, test-from-spec approach |

## Candidate Knowledge notes

- [ ] **"AI-first testing: writing tests from spec before building forces better design"** - Kapil's approach of having AI generate tests from the spec, then building against them, inverts the usual flow and could improve both test quality and implementation discipline.

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-08, [[2026-07-08 - Kapil Pau - Senior Backend Engineer Screen]]] Screened Kapil Pau for Senior Backend Engineer. Good technical screening, transparent salary conversation (140-150k ask vs. 120k cap). Flagged lead/principal leveling option. Progressing to next stage.

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved in source artifact at /tmp/transcripts/metaview/2026-07-08 - Kapil Pau - Senior Backend Engineer (Metaview).md]
