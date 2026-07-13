---
date: 2026-07-10
time: "13:30"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - Sachin Malanki
interviewer: "[[Ryan Bolton-Smith]]"
interviewer_email: ryan.bookings@nala.money
candidate: Sachin Malanki
candidate_email: sachin.chini@gmail.com
role: Senior Platform Engineer
project: "[[Hiring]]"
source: metaview
source_url: "https://my.metaview.app/notes/462947962"
tags: [meeting, interview, talent-screen]
---

# 2026-07-10 - Sachin Malanki - Senior Platform Engineer (Talent Screen)

> [!summary] TL;DR
> Sachin is a Senior Platform Engineer at New Day (fintech, credit cards) with 3-4 years in the role, working across AWS, EKS, Terraform, observability, and developer platforms. He is looking to move because a private equity acquisition has created strategic uncertainty and manager churn. He has direct experience as a solo platform engineer at a prior company and expressed comfort with NALA's bus-factor setup. Needs skilled worker visa sponsorship. Salary expectation lands around GBP 105-110k (current GBP 85-90k + 15% bonus, seeking 20-25% uplift). One month notice.

## Screen Assessment

### Fit & Motivation

Sachin's motivation to leave is structural, not flight-risk whimsical. New Day was acquired by a private equity firm and the resulting lack of roadmap clarity and revolving managers have pushed him to market. He articulated this cleanly:

> [!quote]- Source
> "We've recently been bought over by another private equity firm, and since then I think it's been a bit of shaky decisions that's been made from the senior management level. So I'm not kind of understanding what our roadmaps are for the next 6 months to 1 year to even 3 years."

He also flagged growth stalling due to manager churn:

> [!quote]- Source
> "My manager has been quite frequently changing, and that's something that's not helping me grow in the long run as well."

He showed genuine interest in NALA's business model, asking intelligent questions about differentiation from Wise/Remitly/Western Union, and whether NALA is profitable. These are commercial-awareness signals, not box-ticking.

### Green Flags

1. **Solo platform experience.** He was the sole platform engineer at his pre-New Day role and explicitly said he enjoyed it and can relate to NALA's setup:

   > [!quote]- Source
   > "There's something that was similar to my other role when I first started off. I think that I was the only platform engineer as well. So I think I can understand how that role is."

2. **Developer platform ownership (Backstage).** He built an internal developer platform using Backstage as a self-initiated POC, drove adoption, and measured success by engineer feedback. This is directly relevant to NALA's developer experience gap:

   > [!quote]- Source
   > "When you kind of hear from them saying that, oh, this saved me so much time, I don't have to like switch 5, 10 tabs... Having everything in like a single pane of glass."

3. **Fintech compliance awareness.** Current role involves PCI-DSS, PII data tiering, and regulatory constraints. Understands that platform engineering in financial services is not the same as in a startup without compliance obligations.

4. **Cost optimisation instinct.** Proactively identified and fixed S3 lifecycle policy gaps, orphaned EBS volumes, and weekend EKS cluster over-provisioning without being asked. The examples were concrete, not theoretical.

5. **Incident response maturity.** Led a production incident end-to-end (load balancer misconfiguration after a deployment). Showed correct prioritisation: restore service first, root-cause second:

   > [!quote]- Source
   > "Getting the service back up is more important than me trying to fix or like understand what the root cause is."

6. **Strong documentation culture.** Described a multi-layered knowledge management approach: ADR process for architectural decisions, Jira for in-progress work, Markdown-to-Confluence pipeline, standups, and biweekly show-and-tells.

### Red Flags

1. **No Kafka hands-on.** Has used Confluent (hosted Kafka) and NATS JetStream but explicitly stated he does not work with Kafka day-to-day. NALA's stack is Kafka-heavy. This is a gap, not a blocker, but needs probing in the technical round.

   > [!quote]- Source
   > "I do not really work on Kafka on a day-to-day basis... I've not really worked with Kafka, I would say."

2. **Visa sponsorship required.** Sachin needs a skilled worker visa. He mentioned 1-2 years remaining on his current visa. Ryan confirmed NALA sponsors, so this is process overhead, not a blocker.

3. **Salary expectation at top of range.** Current comp is GBP 85-90k base + 15% bonus. Seeking 20-25% uplift, which puts him at GBP 105-112k base. Need to validate against the approved band for Senior Platform Engineer.

4. **Terragrunt frustration may signal opinionated-but-untested preferences.** He was vocal about Terragrunt being painful and preferring modular Terraform with workspaces, which is a reasonable opinion. But no evidence he has built a greenfield IaC setup from scratch at scale, only that he would do it differently. The NALA role is greenfield, so this needs testing in the technical round.

### Logistics

