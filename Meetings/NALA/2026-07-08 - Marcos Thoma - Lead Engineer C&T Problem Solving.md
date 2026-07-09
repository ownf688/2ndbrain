---
date: 2026-07-08
type: interview
interview_type: problem-solving
attendees:
  - "[[Wisdom Matthew]]"
  - "[[Arkadiusz Ziobrowski]]"
  - Marcos Thoma
project: "[[Hiring]]"
duration: 69m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/462724017"
tags: [meeting, interview, hiring]
---

# 2026-07-08 - Marcos Thoma - Lead Engineer C&T Problem Solving

> [!summary] TL;DR
> Problem-solving (pair programming) interview for Marcos Thoma, candidate for Lead Engineer - Collections and Treasury. Wisdom Matthew led, Arkadiusz Ziobrowski (Arek) shadowed. Marcos is Brazilian, based in Alicante, Spain. 34 years old, father of 3, with experience across large banks, forex companies, and small fintechs. He built a transaction limits system in Go with a totals-caching approach. Demonstrated solid architectural thinking (separate validator type, configurable limits, database atomicity) and handled concurrency questions well (optimistic locking, SELECT FOR UPDATE). Struggled slightly with Go syntax (hasn't been writing raw code recently, heavy AI usage) but thinking was sound. Feedback to be submitted by Wednesday, candidate expects to hear back by end of week.

## Decisions

None. This was an assessment interview.

## Action items

- [ ] [[Wisdom Matthew]] - Submit interview feedback on Marcos Thoma in Workable
- [ ] [[Arkadiusz Ziobrowski]] - Submit interview feedback on Marcos Thoma in Workable

## Open questions

- How does Marcos compare to the bar set in the Engineering Hiring Kick Off ICP? He demonstrated scalable systems thinking, ownership, and some product awareness. Golang proficiency is present but rusty on syntax.
- This is Marcos's second interview (first was a screen on 2026-07-06). What is the next stage if he passes?

## Key discussion points

### Transaction limits system design

Marcos built a transaction validation system with per-transaction, per-day, and per-month limits. His first instinct was to create a user totals map (caching approach) rather than scanning all transactions each time. When told not to optimize the in-memory storage, he pivoted but kept the conceptual model of a totals table. He proposed a separate totals table that could work identically in Postgres or Redis, not just in-memory.

> [!quote]- Source
> "I was imagining having some type of map of transactions where I could pair ID... I should save something different. I should have here that is the type. So should be user totals."

### Database consistency and atomicity

When asked about data consistency between the transactions table and totals table, Marcos articulated two approaches: (1) for simple cases, wrap both writes in a single Postgres transaction; (2) for complex distributed scenarios, use optimistic locking with a latest-transaction-ID reference, retry logic, and fallback to full recalculation if the optimistic lock fails.

> [!quote]- Source
> "If transaction is something small and well consistent like a Postgres table, we could have just 2 Postgres tables in the same transaction approach because it's not a lot of extra data."

### Concurrency handling

Wisdom asked about multiple instances hitting the same user's totals simultaneously. Marcos discussed ring-based load balancing as a first-pass mitigation, then correctly identified that the real solution is pessimistic locking (SELECT FOR UPDATE in Postgres) or optimistic locking with version checks. He showed awareness of the trade-offs between the two approaches.

> [!quote]- Source
> "When I create the transaction, this record is already-- could already give me that. If I have a database transaction here and I am reading the totals... and I lock this entity with a set it up Transaction in Postgres, I would not have this happening."

### Multi-currency extensibility

When asked how to handle multiple currencies, Marcos proposed a configuration table keyed by country (not currency, since different countries with the same currency may have different regulations). He suggested a compliance engine pattern from his previous work: load all configs upfront, run validation as a stateless black box. Good separation of concerns thinking.

> [!quote]- Source
> "per country is probably better because we can have different countries with same currency, I believe so"

### Testing philosophy

Marcos expressed preference for BDD over table-driven tests. In production, he'd use Godog with a Docker Postgres for integration testing. He struggled a bit with Go test syntax in the session (acknowledged heavy AI usage recently), but his testing philosophy was sound: full coverage, separate test per business case, t.Run isolation.

> [!quote]- Source
> "I love to test everything with business validations on the service layer. So normally I create, if I have Postgres example, I create a Docker Postgres, I start the application in parallel."

### Candidate background and questions

Marcos has experience with Kafka (built a message bus platform from zero), performance optimization, and AWS cost management. Shared a war story about proving AWS T-family CPU throttling to skeptical colleagues. Asked about company challenges. Wisdom and Arek shared that NALA recently had its record month for transaction volume, infrastructure is currently over-provisioned for safety, and they're working on making it more elastic for cost reasons.

> [!quote]- Source
> "I had experience creating a message bus platform for the company where I created Kafka from zero and had to go deeper on that."

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | No strong signal |
| Play to Win | Positive | Pushed through syntax struggles to deliver a working solution in the time constraint |
| Speed Wins | Positive | Immediately started thinking about architecture before coding, managed time well |
| Understand Why | Positive | "The TTL should be totally aware about the business rule" - thinks about business context behind technical decisions |

## Candidate Knowledge notes

*Atomic insights worth promoting to `/Knowledge/`. Flag here; promote during weekly review.*

- [ ] **"Transaction totals caching beats full-scan validation at scale"** -- Marcos's instinct to pre-compute running totals per user rather than scanning all transactions each time a limit check runs. Relevant to NALA's own transaction infrastructure.

## Propagation

*Proposed updates to other notes. Apply after review.*

### [[Wisdom Matthew]]

- [2026-07-08, [[2026-07-08 - Marcos Thoma - Lead Engineer C&T Problem Solving]]] Led problem-solving interview for Marcos Thoma. Good probing on concurrency, multi-currency extensibility, and database consistency. Guided candidate without giving answers.

### [[Arkadiusz Ziobrowski]]

- [2026-07-08, [[2026-07-08 - Marcos Thoma - Lead Engineer C&T Problem Solving]]] Shadowed problem-solving interview for Marcos Thoma. Made helpful interjections on storage interface extensibility and caught syntax errors.

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved at source: /tmp/transcripts/metaview/2026-07-08 - Marcos Thoma - Lead Engineer C&T Problem Solving (Metaview).md]
> Transcript is 69 minutes, approximately 53KB. See source file for full verbatim content.
