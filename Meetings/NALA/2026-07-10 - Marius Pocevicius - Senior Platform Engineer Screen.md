---
date: 2026-07-10
time: "12:45"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - Marius Pocevičius
interviewer: "[[Ryan Bolton-Smith]]"
interviewer_email: ryan.bookings@nala.money
candidate: Marius Pocevičius
candidate_email: marius.pocev@gmail.com
role: Senior Platform Engineer
project: "[[Hiring]]"
source: metaview
source_url: "https://my.metaview.app/notes/462339116"
tags: [meeting, interview, talent-screen]
---

# 2026-07-10 - Marius Pocevičius - Senior Platform Engineer Talent Screen

> [!summary] TL;DR
> Ryan ran a 30-minute talent screen with Marius Pocevičius for Senior Platform Engineer. Marius is a generalist engineer currently at Tuza (merchant onboarding fintech), previously at Otherworld (VR entertainment). He showed genuine enthusiasm for the solo-ownership nature of the role and NALA's build-it-yourself culture (Rafiki born from necessity). He has strong AWS/CDK/IaC fundamentals but acknowledged gaps in Kafka and some tooling at NALA's scale. Call was cut short -- Ryan scheduled a follow-up the same day at 3 PM to cover behavioural/technical scenarios.

## Screen Assessment

| Dimension | Rating | Notes |
|-----------|--------|-------|
| Motivation & fit | Strong | Actively looking for a challenge with more autonomy. Current role feels stagnant. Excited by solo ownership and scale. |
| Role understanding | Good | Asked the right first question -- "what does platform mean here?" Understands it varies by company. Grasps the breadth (security, observability, deployment, DevEx). |
| Technical surface area | Promising, gaps flagged | AWS, CDK, Terraform, CI/CD pipelines, Redis, observability. No Kafka experience. No explicit ECS/RDS depth discussed yet. |
| Communication | Good | Articulate, structured answers. Gave context without rambling. Self-aware about gaps. |
| Red flags | None significant | Generalist background could mean shallow platform depth -- needs probing in follow-up. |
| Green flags | Multiple | Build-it-yourself instinct (game servers at 13-14, VR hardware hacking). Curiosity-driven learner. Fintech domain familiarity. Genuinely energised by NALA's complexity, not performing enthusiasm. |

## Values Alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Positive | At Tuza, designed merchant onboarding to "allow the merchant to provide the most amount of information possible with the least friction possible" -- thinks from the end-user backward. |
| Play to Win | Positive | "Whenever something needs to be done, it doesn't matter whether I know how, it doesn't matter whether I know the tech, this is something that needs to be done. Therefore, I go ahead and learn how to do that." |
| Speed Wins | Neutral | No strong signal yet. Generalist instinct suggests bias to action, but not tested. |
| Understand Why | Positive | Unprompted, identified that Rafiki being "born out of necessity" was a positive culture signal. Asked probing questions about team structure and scale before accepting the pitch. |

## Key Discussion Points

### Why the role exists

Ryan explained the platform function was historically carried by Nico (ex-CTO) and Seb (OG engineer) from 2020. Both left in the last 6 months. A replacement had stepped in but took a career break due to family issues, leaving zero dedicated platform support. The role is solo, reporting daily to Eduardo (EM, Italy, 3-4 years tenure), sitting across both NALA and Rafiki teams.

> [!quote]- Source
> "This kind of left a bit of a hole in the business, right? Not having a dedicated platform person... we've now lost all dedicated platform support. Obviously we can get by it, but they're spinning out of like new services. The problem we've got isn't a scaling problem because spinning up new clusters and stuff isn't too difficult. But the problem that we've got is the velocity of the scale at which we approach."

### Marius's background -- generalist with platform instincts

Currently at Tuza (fintech, merchant onboarding automation for payment acquirers). Builds end-to-end: frontend, backend, AWS infrastructure, CI, Redis, observability. Previously at Otherworld (VR entertainment startup) where he was an extreme generalist -- backend, frontend, hardware integration, cross-compilation pipelines, Docker, CI for Windows/Linux builds. CS degree from King's College London.

