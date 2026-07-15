---
date: 2026-07-14
time: "10:30"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - "Ram Kilari"
interviewer: "[[Ryan Bolton-Smith]]"
candidate: Ram Kilari
candidate_email: krishnakilari66@primemailhost.com
role: Senior Platform Engineer
duration: 26m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/464407727"
tags: [meeting, interview, talent-screen]
---

# 2026-07-14 - Ram Kilari - Senior Platform Engineer Screen

> [!summary] TL;DR
> Ryan screened Ram Kilari for Senior Platform Engineer. 10 years IT experience, 6-7 as SRE/DevOps, currently contracting at ICIS (RELX). Built a custom patch management platform (Patch Shield) from scratch -- solid builder instinct. However, technical depth is shallow: AWS cost/scaling answer was diagnostic checklist rather than a solved problem, IaC answer was textbook, and no experience with Kubernetes, Kafka, or Azure at a commercial level. Asking GBP 75k, 2-week notice, UK dependent visa to ILR 2028. No progression signal -- Ryan did not indicate next steps beyond "speak with the hiring manager". Lean no.

## Decisions

- **Decision:** No explicit proceed/no-proceed made on the call
  - *Rationale:* Ryan closed by saying he'd speak with the hiring manager and aim to get back by "tomorrow afternoon"
  - *Source:* "I'm gonna speak with the hiring manager with the answers that you've given me today"

## Action items

- [ ] [[Ryan Bolton-Smith]] - Deliver proceed/no-proceed to Ram by 2026-07-15 afternoon
- [ ] [[Ryan Bolton-Smith]] - If no-proceeding, log rationale in Workable and close the loop with candidate promptly

## Open questions

- Is Ram's patch management build (Patch Shield) genuinely transferable to a fintech platform context, or is it ops-maintenance work that won't carry at NALA's level?
- Right-to-work dependency: dependent visa until April 2028, then ILR. No sponsorship needed, but what happens if spouse's visa status changes before ILR conversion?
- No evidence of Kubernetes, containerisation, or microservices experience beyond a passing mention. Can he operate at the infrastructure abstraction level NALA needs?

## Key discussion points

### Background and current role

Ram has 10 years of IT experience, starting in Linux/system admin and moving through DevOps and cloud into SRE. Currently contracting at ICIS (a RELX subsidiary covering oil data), a 16-person SRE function where he works in a 3-person group focused on patching and system upgrades. His contract formally ended last month but is on a rolling period while he delivers knowledge transfer on a tool he built.

He wants to go permanent for two reasons: contractor life in the UK means no holiday, and he feels unable to see builds through when structural changes happen and he rotates out mid-project. Both are honest, self-aware motivations rather than chasing money.

> [!quote]- Source
> "When I'm trying to contribute and when I'm starting building something and there is some kind of reorganization, structural changes, I'm just moving the flip. So now I decided to work as a permanent employee."

### Headline build: Patch Shield

The strongest signal in the entire screen. Ram inherited an environment with no patch strategy -- servers were respun manually on vulnerability detection. He built from scratch: Ansible playbooks for repeatable patching, a Python script to pull live AWS inventory and segment by availability zone, Jenkins schedulers to automate sequencing, and a dashboard showing snapshot timestamps, uptime before/after reboot, service state before/after, and per-zone sequencing. He then migrated off Jenkins to npm/Node with cron schedulers when the client team flagged Jenkins complexity.

This is a genuine build -- problem-identified, iterated from manual to automated to self-service. The instinct is right. The technology choices (Ansible, Python, shell scripts, npm/Node as a runner) are pragmatic but low-sophistication for a Senior Platform Engineer at a fintech.

> [!quote]- Source
> "Previously they're not thinking about the patching, they just respin the servers when they want to, when they see any kind of vulnerabilities. So when I'm coming to this company, they don't have any kind of a patch platform. So I started building from the scratch."

### AWS cost and scaling (scenario question)

