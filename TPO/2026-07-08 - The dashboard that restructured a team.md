---
tags: [tpo, seed]
heat: warm
date: 2026-07-08
type: operator-guide
---

# The dashboard that restructured a team

## Take

I built a dashboard that cross-references Google Calendar with our HRIS org chart to show whether every manager-report pair has a recurring 1:1 booked. The data revealed that our COO had 23 direct reports and several managers hadn't met their reports in weeks. That data directly drove a structural change: consolidating B2B Sales, Trading, and Customer Success under a single leader. A People team dashboard changed how the company was organised.

## Insight

People teams produce reports that describe the org. They rarely produce data that changes the org. The difference is specificity and timing. A quarterly engagement survey that says "managers could communicate better" changes nothing. A live dashboard that shows "these 4 manager-report pairs have no 1:1 booked this month, and this leader has 23 directs" forces a conversation about structure. Build dashboards that make structural problems visible to the people who can fix them, and the dashboards become the catalyst, not the report.

## Evidence

- 1:1 Discipline Tracker: cross-references Google Calendar against HiBob org chart
- Automated weekly pipeline via GitHub Actions, deployed on Vercel
- Identified COO with 23 direct reports (impossible span of control)
- Identified managers with no 1:1s booked for their reports
- Data directly aided structural reorg: B2B Sales, Trading, CS consolidated
- Owen's self-review: "identified capacity overload gaps in the leadership team and aided a structural change - that's real business impact driven from data"

## Angles

- The difference between descriptive People analytics (what happened) and catalytic People analytics (what needs to change)
- Why live dashboards beat quarterly reports for driving structural decisions
- Calendar + HRIS as the two data sources that reveal management reality vs. org chart fiction
- Building for specificity: "these 4 pairs have no 1:1" is actionable, "1:1 discipline is low" is not

## Context

*Private - do not publish.*

Built early 2026. The meeting cost dashboard (separate tool) provided complementary data: ~$772K total meeting cost across 149 employees, ~$193K monthly. Together, the 1:1 tracker and meeting cost dashboard gave Owen two levers: are people meeting (1:1 tracker) and are they meeting efficiently (meeting cost)?
