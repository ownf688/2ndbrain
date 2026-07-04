---
date: 2026-07-04
type: war-story
themes: [hiring, data, strategy, remote-teams]
source: "[[Restricting hiring geography tanks top-of-funnel]]"
heat: warm
status: seed
---

# Geographic hiring restrictions kill your pipeline before you can measure the damage

> **The take:** When you restrict hiring to one city, the damage is invisible in weekly metrics because recruiters compensate with volume. By the time you notice, you've lost months.

## Context (private, not for publication)
Months of London-only engineering hiring at NALA produced a thin pipeline (1 platform engineer candidate after withdrawals, backend barely at 4 pair programmings/week). Recruiters were hitting activity targets so it didn't look broken in standup dashboards. Ryan predicted response rates would triple when the CEO approved EU/UK remote hiring on Jun 29. The unlock only happened after a data brief showing the pool size problem.

## The insight
Geographic hiring constraints are one of the few talent decisions where the damage compounds silently. Here's why:

Recruiters are professionals. When the pool shrinks, they work harder -- more outreach, more creative sourcing, more follow-ups. Their activity metrics stay green. The weekly standup looks fine. But response rates drop, candidate quality thins, and the pipeline quietly empties.

The problem only becomes visible when you compare input (sourcing effort) to output (qualified candidates in pipeline). By then, you've lost weeks or months of compounding -- the candidates who would have responded, referred friends, and accelerated the flywheel.

The fix is a structural review trigger: if qualified pipeline drops below X after N weeks under a geographic constraint, the constraint goes to leadership for review automatically. Don't wait for recruiters to escalate -- they'll compensate with effort instead, because that's what good recruiters do. Make the data force the conversation.

## Evidence
- Months of London-only constraint: 1 platform engineer candidate remaining, backend at 4 pair programmings/week (target was higher)
- Recruiter activity metrics looked healthy throughout the period
- Response rate prediction: "triple" after geography opened up
- Constraint only lifted after a dedicated data brief to the CEO -- it didn't self-correct from standard metrics

## Angles
- [ ] Blog post: "Your recruiters are hiding your hiring problem -- and it's not their fault"
- [ ] LinkedIn post: "We restricted engineering hiring to London for months. Activity metrics stayed green. Pipeline was dying. Here's what the data missed."
- [ ] Talk/panel point: Why recruiting dashboards lie about geographic constraints

## Adjacent seeds
- [[2026-07-04 - The proxy trap - activity metrics that look like coaching but arent]]
