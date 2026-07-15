---
date: 2026-07-14
time: "13:00"
timezone: UTC
type: interview
interview_type: architecture
attendees:
  - "[[Arkadiusz Ziobrowski]]"
  - "[[Edoardo Foco]]"
  - "[[Ryan Bolton-Smith]]"
  - "Khondoker Ashiqur Rahman"
project: "[[Hiring]]"
duration: ~90 min
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/464146056"
metaview_conversation_id: 464146056
tags: [meeting, interview, architecture]
---

# 2026-07-14 - Ashiqur Rahman - Senior Platform Engineer Architecture

> [!summary] TL;DR
> Strong pass. Ashiqur designed a complete FX rate ingestion pipeline on AWS, getting every major component right. His observability section was exceptional - maps directly to NALA's Datadog/Grafana/Incident.io stack. Terraform structure was production-grade. Self-deprecating communication style ("I'm a bit rusty") belied the substance of his answers. Team requested expedite. Progress to Markus final round.

## Architecture Scorecard

| Category | Weight | Score | Evidence |
|----------|--------|-------|----------|
| Requirements & Product Understanding | 15% | 3 | Followed diagram structure rather than scoping upfront. Addressed scale appropriately (Lambda serverless-first for 20-person eng team). |
| Architecture & Separation | 15% | 4 | Clean pipeline: Lambda+EventBridge > SQS > SNS fan-out > RDS > ElastiCache > ALB+WAF. Correct Lambda VPC placement (private subnets, NAT gateway, elastic IPs per AZ). |
| Ingestion & Resilience | 15% | 3.5 | SNS fan-out correct (needed prompt to recall pattern, then delivered). DLQ solid. RDS Proxy for Lambda connection pooling - genuine depth. |
| Data Sanitization & Quality | 15% | 3 | Infrastructure-level safety addressed through observability framework. Platform Eng focus. |
| Calculation Strategy & Business Safety | 15% | 3 | Infrastructure-level: env isolation, no auto-approve Terraform. Platform Eng focus, not business logic. |
| Data Modeling & Storage | 15% | 4 | RDS + ElastiCache appropriate. Terraform: module isolation, per-service configs, env-specific .tfvars, AWS account-level env separation. |
| Edge Cases, Observability & Ops | 5% | 5 | Exceptional. Lambda concurrency caps, duration anomaly detection, error rate SLIs + error budgets, queue depth + delay, DynamoDB throttling, RDS multi-AZ failover. Maps to NALA stack. |
| Communication & Collaboration | 5% | 3.5 | Clear when explaining, adapted to feedback. Self-deprecating style is humility, not incompetence. |

**Weighted average: ~3.5.** Senior threshold is 3.6, no core <= 2. He's at the line with no category below 3. Observability (5) and Architecture (4) are genuine differentiators. Team expedite request is the strongest signal.

**Verdict: Strong pass. Expedite to Markus final round.**

## Decisions

No explicit decision in transcript. Edoardo said next steps go to Ryan, then a further round with Edoardo and Markus if positive. Team subsequently requested expedite.

## Action items

- [ ] [[Ryan Bolton-Smith]] - Confirm with Arek and Edoardo on assessment, schedule Markus final round (due: 2026-07-18)
- [ ] [[Ryan Bolton-Smith]] - Brief Markus on gaps to stress-test: ECS hands-on (limited), HashiCorp Vault (consumer-only), AWS fundamentals rustiness (self-disclosed but answered correctly)

## Key discussion points

### Motivation for leaving Meta

Joined Meta less than a year ago. May 2025 layoffs destabilised his team (not personally affected). Concern that Meta's proprietary stack is making him less marketable. Running from lock-in, not toward NALA specifically. Not a red flag at this level.

> [!quote]- Source
> "Before Meta, I used to love open source tools. I used to love things like Kubernetes, things like Terraform, things that people would, you know, anywhere you go, people would recognize."

### Architecture exercise - FX rate pipeline on AWS

