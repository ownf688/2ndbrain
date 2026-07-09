---
tags: [tpo, seed]
heat: hot
date: 2026-07-08
source: "[[Hiring]]"
type: operator-guide
---

# I built a bot that chases hiring managers so I never have to again

## Take

The single most time-consuming part of running a hiring function isn't sourcing, scheduling, or closing. It's chasing interviewers for feedback they promised 3 days ago. I automated the entire chase cycle with a bot that costs nothing to run, and it changed how our company thinks about hiring accountability.

## Insight

Every People team treats missing interview feedback as a people problem (interviewers are lazy/busy/forgetful) and applies a people solution (send a reminder, escalate to their manager, put it on the standup agenda). That's wrong. It's a systems problem. The chase cycle is perfectly predictable: you know who interviewed, when it happened, and whether they submitted. If it's predictable, automate it. Build a bot that cross-references your ATS with Google Calendar, identifies gaps, and sends escalating Slack messages on a timer. Nobody is exempt - including the CEO.

## Evidence

- At NALA, I was spending 3-5 hours per week manually chasing hiring managers for interview feedback
- Built a 4-bot hiring system in March 2026: Chase (feedback nudges), Stage Gate (scorecard enforcement), Interview Brief (pre-interview prep DMs), and Dashboard (weekly pipeline health)
- Chase runs hourly on weekdays, cross-references Workable candidates at interview stages with Google Calendar to find the actual interview time and attendees
- 3-tier escalation: 30min-24h friendly nudge in hiring channel, 24-72h firm reminder + DM to interviewer, 72h+ urgent message + DM interviewer + DM their manager (looked up via HiBob org chart)
- Nobody exempt: the bot has chased the CEO, the Head of Engineering, the CFO, and me. The chase-state log shows 50+ escalation records
- The bot never uses candidate surnames in Slack (first name + last initial only) for privacy

## Angles

