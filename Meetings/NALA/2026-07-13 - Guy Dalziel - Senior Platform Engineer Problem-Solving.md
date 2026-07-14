---
date: 2026-07-13
time: "10:00"
timezone: UTC
type: interview
interview_type: problem-solving
attendees:
  - "[[Christos Petropoulos]]"
  - "[[Edoardo Foco]]"
candidate: "Guy Dalziel"
candidate_email: work@id.guydalziel.dev
role: "Senior Platform Engineer"
duration: ~96m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/460613555"
metaview_conversation_id: 460613555
tags: [interview, metaview, platform, hiring]
---

# 2026-07-13 - Guy Dalziel - Senior Platform Engineer Problem-Solving

> [!summary] TL;DR
> Guy Dalziel completed a 90-minute problem-solving interview for Senior Platform Engineer. He designed infrastructure for NALA's FX rate ingestion pipeline (Lambda + SNS/SQS fan-out + S3 for raw storage + ECS for web serving) and demonstrated a Terraform project structure with modules and multi-environment support. Solid AWS breadth, pragmatic instincts on cost, but solution quality stayed at "competent practitioner" level - never exceeded the brief, missed TLS until prompted, conflated WAF with encryption, and the Terraform section showed familiarity without depth on abstractions or environment management patterns. Signal: borderline 3-star. Proceed with caution.

## Decisions

- **No decisions made.** This is a candidate evaluation, not a decision meeting.

## Key discussion points

### Architecture design: FX rate ingestion pipeline

Guy was given an intentionally vague brief: design infrastructure for NALA's FX rate pipeline (ingest from 20 provider APIs, 20 currency pairs each, once per hour, normalize, sanitize, compute NALA rates, serve via API).

He correctly identified Lambda + EventBridge as the right compute model for hourly batch ingestion of small payloads (~20MB/hour). Good instinct to calculate data volumes first (20 APIs x 20 pairs x 5KB = ~2MB actual, though he rounded to 20MB). Proposed S3 config files for API endpoint management over multiple EventBridge rules - pragmatic and extensible.

> [!quote]- Source
> "I don't think you'd want something sitting there permanently if it's spending the majority of its time not doing anything. So I think serverless is probably your best bet there."

### Message fan-out architecture

Initially proposed SQS for the event queue, then self-corrected to SNS + SQS fan-out when he realized the architecture required publishing to multiple consumer queues. The self-correction was good - he caught his own mistake before the interviewers needed to intervene. However, it took a couple of back-and-forth exchanges to land on the clean SNS-topic-to-multiple-SQS pattern, which is a standard AWS pattern a senior engineer should reach faster.

> [!quote]- Source
> "I think we would likely need to use SNS and have the queues subscribed to it in order for both of those queues to receive the events."

### Document storage decision

When asked about DynamoDB vs MongoDB for storing raw rates, Guy admitted limited MongoDB knowledge but asked a clarifying question about access patterns first. When told it was debug-only, he pivoted away from both to S3 + Athena - a cost-conscious choice that showed practical judgment. This was his strongest moment: rejecting the presented options in favour of something simpler.

> [!quote]- Source
> "DynamoDB might be overkill for document storage. Potentially we could use something like S3... maybe as Parquet files, and then use something like Athena to run queries over them."

### Observability and failure handling

Listed standard CloudWatch monitoring (Lambda invocations, success rates, RDS metrics, EventBridge scheduling). When asked about Lambda failure handling, gave a textbook answer on SQS retry with dead letter queues. Correct but not insightful. No mention of structured logging, distributed tracing, alerting strategy, or runbook culture.

> [!quote]- Source
> "You would want to have dead letter queues for your SQS queues in order to say, okay, if a specific message fails X number of times, then move it into the dead letter queue."

### Web serving layer

Proposed ECS/Fargate containers behind an ALB in a private subnet. Good VPC anatomy: ALB in public subnets, containers in private, cache in a lower tier. Mentioned Memcached over Redis with a reasonable (if slightly imprecise) justification about distributed caching complexity. Considered API Gateway + Lambda briefly for the web layer but correctly dismissed it given 100+ endpoints.

When asked about traffic security, went to WAF instead of TLS. Edoardo had to prompt for TLS/ACM, which Guy then answered correctly. This is a gap: TLS should be the first thing out of a senior platform engineer's mouth when asked about protecting traffic. WAF is complementary, not primary.