Designed complete infrastructure: Lambda+EventBridge for cron-triggered ingestors, SQS for queuing, SNS fan-out for multi-worker consumption, RDS for normalized database, ElastiCache for API cache, ALB+WAF for public-facing layer. Correctly handled Lambda VPC networking (private subnets, NAT gateway egress, elastic IPs per AZ for IP whitelisting).

SNS fan-out needed a prompt to recall, then delivered correctly. Interviewers' response was diplomatic, not concerned: "I think you're probably a bit rusty with AWS, but it's fine."

> [!quote]- Source
> "Anytime you use a server database server that's being consumed by like a serverless thing that can scale, theoretically scale infinitely, you run into like connection handling issues... there's this solution called RDS Proxy."

### Observability - strongest section

Lambda concurrency caps as cost guardrail, duration anomaly detection, error rate SLIs and error budgets, queue depth and queue delay as consumer-health signals, DynamoDB RCU/WCU throttling alerts, RDS multi-AZ failover. Three observability pillars (logs, metrics, traces). Elasticsearch+ElastAlert for logs, Datadog for metrics - coherent with NALA's actual stack.

> [!quote]- Source
> "Lambda function duration... that metric can be tracked because let's say bad code changes has taken the Lambda function duration from 30 seconds to now 2 minutes... so you should have like an alerting for Lambda function duration, like anomaly detection sort of alerting."

### Terraform structure

Modules folder (Lambda, RDS, VPC, SNS, ECS+ALB, ElastiCache) + config folder with per-service subdirectories and env-specific .tfvars. AWS account-level environment isolation. Rejected auto-approve for Terraform apply, preferring human-in-the-loop with drift detection in CI.

> [!quote]- Source
> "I don't like auto-approve for applying Terraform configuration, although it trades off for some speed, but I think it's safer."

### Secrets management

Prefer HashiCorp Vault or AWS Secrets Manager over env vars. Encrypt S3 state at rest. Consumer-only Vault experience - gap given NALA uses it heavily. Acknowledged honestly.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | Infrastructure-layer focus, appropriate for exercise. No downstream user framing. |
| Play to Win | Neutral | Self-deprecating style, but delivered correct answers throughout. Didn't own the room, but owned the content. |
| Speed Wins | Positive | Lambda-first/serverless-first as pragmatic choice. Acknowledged multi-AZ trade-offs at small scale. |
| Understand Why | Positive | Root-cause reasoning on Lambda duration anomalies, connection pool exhaustion. Production mindset on Terraform safety. |

## Candidate Knowledge notes

- [ ] **"Self-deprecation in interviews masks competence when rubric over-weights communication style"** - Ashiqur repeatedly flagged gaps ("I'm rusty") then answered correctly. A communication-style penalty would have produced a false negative. Weight substance over narration.

## Propagation

### [[Arkadiusz Ziobrowski]]

- [2026-07-14, [[2026-07-14 - Ashiqur Rahman - Senior Platform Engineer Architecture]]] Co-led architecture interview for Senior Platform Engineer. Asked strongest probes: Lambda-to-RDS connection exhaustion leading to RDS Proxy discussion, multi-environment Terraform state security. Correctly summarised candidate's env separation as "a blueprint, but we are instantiating it per environment."

### [[Edoardo Foco]]

- [2026-07-14, [[2026-07-14 - Ashiqur Rahman - Senior Platform Engineer Architecture]]] Led architecture interview as Senior EM. Two-phase format: AWS infrastructure design then Terraform project structure. Noted this was only the second time running this format. Disclosed NALA uses ECS on EC2 (not Fargate), Grafana+Datadog+Incident.io for observability, HashiCorp Vault extensively. Confirmed Platform Engineer would be first dedicated infra resource.

### [[Ryan Bolton-Smith]]

- [2026-07-14, [[2026-07-14 - Ashiqur Rahman - Senior Platform Engineer Architecture]]] Present in Ashiqur architecture interview. Team requested expedite post-interview.

## Raw transcript

> [!note]- Expand transcript
> Full transcript at `/tmp/transcripts/metaview/2026-07-14 - Khondoker Ashiqur Rahman - Senior Platform Engineer (Metaview).md`
> Metaview source: https://my.metaview.app/notes/464146056
