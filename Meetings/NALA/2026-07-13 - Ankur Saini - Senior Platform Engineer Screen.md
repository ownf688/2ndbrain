---
date: 2026-07-13
time: "15:15"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - "Ankur Saini"
interviewer: "[[Ryan Bolton-Smith]]"
candidate: Ankur Saini
candidate_email: ankur08071994@gmail.com
role: Senior Platform Engineer
duration: 30m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/462749529"
tags: [meeting, interview, metaview]
---

# 2026-07-13 - Ankur Saini - Senior Platform Engineer Screen

> [!summary] TL;DR
> Ryan screened Ankur Saini for Senior Platform Engineer. 7 years experience (4 at Quiff, a gambling company), AWS/EKS/Terraform/Terragrunt/ArgoCD stack. Has IDP (internal developer platform) build experience. Answers were technically adequate but consistently surface-level, recitation-heavy, and lacked the sharpness NALA needs at senior level. 3-month notice, skilled worker visa (sponsorship needed), asking GBP 80k+ (current ~67-68k). Lean no.

## Decisions

- **Decision:** Ryan to share profile with hiring manager for proceed/no-proceed
  - *Rationale:* Standard screen process, next step is hiring manager review
  - *Source:* "I'm going to have a chat with the hiring manager about your profile"

## Action items

- [ ] [[Ryan Bolton-Smith]] - Share Ankur Saini's profile with hiring manager, get proceed/no-proceed (due: 2026-07-14)
- [ ] [[Ryan Bolton-Smith]] - If progressed, send candidate prep doc for 90-min technical architecture + Terraform exercise (due: 2026-07-15)

## Open questions

- Can Ankur operate as a solo/near-solo platform engineer, or does he need the team structure he has at Quiff (6-person team, manager above him)?
- Depth of Kubernetes networking knowledge -- the IP exhaustion incident answer was well-structured but reads like a rehearsed case study. Would it hold up under deeper probing?
- No mention of Kafka, observability tooling beyond basic alerting, or security posture beyond "zero trust" as a buzzword. How would he handle NALA's fintech compliance requirements?

## Key discussion points

### Background and current role

Ankur has 7 years of experience across India and the UK. Currently at Quiff (online sports betting), where he's been ~4 years. Joined when the company was ~20 people, now 200+. Works in a 6-person platform team with a lead above him and 3 reports below. Holds a Master's in Data Science & Analytics from London.

His current work centres on an IDP called "Happier Place" -- self-service tools for developers including feature flag automation, ClickUp integrations, and agentic AI workflows for incident reporting/postmortems. Infrastructure is AWS EKS with ArgoCD (GitOps), Karpenter for autoscaling, Terraform + Terragrunt for IaC.

> [!quote]- Source
> "I build the golden paths that allow engineers to ship like software faster, more reliable, more secure."

### Motivation for NALA

Ankur says he's happy at Quiff but interested in fintech exposure. He personally relates to the cross-border payments problem as an Indian national sending money home. Has used Remitly, Wise, ICICI UK, and Aspora but hasn't tried NALA yet.

Motivation is plausible but generic -- "financial sector to move my career ahead" is not a strong conviction signal. No evidence he's researched NALA's specific technical challenges or regulatory environment.

> [!quote]- Source
> "NALA is solving, you know, real, real just tangible problems like, you know, cross-border payments."

### AWS cost optimisation (scenario question)

Ankur described migrating from HPAs (manual node scaling) to Karpenter for autoscaling, claiming a 30% cost reduction. The answer covered the right tool (Karpenter) but was thin on diagnostic process. He didn't describe how he identified the cost driver, what metrics he used, or what the before/after looked like in concrete terms. The answer was tool-name-driven, not problem-driven.

> [!quote]- Source
> "We onboarded an intelligent tool that is known as Karpenter. So that reduces our bill like to 30%, I can say, and it scales like automatically."

### Infrastructure as code (scenario question)