Ryan asked Ram to walk through a time he fixed a system burning money or buckling under load. Ram did not cite a specific incident. Instead he described a diagnostic checklist he would apply: check auto-scaling, check logs for spike patterns, assess whether spikes are real traffic or internal service noise, check server specs against actual usage, and consider right-sizing. The answer was entirely hypothetical and process-oriented. No numbers, no before/after, no named outcome.

This is a meaningful gap. At senior level, the ask is a war story. Ram delivered a playbook.

> [!quote]- Source
> "I'll check for whether it is in 24/7 production support, there is a kind of huge spikes on the ones. On particular times... I'll put some monitoring on the ones to continuously monitor that one."

### Infrastructure as code (scenario question)

Ram described using Terraform modules for test environment provisioning: separate modules for VPCs, servers, load balancers; variable-driven; reusable across environments. Correct fundamentals. When asked what's painful about it, he gave a strong and real answer: console drift causing state file corruption, specifically RDS version upgrades made manually that later cause plan conflicts. He clearly has lived this problem.

When asked "how would you do it from scratch?" he shifted to advocating for Kubernetes over EC2 (which he said 90% of EC2 workloads could move to), keeping DNS dependencies internal to AWS to reduce blast radius during incident recovery, and using Ansible for configuration on top of Terraform for provisioning. The architectural intuition is reasonable but the answer is general rather than grounded in a specific project.

Notably: no commercial Azure or GCP experience, no mention of Terragrunt, no GitOps tooling (ArgoCD, Flux), no remote state management strategy, no mention of how he handles secrets or policy-as-code.

> [!quote]- Source
> "If you run it from the AWS console side and if you haven't upgraded in your Terraform file, someone has changed a small change in future... when they are going and run this plan, and if they apply, you already upgraded and there is no downgrade policy for the RDS clusters."

### Motivation for NALA

Ram's stated reason for choosing NALA is ownership -- the ability to build something and see it through, rather than being rotated out mid-project as a contractor. That is a coherent and honest answer. However, he did not mention NALA's product, the payments mission, fintech compliance complexity, or anything specific about the technical environment. The motivation is about his personal contractor frustration, not about NALA.

> [!quote]- Source
> "When we are joining in this stage of companies, we can get some kind of ownership for the applications, and you can own the applications where you can build."

### Logistics

- Notice period: 2 weeks (rolling contract)
- Available: ASAP after notice
- Right to work: UK dependent visa on spouse, valid until April 2028, then ILR conversion. No sponsorship needed.
- Salary: GBP 75,000 (application listed $94,270 USD -- currency mislabelling on the form)

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Neutral | No reference to end users, developers, or internal customers of platform infrastructure. Patch Shield served the ops team's needs but Ram didn't frame it that way. |
| Play to Win | Weak positive | Built Patch Shield from zero without being asked for a full platform. Adapted when Jenkins was too complex for the team. Shows driver instinct at a surface level. |
| Speed Wins | Neutral | Used AI to accelerate Ansible playbook writing: "previously if I want to build this kind of Ansible setup it'll take 6 to 7 months, but now it will finish it in weeks." Pragmatic, not strategic. |
| Understand Why | Weak negative | Scenario answers were diagnostic checklists, not root-cause stories. No "here's why the system failed and what that taught us" moment. Describe-the-process, not explain-the-cause. |

## Candidate knowledge notes

- Patch Shield architecture: zone-segregated AWS inventory pull via Python + Ansible + cron/Node runner. Snapshot, patch, validate, report cycle with AZ sequencing to minimise blast radius. Worth noting as a usable pattern for any team without a patch strategy.
- State file drift is the real Terraform pain point Ram has lived. The RDS upgrade scenario he described is a genuine and common failure mode -- useful calibration question for future platform engineer screens.

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-14, [[2026-07-14 - Ram Kilari - Senior Platform Engineer Screen]]] Screened Ram Kilari for Platform Eng. Lean no -- SRE background, built Patch Shield (solid instinct), but technical depth thin: scenario answers were checklists not war stories, no Kubernetes/GitOps/Kafka experience, no commercial Azure. GBP 75k, 2-week notice, dependent visa (no sponsorship needed). Next step: proceed/no-proceed to candidate by EOD 2026-07-15.
