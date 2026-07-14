---
date: 2026-07-13
time: "10:30"
timezone: UTC
type: interview
interview_type: problem-solving
attendees:
  - "[[Wisdom Matthew]]"
  - Kapil Pau
  - "[[Simeon Kostadinov]]"
interviewer: "[[Wisdom Matthew]]"
shadow: "[[Simeon Kostadinov]]"
candidate: Kapil Pau
candidate_email: kapilpau@hotmail.com
role: "Senior Backend Engineer"
duration: 59m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/464977432"
metaview_conversation_id: 464977432
tags: [meeting, interview, metaview]
---

# 2026-07-13 - Kapil Pau - Senior Backend Engineer Problem-Solving

> [!summary] TL;DR
> Wisdom Matthew (lead) and Simeon Kostadinov (shadow) ran a 59-minute Go-based problem-solving interview with Kapil Pau for Senior Backend Engineer. The exercise was a money transfer service with daily/monthly transaction limits. Kapil proposed a sensible data structure redesign (nested maps with pre-aggregated counters) and had a good design discussion about Redis caching, cache invalidation, and data redundancy tradeoffs. He got a working solution with limit enforcement validated in the terminal. However, he coded slowly without AI assistance (hit his Claude usage cap), needed several nudges from Wisdom on Go syntax, and the concurrency/locking discussion revealed surface-level distributed systems thinking - he proposed transaction-ID-based locks but conflated idempotency with concurrency control, and needed Wisdom to push him toward the actual problem (enforcing limit guarantees across distributed instances). Validation logic was placed in the storage layer rather than the service layer, and when challenged on it, he acknowledged it was wrong for production but didn't demonstrate instinctive architectural layering. Solid 3-star performance: meets the minimum bar but does not raise it.

## Decisions

- **Decision:** Pending - awaiting interviewer scorecards via Workable
  - *Rationale:* Need Wisdom and Simeon's formal feedback before making a stage-gate call
  - *Source:* "we'd go back, put in our feedback, and you should expect to hear back from... Ryan"

## Action items

- [ ] [[Wisdom Matthew]] - Submit Workable scorecard for Kapil Pau problem-solving round
- [ ] [[Simeon Kostadinov]] - Submit Workable scorecard for Kapil Pau problem-solving round
- [ ] [[Ryan Bolton-Smith]] - Communicate outcome to Kapil once scorecards are in

## Open questions

- Salary gap remains unresolved: Kapil needs 140-150k cash, NALA caps at ~120k base (flagged in screen). Did the engineering managers discuss leveling?
- Can Kapil operate at senior speed without AI assistance? He hit his Claude weekly limit and coded noticeably slower without it. At NALA, AI is a tool, not a crutch.
- Concurrency understanding: surface-level or deep? The locking discussion was prompted heavily by Wisdom. Need to weight this against the screen's stronger distributed systems answers (Kafka ordering, local vs distributed locks).

## Key discussion points

### Data structure design

Kapil proposed replacing flat transaction slices with a nested map structure: month-level aggregation (count + amount) containing day-level maps (count + amount + transaction list). Pre-aggregated counters mean limit checks run in constant time without scanning all transactions. Wisdom challenged on data redundancy (writing to two places) and cache invalidation (when to reset counters). Kapil handled the redundancy concern adequately, acknowledged the tradeoff, and when asked whether time or space mattered more, deferred to Wisdom, who confirmed NALA prefers storing more data for audit purposes.

> [!quote]- Source
> "having sort of a value that is written at transfer time. So we don't need to be sort of calculating the previous number of transactions and the transaction amounts every time."

### Redis caching and failure recovery

When Wisdom asked about Redis failure recovery, Kapil described a read-through cache pattern: on the next transaction attempt, if Redis is empty, query Postgres for that month's transactions, rebuild the cache, then proceed. He correctly identified that Redis might be unnecessary overhead if users send few transactions per day, showing cost-awareness. However, he didn't proactively discuss write-through vs write-behind patterns, cache warming strategies, or TTL design beyond a brief mention of expiry.

> [!quote]- Source
> "if it's very rare, like if users are on average sending 1 per day or sort of 2 or 3 a month, then having Redis might be an unnecessary expense and resource to manage"

### Concurrency and distributed locking

This was the weakest section. When Wisdom asked about race conditions, Kapil proposed using transaction IDs as Redis lock keys, generated when a user clicks "create transaction." The lock would have a TTL and release on completion or cancellation. Wisdom pushed on distributed scenarios: two instances, same user, two transactions hitting different machines simultaneously. Kapil's answer was that the transaction-ID lock prevents this because "only one transaction can come through in that window." This conflates idempotency (preventing duplicate sends of the same transaction) with concurrency control (preventing two different transactions from both passing limit checks simultaneously). He also suggested regional caches to reduce scope, which doesn't solve the core problem of a single user's limit enforcement across instances. Wisdom had to guide him toward the actual problem rather than Kapil identifying it independently.

