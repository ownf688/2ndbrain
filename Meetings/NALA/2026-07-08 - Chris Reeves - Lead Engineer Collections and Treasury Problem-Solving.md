---
date: 2026-07-08
time: "10:30"
timezone: UTC
type: interview
interview_type: problem-solving
attendees:
  - "[[Christos Petropoulos]]"
  - "[[Edoardo Foco]]"
  - Christopher John Reeves
interviewer: "[[Christos Petropoulos]]"
interviewer2: "[[Edoardo Foco]]"
candidate: Christopher John Reeves
role: "Lead Engineer - Collections and Treasury"
duration: 60m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/460613533"
tags: [meeting, interview, metaview]
---

# 2026-07-08 - Chris Reeves - Lead Engineer C&T Problem-Solving

> [!summary] TL;DR
> Christos and Edoardo ran the architecture/problem-solving interview with Chris Reeves for Lead Engineer - Collections and Treasury. Chris was asked to design an FX rate aggregation system. He demonstrated strong system design fundamentals: microservices with clear separation, Kafka for async messaging, protocol buffer contracts, DLQ + idempotency for resilience, API ownership of database access (no shared DB anti-pattern). Key gaps: no prior FX domain experience (didn't know what a currency pair rate looks like), struggled with the float/decimal storage question, and initial design was over-engineered with one microservice per exchange provider before iterating to a more scalable consumer model. He recovered well when guided. Chris comes from 5 years at a bank (unnamed, likely Tide or similar) where he built the platform SDK and notification systems. Next step is leadership interview with Markus.

## Decisions

None (evaluation to be shared with Ryan for progression decision)

## Action items

- [ ] [[Christos Petropoulos]] - Share interview feedback with [[Ryan Bolton-Smith]]
- [ ] [[Edoardo Foco]] - Share interview feedback with [[Ryan Bolton-Smith]]

## Open questions

- Chris has no FX domain experience. How much of a barrier is this for the C&T lead role specifically?
- His initial over-engineering tendency (one microservice per provider) - is this a pattern or a one-off from nerves?

## Key discussion points

### Background and current role

Chris has been at "Bank" for 5 years. Joined as their second Golang hire. Built a platform SDK that standardized service startup/shutdown, monitoring, telemetry, and tracing across all Go microservices. As the company scaled, this became its own team which Chris has led since. Also owns Platform Late (delayed event bus), notification platform (webhooks, emails, SMS), and various infrastructure services.

> [!quote]- Source
> "I joined as their second Golang hire. When I joined, there was a Ruby on Rails monolith that the engineering team wanted to decompose into Golang microservices."

### Architecture task: FX rate aggregation

The task: design a system to consume FX rates from multiple providers and competitors, produce NALA's own competitive rates. Chris's approach:

1. Separate Go services polling each exchange API on a cron schedule
2. Standardize responses into a common protobuf contract
3. Publish to Kafka topic
4. Consumer inserts via an API service that owns the database
5. Separate cron + consumer to trigger rate calculation
6. Two tables: raw rates and cached current/average rate

He iterated on the design during the session, moving from one-microservice-per-provider to a single configurable consumer with an interface pattern - a good sign of adaptability.

> [!quote]- Source
> "It's generally considered a microservice kind of anti-pattern that you would have 2 different things be able to write or read to a database."

### Technical depth: data types and resilience

Chris correctly identified float64 precision issues for rate storage but couldn't recall that Postgres has a decimal type (Edoardo had to tell him). He knew to store currency in pence/cents from his banking background. On resilience, he covered: DLQs for failed messages, idempotency keys, metrics/alerting, graceful retry on Kafka downtime, and the at-most-once vs at-least-once delivery trade-off.

> [!quote]- Source
> "In banks, we, when we're storing currency data, we take it down to the lowest common denominator across the currency. So we're storing pence and cents."

### Competitor data scraping

When asked how to get competitor rates without API access, Chris immediately suggested web crawling. He correctly identified the brittleness problem and proposed good alerting/monitoring as the mitigation. Edoardo confirmed this is what NALA actually does.

> [!quote]- Source
> "I assume you probably have to crawl their website, I guess, which is a bit dirty. But it would probably get the job done."

### Candidate questions - culture and challenges

Chris asked about best things and biggest challenges at NALA. Christos highlighted people culture ("how much people help each other") and product ownership. Edoardo highlighted growth (from $15M to $150M+ monthly). Both named scaling speed as the main challenge - roadmap churn and resource allocation.

### Interviewer observations

Christos and Edoardo ran a well-structured interview. They let Chris lead the design, asked good probing questions (data structure completeness, validation gaps, float storage), and steered rather than dictated. Christos's "what can go wrong?" question was particularly effective.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | No strong signal |
| Play to Win | Positive | Built platform SDK and grew it into its own team at current company |
| Speed Wins | Neutral | Design was methodical rather than fast - appropriate for the task |
| Understand Why | Positive | Asked about engineering challenges and culture - wants to understand the environment |

## Candidate Knowledge notes

None

## Propagation

### [[Christos Petropoulos]]

- [2026-07-08, [[2026-07-08 - Chris Reeves - Lead Engineer Collections and Treasury Problem-Solving]]] Interviewed Chris Reeves for Lead Engineer C&T. Asked effective probing questions ("what can go wrong?"). Well-structured interview with Edoardo.

### [[Edoardo Foco]]

- [2026-07-08, [[2026-07-08 - Chris Reeves - Lead Engineer Collections and Treasury Problem-Solving]]] Interviewed Chris Reeves for Lead Engineer C&T. Led the architecture task clearly, good follow-up on data structure gaps (float64 vs decimal, missing fields). Positive sell on NALA culture at the end.

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved in source artifact at /tmp/transcripts/metaview/2026-07-08 - Chris Reeves - Lead Engineer Collections and Treasury (Metaview).md]
