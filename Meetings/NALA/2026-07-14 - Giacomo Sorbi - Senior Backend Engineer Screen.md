---
date: 2026-07-14
time: "09:00"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - "Giacomo Sorbi"
project: "[[Hiring]]"
duration: ~21 min
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/463525852"
metaview_conversation_id: 463525852
tags: [meeting, interview, talent-screen]
---

# 2026-07-14 - Giacomo Sorbi - Senior Backend Engineer Screen

> [!summary] TL;DR
> Giacomo is a London-based contractor (6+ years via Toptal, limited company), motivated by market softness in premium consultancy rather than active pull toward NALA. Competent generalist with broad stack exposure but limited Go depth and no fintech domain background. Technical answers functional but surface-level. Lean no - the Go gap and passive motivation are real flags for a senior fintech backend role.

## Decisions

None. Ryan committed to reverting by "tomorrow afternoon" after engineering manager review.

## Action items

- [ ] [[Ryan Bolton-Smith]] - Debrief with engineering managers (Markus) on Giacomo's profile (due: 2026-07-15)
- [ ] Engineering Manager (Markus) - Proceed to live Go coding exercise or reject (due: 2026-07-15)

## Open questions

- Can the Go gap be tested definitively in a live coding exercise, or is self-described light usage disqualifying at Senior?

## Key discussion points

### Background and work arrangement

Giacomo has 6+ years as a contractor via Toptal, operating through his own limited company. Trigger for looking is market-driven: Toptal's premium rates generating less inbound. Passive-market candidate, available immediately.

Most recent project (confidential, US-based): training and certification software, Python/C# backend on AWS, React frontend. Notable challenge was timezone normalisation across US regions for certification expiry rules.

> [!quote]- Source
> "I was the first or second technical hire in a number of projects, so I needed to take ownership of features or even products from scratch."

### Go proficiency - the critical gap

Acknowledged limited recent Go usage. Described Go as "very Python-like" - imprecise for NALA's primary backend language. Hedged on live coding comfort.

> [!quote]- Source
> "I didn't use it much, very recently, but I would say so. It's very Python-like, and Python was my first language."

### Technical questions - adequate, not sharp

**Unique user report:** Pragmatic approach - query transaction log with time-window filter. No caching layers, materialized views, or background aggregation mentioned. Minimum viable response compared to other SBE candidates (e.g. Andrei Petrovich proposed background workers).

**Double-spend / idempotency:** Led with UX (disable button, show loader) - solid instinct. Backend idempotency via unique identity keys and status queue. Did not name idempotency keys explicitly. Pattern was there but not as precise as a fintech native.

**Distributed locking:** Correctly distinguished local locks from distributed locks when prompted. But this was prompted - he needed the scenario handed to him.

**AI usage:** Thoughtful framing. Uses AI for tests, docs, feature code. Cautious about AI for architecture. Forward-looking on AI agent orchestration and token management.

> [!quote]- Source
> "When you need to move a bit more high level, that can be tricky."

### Logistics

- Location: London, UK. Settled status. Immediate availability.
- Salary: GBP 100-120k. Fully remote required. Limited company / B2B.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | UX instinct on double-spend is implicit customer thinking but not framed that way |
| Play to Win | Weak | "As long as it's legal, I do it" on industry preference. Contractor mindset, not mission-driven |
| Speed Wins | Neutral | Answers prompt and structured. No shipping-under-pressure examples |
| Understand Why | Neutral | Asked clarifying question on report type. Technical answers stayed at the what, not the why |

## Candidate Knowledge notes

- [ ] **"AI orchestration as engineering's next role"** - Giacomo's framing that engineers will become "masters of AI activity, including token consumption and MCP environments" is a coherent view of the AI-native engineering stack

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-14, [[2026-07-14 - Giacomo Sorbi - Senior Backend Engineer Screen]]] Screened Giacomo Sorbi for SBE. Lean no - Go gap (self-described light usage), passive motivation (market softness not pull), adequate but surface-level technical answers. GBP 100-120k, London, settled status, immediate start. Deferred to Markus for proceed/reject.

## Raw transcript

> [!note]- Expand transcript
> Full transcript at `/tmp/transcripts/metaview/2026-07-14 - Giacomo Sorbi - Senior Backend Engineer (Metaview).md`
> Metaview source: https://my.metaview.app/notes/463525852
