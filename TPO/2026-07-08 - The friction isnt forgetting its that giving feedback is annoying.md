---
tags: [tpo, seed]
heat: warm
date: 2026-07-08
source: "[[Hiring]]"
type: operator-guide
---

# The friction isn't forgetting. It's that giving feedback is annoying.

## Take

I built an internal bot (Chase) that chases hiring managers for missing interview feedback. It worked - escalation rates dropped, submission rates improved. But the root cause didn't change. Interviewers still hated filling out ATS scorecards. Chase was treating the symptom (late feedback) not the disease (the feedback form is a 5-minute tax on people who just spent 45 minutes interviewing). So I built Nudge: a Slack bot where interviewers brain-dump their thoughts in 60 seconds, and AI structures it into a scorecard they confirm with one click.

## Insight

Before you automate a reminder, ask whether the thing you're reminding people about is unnecessarily painful. If it is, fix the thing, not the reminder. Every ATS vendor adds Slack notifications assuming the problem is awareness. The problem is friction. An interviewer will happily type "Sarah was strong on system design but struggled with the ambiguity question, I'd advance her but want to probe resilience in the next round" into a Slack DM in 30 seconds. They will not spend 5 minutes navigating to Workable, finding the candidate, opening the scorecard form, rating 6 dimensions on a 1-5 scale, and writing comments in three text boxes. Same information. Completely different friction.

## Evidence

- Chase (internal bot): reduced manual chase effort from 3-5 hours/week to zero
- But: feedback quality didn't improve because the underlying form was still painful
- Nudge (product): Slack-native capture, AI structuring, one-click confirm
- V2 added probe threading: if Interviewer 1 flagged "weak on system design," Interviewer 2's opening DM weaves that in so they probe deeper
- No direct competitor in the Slack-native free-text capture space (Metaview, BrightHire require recording bots on the call)

## Angles

- "The Friction Diagnosis" as a named framework
- The internal-tool-to-product pipeline (Chase taught me the problem, Nudge solved it)
- Why Slack-native beats browser-redirect for feedback capture
- Probe threading as the compounding intelligence moat

## Context

*Private - do not publish.*

Nudge is a commercial product (nudgebot.ai, Northwall Technologies Ltd). Stripe billing live, multi-workspace OAuth, Slack App Directory. Pricing: GBP 39/79 per month. Strategy: sell, don't build - first 10 paying customers is the gate before any further development. TAM: 93,000 paid Slack orgs, ~111M GBP ARR potential.
