---
tags: [tpo, seed]
heat: hot
date: 2026-07-08
type: operator-guide
---

# I built 21 tools and I'm not an engineer

## Take

In the last 12 months I've built 21 production tools for my People function - hiring bots, dashboards, an AI knowledge system, a performance framework engine, and a commercial SaaS product. I have no engineering degree. I can't whiteboard a system design. I built every one of them using Claude Code, and the total cost is less than one junior developer's monthly salary.

## Insight

The gap in People Ops isn't ideas or strategy. It's execution infrastructure. Every Head of People knows they should track 1:1 discipline, automate interview prep, monitor feedback cadence, and generate pipeline reports. Nobody does it because the build cost is prohibitive - you need engineering time, and engineering is always allocated to product. AI coding tools have collapsed that constraint. A People leader who can describe what they want in plain English can now build production tools in hours, not sprints. The era of the non-technical People leader is over. If you can't build your own tooling, you're competing against people who can.

## Evidence

- 21 distinct tools built between March 2025 and July 2026
- Chase bot: automated feedback chasing, runs hourly, 50+ escalation records, nobody exempt (including CEO)
- 1:1 Tracker: cross-references Google Calendar with HiBob org chart, identified capacity overload that drove a structural reorg (B2B Sales consolidation)
- Meeting Cost Dashboard: joins salary data with calendar data across 149 employees, revealed ~$772K total meeting cost / ~$193K monthly
- PeopleOS: AI-native control tower with Claude-powered /ask endpoint for instant People intelligence
- Nudge: commercial SaaS product (nudgebot.ai), Stripe billing, multi-workspace OAuth, Slack App Directory
- JD Intelligence: 76 roles, 540 competency definitions, AI-generated job descriptions calibrated to NALA's levelling framework
- Total infrastructure cost: Vercel (free tier for most), Supabase (free tier), GitHub Actions (free tier), Claude API (~$50/month)

## Angles

- The "describe it, don't design it" approach to building with AI
- Why People teams should own their own tooling (you understand the problem better than any engineer assigned to an internal tools ticket)
- The compound effect: each tool generates data that feeds the next tool
- The career signal: going from "uses AI to draft emails" to "builds production systems with AI" in 12 months
- What breaks when a non-engineer builds production tools (and how to handle it)

## Context

*Private - do not publish.*

Owen's self-review captured the evolution: "At the start I was using GPT/Gemini & Claude to draft communications and structure thinking. By March I was using Claude Code to build production tools." The 21 tools span internal NALA infrastructure (13), external products (3), personal knowledge systems (2), and side projects (3). All built primarily in Claude Code by someone whose job title is Head of People.

## First Draft

### I Built 21 Tools and I'm Not an Engineer

Twelve months ago I was using ChatGPT to draft Slack messages. Today I run 21 production tools across my People function - bots that chase hiring managers, dashboards that calculate meeting costs, an AI system that generates interview prep briefs, and a SaaS product with Stripe billing and a waitlist.

I have no engineering degree. I can't explain the difference between a B-tree and a hash map. I built every single one of these tools using Claude Code, and the total monthly infrastructure cost is less than a team lunch.

**Here's what I learned.**

### The Insight: Your Engineering Team Will Never Build Your People Tools

Every People leader I know has a backlog of tools they wish existed. A dashboard that shows whether managers are actually holding 1:1s. A bot that sends interviewers their prep before each call. A report that tells the CFO which roles are stalling and why.

None of these get built because engineering is allocated to product. Your internal tools ticket sits in the backlog behind revenue-generating features. Sometimes an engineer picks it up as a hack week project, builds 60% of it, and then goes back to their real work. You're left with a half-built dashboard that nobody maintains.

This is the structural problem. Not that People teams lack ideas, but that they lack the ability to execute on those ideas without begging for engineering time.

AI coding tools have broken that constraint. If you can describe what you want in plain English - "scan Workable for interviewers who haven't submitted feedback, cross-reference Google Calendar to find when the interview happened, then send a Slack message that escalates over time" - you can build it. Today. Without an engineer.

### What I've Built (The Full List)

I'm going to be specific because specificity is what makes this useful. Vague claims about "leveraging AI" help nobody.

**Hiring automation (5 tools):**
- A bot that chases interviewers for missing feedback with 3-tier escalation (Chase)
- A bot that catches candidates advanced without completed scorecards (Stage Gate)
- A bot that DMs interviewers prep briefs before their interviews (Interview Brief)
- A weekly pipeline health report with RAG status per role (Dashboard)
- A deterministic Monday pipeline brief for the CFO with week-over-week diffs