Described a Terraform + Terragrunt setup managing up to 40 environments. Modular approach, S3 remote state, DynamoDB locking. Migrated away from terraform.io (HCP) to reduce costs. Pain point was environment-specific overrides (SQS TTL needing to differ in prod vs dev) -- solved with custom modules.

When asked "what would you change if starting over," gave three shifts: unified GitOps from day one (ArgoCD), self-service templates for developers, and aggressive state file decoupling by lifecycle. The "start over" answer was the strongest of the interview -- showed architectural thinking, though still somewhat abstract.

> [!quote]- Source
> "Instead of larger nested directories, I would strictly isolate core networking, basically shared data stores... So basically this minimizes the blast radius of any change."

### Production incident (scenario question)

Described an IP address exhaustion incident during a high-traffic football match (Argentina vs Egypt, ~7 July). Pods stuck in pending state because VPC subnet CIDR was exhausted, preventing new worker nodes from joining the EKS cluster. Stabilised by pausing non-critical deployments, added new subnets (7-8 minute recovery), then expanded VPC CIDR strategy and added IP utilisation monitoring.

Well-structured answer (detect > diagnose > stabilise > permanent fix > prevent). But the narrative felt rehearsed. He didn't mention who else was involved, how the incident was escalated, what the customer impact was, or what the postmortem looked like beyond "we added monitoring."

> [!quote]- Source
> "The subnet IP address space was exhausted. So since each pods and nodes requires IP from the subnet CIDR."

### Logistics

| Item | Detail |
|------|--------|
| Notice period | 3 months |
| Right to work | Skilled worker visa (company-sponsored, needs new sponsorship) |
| Salary ask | GBP 80,000+ (current ~67-68k) |
| Office | Confirmed 4 days/week in Canary Wharf is fine |
| Location | Greater London |

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | Mentioned building self-service tools for developers (internal customers), but no strong signal of empathy-driven design or candidate/user-first thinking |
| Play to Win | Weak/Neutral | No evidence of driving outcomes beyond his assigned scope. Described work within a team hierarchy, always with a manager above. "I manage 3 more people" but no evidence of taking ownership of hard calls |
| Speed Wins | Neutral | 7-8 minute incident recovery is decent. But answers were slow to get to the point, heavily padded with filler. No evidence of bias to action or opinionated decision-making |
| Understand Why | Weak | Answers were tool-focused, not root-cause-focused. Cost question answered with "we used Karpenter" not "we analysed spend and found X was the driver." Incident answer had good structure but lacked the "why did we miss this in the first place" reflection |

## Candidate Knowledge notes

*No Knowledge notes flagged from this interview.*

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-13, [[2026-07-13 - Ankur Saini - Senior Platform Engineer Screen]]] Screened Ankur Saini for Platform Eng. Lean no -- 7yr experience but answers surface-level, recitation-heavy, tool-name-driven not problem-driven. Quiff (gambling), 4yrs, 6-person team. GBP 80k+, 3-month notice, visa sponsorship needed.

### Ankur Saini (new People note stub)

- **Name:** Ankur Saini
- **Role:** Senior Platform Engineer (candidate)
- **Company:** Quiff (online sports betting)
- **Workable ID:** 26aa1cc1 | Stage: Talent Interview
- **Source:** LinkedIn free posting, applied 2026-07-05
- **Key facts:** 7 years exp (UK + India), AWS/EKS/Terraform/Terragrunt/ArgoCD, MSc Data Science & Analytics (London), Indian national on skilled worker visa, Greater London
- **First interaction:** [2026-07-13, [[2026-07-13 - Ankur Saini - Senior Platform Engineer Screen]]] Talent screen with Ryan. Lean no.

## Raw transcript

> [!note]- Expand transcript
> [Full transcript preserved at /tmp/transcripts/metaview/2026-07-13 - Ankur Saini - Senior Platform Engineer (Metaview).md -- 190 lines, 29:42 duration]