- The "30-24-72 Rule" as a named framework for escalation timing
- Why calendar is the source of truth, not the ATS (Workable doesn't record when the interview actually happened)
- The difference between Chase (tardiness) and Stage Gate (process violations) - two distinct failure modes
- State committed to git: every escalation is auditable, no duplicates across runs
- Building this as a non-engineer using Claude Code

## Context

*Private - do not publish.*

The bot was born from NALA's hiring data: 7% high-performer rate, 33% left within a year, 70% attrition in the 2022 cohort, 1.5-2M GBP cost of the replace-the-replacement cycle. The 4-bot system was built in March 2026 from research across 60+ Slack channels and 4 years of hiring history.

## First Draft

### I Built a Bot That Chases Hiring Managers So I Never Have to Again

I used to spend 3-5 hours every week doing the same thing: DMing hiring managers on Slack asking if they'd submitted their interview feedback. "Hey, you spoke to Sarah on Tuesday - did you get a chance to fill in the scorecard?" Then waiting. Then following up. Then escalating to their manager. Repeat across 8 open roles and 15 interviewers.

One Wednesday I counted the messages. Fourteen chase messages before lunch. Fourteen. For a task that is entirely predictable and requires zero judgment.

**So I built a bot to do it for me. Here's exactly how.**

### The Problem Isn't Forgetting. It's That Nobody's Watching.

The conventional wisdom is that interviewers forget to submit feedback. They don't forget. They deprioritise it because there's no consequence. Their next sprint standup matters more than a Workable scorecard that nobody checks.

The real problem is accountability at scale. When you have 3 open roles and 5 interviewers, you can track feedback submissions in your head. When you have 8 roles and 15 interviewers doing 20+ interviews a week, you physically cannot. Things slip. And when things slip, you get interviewers submitting feedback 5 days after an interview based on a vague recollection, which is worse than no feedback at all.

### The Architecture: Four Bots, Not One

I didn't build one tool. I built four, because missing feedback is actually four different problems:

**1. Chase** - catches tardiness. An interviewer spoke to a candidate but hasn't submitted feedback. This is the volume problem - it happens constantly.

**2. Stage Gate** - catches process violations. A recruiter advanced a candidate to the next stage before the previous interviewer submitted their scorecard. This is the quality problem - decisions made without evidence.

**3. Interview Brief** - prevents poor interviews. Before each interview, the bot DMs the interviewer with the candidate's prior feedback, the stage-specific assessment criteria, and a link to the relevant playbook. An interviewer who walks in prepared gives better feedback.

**4. Dashboard** - catches pipeline rot. Every Monday, a report drops in #exec-hiring showing candidates stuck at the same stage for 7+ days, empty pipelines, and a RAG status per role. This is the visibility problem - leadership doesn't know where hiring is stalling.

### How Chase Works (Build This Yourself)

Chase is the simplest and highest-impact of the four. Here's the logic:

**Step 1: Scan your ATS.** Every hour on weekdays, pull all candidates at interview stages (anything past "Applied"). For each one, check whether any interviewer has submitted a rating or review.

**Step 2: Cross-reference Google Calendar.** This is the key insight. Your ATS knows a candidate is at the "Interview" stage, but it doesn't reliably record when the interview happened or who attended. Google Calendar does. Search across your hiring team's calendars for events matching the candidate name. Extract the attendees and the event end time.

**Step 3: Calculate the gap.** Compare the interview end time to now. That's how long the interviewer has had to submit feedback.

**Step 4: Escalate on a timer.**

| Gap | Action | Channel |
|-----|--------|---------|
| 30 min - 24 hours | Friendly nudge | Hiring channel |
| 24 - 72 hours | Firm reminder | Hiring channel + DM to interviewer |
| 72+ hours | Urgent | Hiring channel + DM interviewer + DM their manager |

**Step 5: Persist state.** After each run, write the current chase state to a file (I use JSON committed to git). This prevents duplicate messages and gives you an audit trail. When a scorecard is submitted, the record clears automatically on the next run.

The manager lookup for tier-3 escalation comes from your HRIS (I use HiBob's org chart API). The bot looks up the interviewer's manager and DMs them directly: "Your report interviewed [Candidate First Name + Last Initial] 3 days ago and hasn't submitted feedback."

### The Rule That Makes It Work: Nobody Is Exempt

When I deployed Chase, the first person it escalated to tier 3 was our CEO. The second was our Head of Engineering.

This is not a bug. This is the feature.

If you build an accountability system with a VIP skip list, you don't have an accountability system. You have a tool that enforces rules for junior people and lets senior people do whatever they want. Everyone in the company will know this within a week, and the tool loses all credibility.

Our CEO gets chased by the same bot, on the same timer, with the same escalation path. The only person who doesn't get chased is the bot itself.

### What I'd Do Differently

**Add response tracking.** Chase knows whether feedback was submitted, but it doesn't know the quality. A one-line scorecard ("seemed fine") technically clears the chase, but it's not useful feedback. Version 2 should flag thin submissions for a quality check.

**Integrate with the ATS webhook, not polling.** Chase polls Workable hourly. A webhook-based approach would react to stage changes in real time. I chose polling because it was simpler to build and debug, but webhooks would reduce the delay between interview and first nudge.

**Build the dashboard first.** I built Chase first because it solved my biggest pain point. But in hindsight, the Dashboard (Monday pipeline health report) created more organisational change because it made hiring health visible to leadership. Visibility drives accountability faster than nudges.

### The Numbers

Before Chase, I had no reliable data on feedback submission rates because I was tracking it manually in my head. After Chase, I have a complete audit log of every interview, every gap, every escalation.

What I can tell you: the 3-5 hours per week I spent chasing are gone. The bot handles it. I spend that time on hiring strategy, candidate experience, and interviewer calibration - things that actually improve outcomes.

The deeper impact is cultural. When interviewers know that a bot will chase them (and escalate to their manager at 72 hours), feedback becomes a priority, not an afterthought. The bot doesn't get tired, doesn't feel awkward about chasing a VP, and doesn't skip a week because it's busy.

### Build This. Today.

You need four things:
1. ATS API access (Workable, Greenhouse, Lever all have one)
2. Google Calendar API access (service account with read access to hiring team calendars)
3. Slack API (bot token with channel posting + DM permissions)
4. HRIS API for manager lookup (HiBob, Rippling, whatever you use)

The logic is ~400 lines of Python. I built the first version in a day using Claude Code. The escalation timer is the hardest part to get right - too aggressive and people resent the bot, too gentle and they ignore it. 30 minutes is too soon (the interviewer might still be in back-to-back meetings). 24 hours is when gentle stops working. 72 hours is when you involve their manager.

If you run a hiring function with more than 5 open roles, you should not be spending your time chasing interviewers for feedback. Build the bot. Reclaim the hours. Spend them on something that actually needs a human.