**People intelligence (4 tools):**
- An AI control tower with a natural-language /ask endpoint (PeopleOS)
- A live dashboard showing whether every manager-report pair has recurring 1:1s
- A meeting cost calculator joining salary data with calendar data across 149 employees
- A monthly org chart sync from HRIS to Google Sheets for Finance

**Hiring quality (3 tools):**
- An AI-powered JD generator with 76 roles and 540 competency definitions
- A weekly exec recruitment report (Slack Block Kit + PDF)
- A CLI-first AI screening pipeline (Haiku pre-screen + Sonnet deep assessment)

**Performance and culture (2 tools):**
- A personal AI knowledge system that ingests meeting transcripts, tracks decisions, and surfaces commitments
- A Manager Health Pulse that cross-references Windmill feedback data with calendar and vault notes

**Commercial product (2 tools):**
- Nudge: a Slack bot for zero-friction interview feedback capture, with Stripe billing and multi-workspace OAuth
- A growth agent CLI for waitlist management and outreach automation

**Side projects (2 tools):**
- A B2B SaaS for UK dog groomers (fully deployed, Stripe Connect, GDPR compliant)
- A Workable API CLI wrapper for real-time hiring data

Plus 3 more I'm probably forgetting.

### The Compound Effect

The real power isn't any single tool. It's that each one generates data that feeds the next.

The 1:1 Tracker showed me which managers weren't meeting their reports. That data fed the Manager Health Pulse. The Health Pulse showed that some managers had high meeting volume but zero documented feedback. That insight became the EYS framework's accountability layer. The EYS framework's evidence engine runs during meeting ingestion in the knowledge system, which is fed by the Google Drive transcript pipeline.

None of this was planned as an integrated system. Each tool solved an immediate problem. But because I own all the data and all the logic, the tools compose naturally. An engineering team building to a spec would never have created this - they'd have built each tool as an isolated project with its own data model.

### What Breaks (And How to Handle It)

I'm not going to pretend this is all upside. Building production tools without engineering training means you'll make mistakes that a junior developer wouldn't.

**You'll build fragile integrations.** My first version of the Chase bot broke when Workable changed their API pagination. An engineer would have built retry logic and error handling from the start. I added it after it broke in production on a Monday morning.

**You'll skip tests.** I still don't write automated tests for most of my tools. I test manually, which means I catch bugs after deployment, not before. For internal tools with a user base of 1 (me), this is acceptable. For Nudge, which has external users and Stripe billing, I learned the hard way that you need tests.

**You'll accumulate technical debt.** Several of my tools have hardcoded values that should be environment variables, duplicated logic that should be shared libraries, and no monitoring beyond "did it post to Slack this morning?" I clean these up when they cause problems, not proactively.

The honest trade-off: I ship 10x faster than if I waited for engineering, but the quality floor is lower. For People tools that need to work well enough, not perfectly, this is the right trade-off. For anything touching money or compliance, it's not.

### The Career Implication

A year ago, I described myself as "Head of People who uses AI." Now I describe myself as "Head of People who builds with AI." Those are different things, and the gap between them is widening.

Using AI means prompting ChatGPT for a better version of an email you already wrote. Building with AI means creating infrastructure that runs without you - bots that execute at 3am, dashboards that update weekly, systems that accumulate intelligence over time.

Every People leader will use AI. The ones who build with it will have a structural advantage that compounds every month. They'll have better data, faster processes, and lower operating costs. They'll spend their time on strategy and judgment instead of chasing, reporting, and formatting.

I'm not special. I have average technical aptitude and a broadband connection. What I have that most People leaders don't is the conviction that if I can describe the problem precisely enough, I can build the solution myself.

### Start Here

Don't try to build 21 tools. Build one. Pick the task you spend the most time on that requires the least judgment. For me, it was chasing interviewers for feedback. For you, it might be:
- Checking whether managers have 1:1s booked with all their reports
- Generating a weekly pipeline summary from your ATS
- Sending new hires a structured onboarding checklist on day 1

Describe what you want to an AI coding tool. Be specific about inputs (which APIs), logic (what conditions), and outputs (where the result goes). Build the first version in a day. Deploy it. Fix what breaks. Build the next one.

The tools compound. The skills compound. Twelve months from now, you'll wonder how you ever ran a People function without them.