> [!quote]- Source
> "the reason I was saying using the transaction ID is because then you prevent that race condition, right? Only one transaction can come through in that window."

### Implementation and coding speed

Kapil got a working solution with daily limit enforcement validated in the terminal (10 transactions blocked correctly, amount limits triggered). He coded in Go without AI assistance (weekly Claude limit exhausted), which was slower than expected for someone self-rating 5/5 on Go. He needed syntax help from Wisdom and Simeon on Go-specific patterns (time.Month type, map initialization). He explicitly called out testing and custom errors as things he'd add given more time, and correctly identified that validation constants belong in config, not hardcoded in the storage layer.

> [!quote]- Source
> "I am at my Claude limit, which is why I'm not using it."

### Architectural layering

Wisdom specifically probed why limit validation was in the storage layer rather than the service layer. Kapil acknowledged it was a scoping decision for the exercise and said in production these would be in helper functions and a config package. He understood the duplication problem (new storage implementations would need the same logic). This was a competent answer but reactive - he didn't instinctively separate concerns during implementation, and needed the prompt to articulate the right architecture.

> [!quote]- Source
> "it's only here because this is the only implementation that we have and it was the scope of this"

### Production readiness thinking

When asked what he'd change for production, Kapil listed: testing, custom error codes for UI handling, Redis caching, balance checking, and recipient validation. Reasonable but not exceptional. He didn't mention observability, rate limiting beyond the business rules, circuit breakers, or graceful degradation patterns that a senior engineer in payments would typically surface unprompted.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | Mentioned user-facing error messages and transaction funnels for UX monitoring, but these were prompted by Wisdom's questions rather than volunteered |
| Play to Win | Weak positive | Left Meta to seek ownership at a smaller company (from screen). In this interview, asked about engineering culture and autonomy. But didn't drive the conversation or push back on Wisdom's framing |
| Speed Wins | Weak negative | Coded slowly without AI. Chose not to use the offered time extension to set up AI access. Prioritisation was reasonable (skip tests, focus on core logic) but execution speed was below senior bar |
| Understand Why | Positive | Good cost-benefit reasoning on Redis ("might be unnecessary expense"), acknowledged tradeoffs in data redundancy, understood the "why" behind storing more data in finance. Weakened by the concurrency gap where he didn't understand why his locking approach was insufficient |

## Problem-solving scorecard

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Problem Breakdown** | 3 | Decomposed the exercise into data structure redesign, limit enforcement, and aggregation. Asked good clarifying questions upfront (single vs multi-user, data types, currency scope). But didn't independently identify the concurrency challenge as a first-order concern - it came up only when Wisdom prompted at the end. |
| **Independence** | 3 | Needed syntax help from interviewers on Go patterns. Concurrency discussion was heavily guided by Wisdom - Kapil didn't drive toward the hard problem. Placed validation in the wrong layer and only articulated the correct architecture when challenged. The screen showed stronger independence (idempotency, distributed locking answers were self-directed). |
| **Solution Quality** | 3 | Working solution with correct limit enforcement. Sensible data structure choice (nested maps with pre-aggregated counters). But: concurrency model conflated idempotency with locking, architectural layering was wrong by default, production readiness list was standard rather than payments-grade. No mention of observability, circuit breakers, or graceful degradation. |

**Overall: 3.0 / 5.0** - Meets minimum bar. Consider carefully.

## Candidate Knowledge notes

*No strong candidates for promotion to /Knowledge/ from this interview.*

## Propagation

### [[Wisdom Matthew]]

- [2026-07-13, [[2026-07-13 - Kapil Pau - Senior Backend Engineer Problem-Solving]]] Led problem-solving interview for Kapil Pau (Senior Backend Engineer). Strong interview technique again: probed concurrency assumptions, challenged architectural layering, guided without giving answers. Pushed Kapil to think beyond his transaction-ID lock toward the real distributed consistency problem.

### [[Simeon Kostadinov]]

- [2026-07-13, [[2026-07-13 - Kapil Pau - Senior Backend Engineer Problem-Solving]]] Shadowed Wisdom on Kapil Pau problem-solving round. Minimal intervention (helped with Go syntax, gave a strong culture pitch at the end about NALA's eng culture, developer-led initiatives, and pair programming). First interview interaction logged.

### [[Ryan Bolton-Smith]]

- [2026-07-13, [[2026-07-13 - Kapil Pau - Senior Backend Engineer Problem-Solving]]] Kapil Pau completed problem-solving round. Awaiting Wisdom and Simeon's scorecards. Wisdom told Kapil that Ryan would be in touch with next steps.

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved in source artifact at /tmp/transcripts/metaview/2026-07-13 - Kapil Pau - Senior Backend Engineer (Metaview).md]