| Item | Detail |
|------|--------|
| Notice period | 1 month |
| Right to work | Skilled worker visa required (1-2 years remaining on current visa) |
| Current comp | GBP 85-90k base + 15% bonus |
| Salary expectation | GBP 105-112k (20-25% uplift on base) |
| Current employer | New Day (credit/fintech) |
| Team size (current) | 5 engineers (2 mid, 3 senior) + 2 leads + architects |
| Location | UK-based |

## Values Alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Positive | Built Backstage IDP specifically to improve developer experience. Measured success by user feedback: "when you kind of hear from them saying that, oh, this saved me so much time" |
| Play to Win | Positive | Proactively identified cost savings without being asked. Took on Backstage POC autonomously: "he just told me, you can basically go and try this out... and I just went ahead" |
| Speed Wins | Positive | Prioritised service restoration over root-cause analysis during incident. Implemented "quick fixes" for cost optimisation rather than waiting for a comprehensive project |
| Understand Why | Neutral | Described compliance requirements and architectural reasoning adequately. No strong signal of deep root-cause curiosity beyond the incident management example |

## Key Discussion Points

### Current Role & Stack

Sachin is a Senior Platform Engineer at New Day, a UK fintech providing consumer credit (including white-label for Amazon, Argos). His platform work spans AWS (EKS, EC2, Lambda, S3), Terraform, Terragrunt, Crossplane, and Grafana Cloud for observability. Team of 5 engineers plus 2 leads and multiple architects.

> [!quote]- Source
> "What I do there is build infrastructure for them so that they can kind of have their applications running, scaling, and ensure that there's just more reliability."

### Motivation to Move

Private equity acquisition created strategic ambiguity and manager instability. No roadmap visibility. Not a compensation-driven move.

> [!quote]- Source
> "The main reason is we've recently been bought over by another private equity firm, and since then I think it's been a bit of shaky decisions."

### AWS Cost Optimisation

Proactively identified three cost-saving opportunities: S3 lifecycle policies for tiered storage (compliance-aware, 90-day and 365-day thresholds), orphaned EBS volume cleanup after EKS cluster scaling, and weekend node reduction (15 nodes to 3).

> [!quote]- Source
> "When you see the AWS bill at the end of the month... we are spending on S3 a lot of money because a lot of files come in through S3 for us. But what's happening there is we have not really set up a lifecycle policy."

### Terraform & IaC Opinions

Strong opinions on IaC structure. Critical of Terragrunt as a wrapper that creates deployment coupling and drift-fix bottlenecks. Advocates for modular repos, per-component state files, workspace-based environment management, and variable-driven configuration over code duplication.

> [!quote]- Source
> "I would rather have it more modular and have Terraform not as a monorepo. I would rather have it as a repo for, let's say, a specific at least a specific environment and have that specific state file for that specific component."

### Production Incident Leadership

Led resolution of a load balancer misconfiguration that took down a service. Detected via ops monitoring (not automated alerting, which is a minor concern). Diagnosed the issue as a stale DNS pointer after a deployment changed load balancer values and the old one was deleted. Fixed by creating a private hosted zone with correct values. Key learning was prioritising restoration over root-cause.

> [!quote]- Source
> "I had to basically understand what's happening and try to get the service back up. That was the first thing that kind of ran into my mind."

### Backstage Internal Developer Platform

Self-driven POC that became a production internal developer platform. Plugin-based architecture providing a single pane of glass for engineers across application visibility, tooling, and observability. Required extensive collaboration with end users to understand pain points.

> [!quote]- Source
> "I kind of love the whole idea of you could basically add whatever plugins that you want to ensure that your end users or your engineers don't really have to leave this one platform."

### NALA Role Understanding

Ryan explained the role is a bus-factor fix. The previous platform person (6-year backend engineer who naturally took on platform duties) left a couple of months ago. Sachin would be solo but partnered with Eduardo (Engineering Manager) on platform decisions. Sachin was unfazed and drew on his prior solo platform experience.

> [!quote]- Source
> Ryan: "This role really would be like a bus factor fix role in the sense that you're kind of coming in and taking over and therefore actually leading platform architecture as well."

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-10, [[2026-07-10 - Sachin Malanki - Senior Platform Engineer (Talent Screen)]]] Conducted talent screen for Sachin Malanki (Senior Platform Engineer). Covered technical depth adequately across AWS, Terraform, observability, and incidents. Confirmed visa sponsorship is fine. Sold NALA well (B2B rails, stablecoin corridor, 120x revenue growth, Revolut comparison). Call ran slightly short - Ryan had to cut off Sachin's questions due to back-to-back scheduling: "I'm really sorry, Sachin. I do have to jump because I'm late."