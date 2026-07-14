---
aliases: [Kapil Pau, Kapil]
type: candidate
role: Senior Backend Engineer
company_applied: NALA
status: active-pipeline
tags: [person, candidate]
---

# Kapil Pau

Candidate for Senior Backend Engineer at NALA. First encountered in [[2026-07-08 - Kapil Pau - Senior Backend Engineer Screen]].

## Context

~8 years SWE experience across IBM, AWS, and Meta. Laid off from Meta January 2026 (Quest for Business / Meta Horizon - VR developer platform). At AWS, cherry-picked to lead a new engineering function in London, grew team from 0 to 6-18 engineers (OAT lending model). Go is primary language (self-rated 5/5). UK citizen, based in Stratford, East London. Wants 5 days in office. Immediately available.

## Salary

- Meta total comp: 220-250k GBP (base ~120k, rest stock)
- Minimum cash need: 140-150k (mortgage)
- NALA base cap: ~120k. Lead/principal leveling discussed as possible bridge.

## Pipeline

- [2026-07-08] Talent screen with Ryan Bolton-Smith. Progressed. Strong technical answers, mature AI philosophy. Salary gap flagged.
- [2026-07-13] Problem-solving round with Wisdom Matthew (lead) + Simeon Kostadinov (shadow). Working solution with limit enforcement. Concurrency discussion was the weak point - conflated idempotency with distributed locking. Overall 3/5: meets minimum bar, consider carefully.

## Interview signals

### Screen (2026-07-08)
- Idempotency: Strong (transaction IDs, duplicate rejection)
- Distributed vs local locking: Clean explanation
- Kafka ordering: Solid
- AI usage: Mature ("treats Claude as a junior engineer")

### Problem-solving (2026-07-13)
- Data structure design: Good (nested maps, pre-aggregated counters)
- Redis caching/recovery: Adequate (read-through cache, cost-benefit awareness)
- Concurrency: Weak (conflated idempotency with concurrency control, needed heavy guidance)
- Go coding speed: Below expectation without AI
- Architectural instincts: Reactive, not proactive (validation in wrong layer)

## Open concerns

- Salary gap: 140-150k ask vs 120k cap. Unresolved.
- All big-tech background (IBM, AWS, Meta). Can he thrive with 18 engineers and less structure?
- Coding speed without AI assistance was noticeably slow for a self-rated 5/5 Go developer.
- Concurrency answers degraded from screen (strong conceptual) to live exercise (weak applied). Pattern or nerves?