> [!quote]- Source
> "Throughout all of that, I kind of built up a skill of whenever something needs to be done, it doesn't matter whether I know how, it doesn't matter whether I know the tech, this is something that needs to be done. Therefore, I go ahead and learn how to do that, learn a new language, learn how to do this very niche-specific skill to be able to build this feature."

### Early platform exposure

Started programming at 13-14 running game servers on rented CentOS boxes -- managing networking, port security, Linux administration. Drew a direct line from that to his current work with AWS CloudFormation/CDK.

> [!quote]- Source
> "One of my first kind of experiences with programming, let's say 13, 14, was basically running servers of games so that you could join them with friends and play together. And that was basically using whatever pocket money to rent some kind of Linux, at that point CentOS server, to then be able to run something and then manage all of the networking."

### Motivation to move

Feels he has hit a ceiling at Tuza -- same problems, no progression path. Wants to be around skilled people he can learn from. The solo-ownership platform role appeals specifically because it combines autonomy with high-stakes infrastructure.

> [!quote]- Source
> "I've reached a position where I'm doing the work that I'm doing day to day, and I don't really see myself progressing further than that. I'm just kind of dealing with more of the same challenges and problems."

### Gaps acknowledged

No Kafka experience. Some tooling gaps at NALA's scale. Conceptually familiar with the full stack but hasn't operated all tools deeply. Self-aware and framed it as ramp-up time, not blockers.

> [!quote]- Source
> "There are definitely tools that I haven't used too much and would need some time to pick up. I have no experience with Kafka. There are some gaps essentially, but conceptually all of this is very familiar and interesting."

### Enthusiasm for engineering-as-audience

Marius articulated an interesting perspective on platform engineering: engineers are the most demanding internal customers, and serving them well requires precision and resilience. This suggests he understands the service-orientation of the role, not just the technical side.

> [!quote]- Source
> "I think it's interesting to almost have engineering as an audience for the work that you do... the fact that you are responsible for deploying people's work, you're responsible that it runs smoothly aside from being correct in terms of its logic."

### Logistics

- Call cut short at ~32 minutes due to Ryan's schedule conflict.
- Follow-up booked same day at 3 PM for 10-15 minutes of behavioural/technical scenario questions.
- No on-call requirement for this role (Ryan confirmed).
- Engineering team is ~18 people total.
- Monthly transaction volume: $100M+.

## Propagation

### [[Ryan Bolton-Smith]]

- [2026-07-10, [[2026-07-10 - Marius Pocevičius - Senior Platform Engineer Talent Screen]]] Ran talent screen for Marius Pocevičius (Senior Platform Engineer). Positive initial read. Scheduled same-day follow-up at 3 PM for behavioural probing. Call was cut short due to back-to-back meetings.

### [[Hiring]]

- [2026-07-10, [[2026-07-10 - Marius Pocevičius - Senior Platform Engineer Talent Screen]]] New candidate screened for Senior Platform Engineer (B9B65FF169): Marius Pocevičius. Generalist with fintech experience (Tuza), AWS/CDK/CI skills. Gaps in Kafka. Progressed to same-day follow-up for behavioural/technical scenarios. Green flags: build-it-yourself instinct, self-aware about gaps, genuinely motivated by the challenge.

### Marius Pocevičius *(new People note stub needed)*

- **Role:** Senior Platform Engineer candidate
- **Current company:** Tuza (fintech, merchant onboarding)
- **Previous:** Otherworld (VR entertainment)
- **Education:** CS, King's College London
- **Email:** marius.pocev@gmail.com
- **Workable role:** Senior Platform Engineer (B9B65FF169)
- [2026-07-10, [[2026-07-10 - Marius Pocevičius - Senior Platform Engineer Talent Screen]]] Talent screen with Ryan. Strong motivation, generalist background, AWS/CDK/CI, no Kafka. Progressed to same-day follow-up. Values alignment: positive on Customers First, Play to Win, Understand Why.