> [!quote]- Source
> "You can use a WAF attached to the load balancer in order to filter the traffic." (Edoardo: "I was thinking of a TLS certificate, but WAF is complementary, so I really like the answer there.")

### Security groups

When Edoardo asked about the component needed for Lambdas to talk to RDS inside a VPC, Guy initially guessed DNS resolution, then needed a hint ("It's a very generic component") before landing on security groups. A senior platform engineer should know immediately that security groups are the access control layer within a VPC. He then described the SG-to-SG reference pattern correctly.

### Terraform scaffolding

Showed a standard project structure: provider, backend (S3 state), variables, locals, main.tf. Demonstrated module usage with versioned registry references. When asked about environment management, proposed AWS provider profiles with IAM Identity Center - functional but not what Edoardo was looking for (conditional resource deployment). Didn't reach for workspaces, Terragrunt, or directory-per-environment patterns unprompted. When Edoardo pushed on conditional resources per environment, Guy defaulted to multiple provider aliases, which is a partial answer (handles multi-account, not conditional resource inclusion).

> [!quote]- Source
> "Part of managing change is about making things predictable. So I think for me, that's an important point."

### Candidate questions to NALA

Asked about quality vs speed culture, 5-year evolution, infrastructure challenges, and operational maturity. These are sensible but generic questions. No questions about on-call, incident management, security posture, or cost management - areas where a senior platform engineer should be probing.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | No strong signal. Did not ask about internal customers (developers) or their pain points. |
| Play to Win | Neutral | Showed willingness but no evidence of driving outcomes beyond the brief. Stayed reactive to prompts. |
| Speed Wins | Weak positive | Cost-conscious, pragmatic choices (S3 over DynamoDB, Lambda over EC2). But took long paths to standard answers. |
| Understand Why | Positive | Good clarifying questions on requirements before proposing solutions. "First let's establish some requirements. So what is the document storage for?" |

## Problem-solving scorecard

### Problem Breakdown: 3/5 (OK / minimum bar)

Guy asked good clarifying questions at the start (frequency, data volume, number of APIs) and sized the problem correctly. He broke the pipeline into stages and worked through them sequentially. However, he didn't proactively identify cross-cutting concerns (security, observability, cost) - these only came up when Edoardo asked. A 4-star candidate would have framed the problem holistically before diving into component-level design.

### Independence: 3/5 (OK / minimum bar)

Mixed. He self-corrected on the SNS/SQS fan-out, which shows independent reasoning. But he needed prompting on TLS, took a hint to get to security groups, and didn't reach Edoardo's intended answer on environment management in Terraform. The interview required moderate interviewer guidance to keep moving forward. A senior hire should be driving the conversation, not being led through it.

### Solution Quality: 3/5 (OK / minimum bar)

Solutions were correct and pragmatic but never exceeded expectations. Every answer landed at "competent practitioner" level: right enough, but not demonstrating the depth or opinionated perspective you'd want from someone building NALA's first dedicated platform function. The S3 + Athena pivot for raw rate storage was the one moment that showed genuine judgment. The Terraform section showed familiarity but not mastery - no mention of workspaces, Terragrunt, or directory-per-environment patterns, and the environment management answer (provider profiles) missed the mark.

**Overall: 3.0/5 - minimum bar. Consider carefully.**

## Candidate Knowledge notes

*Atomic insights worth promoting to `/Knowledge/`. Flag here; promote during weekly review.*

- [ ] **"S3 + Athena beats DynamoDB for debug-only data access patterns"** - Guy's pivot away from DynamoDB for infrequently-accessed raw rate storage. Standard pattern but worth logging as a reference point for future platform interviews.

## Propagation

*Proposed updates to other notes. Apply after review.*

### [[Christos Petropoulos]]

- [2026-07-13, [[2026-07-13 - Guy Dalziel - Senior Platform Engineer Problem-Solving]]] Interviewed Guy Dalziel for Senior Platform Engineer. Mostly observing, let Edoardo lead. Gave strong sell on NALA culture and ownership in candidate Q&A section.

### [[Edoardo Foco]]

- [2026-07-13, [[2026-07-13 - Guy Dalziel - Senior Platform Engineer Problem-Solving]]] Led Guy Dalziel's problem-solving interview for Senior Platform Engineer. Good task framing and probing (TLS prompt, environment management, security groups). First candidate interviewed for this role.

### Guy Dalziel (new People note required)

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved at `/tmp/transcripts/metaview/2026-07-13 - Guy Dalziel - Senior Platform Engineer (Metaview).md`]
