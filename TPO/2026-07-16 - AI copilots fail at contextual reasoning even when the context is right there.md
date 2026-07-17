---
date: 2026-07-16
title: "AI copilots fail at contextual reasoning even when the context is right there"
take: "The gap that makes AI assistants frustrating isn't data access — it's the inability to connect dots between facts they already hold."
heat: hot
status: seed
tags: [tpo]
source: "[[2026-07-16 - Parth Owen 1-1]]"
---

## Take

The gap that makes AI assistants frustrating isn't data access — it's the inability to connect dots between facts they already hold.

## Insight

AI tools are getting very good at retrieval. Give them the right context, the right files, the right integrations, and they'll find the answer to any direct question. What they can't do — yet — is reason *across* facts they already possess.

The failure mode: you ask the AI to review a team plan, it spots a dependency flag ("this quarter is too ambitious without the Senior Analytics Engineer hire"), and surfaces it as an open concern. But it already knows the hire was made last month. The candidate is in the ATS. The start date is on the calendar. The People note has been updated. The AI has all of it. It just doesn't connect the dots.

This isn't a retrieval problem. It's an inference problem. And it's the reason AI copilots still create work rather than saving it — because humans have to do the connective thinking that the tool should be doing automatically.

The pattern is consistent: AI excels at "find me X" but stumbles at "given X, Y, and Z — what does that mean?" The latter is what experienced operators actually spend most of their time doing. It's the gap between a fast-but-dumb analyst and a genuinely useful thought partner.

## Evidence

- Concrete example from a Q3 planning session (anonymised): AI reviewed multiple team plans, spotted a capacity flag in the data team plan — specifically that a key hire hadn't been made yet. The AI had access to the hiring system, the People notes, the plan documents. The hire had been made weeks earlier. The AI didn't connect these.
- The AI answered every direct question perfectly. It couldn't answer the indirect one: "does this flag still apply?"
- This isn't a one-off. The same class of failure appears in: performance management (flagging issues already resolved), project tracking (surfacing blockers already cleared), and hiring (treating candidates as uncontacted when follow-up is already in flight).

## Angles

1. **The retrieval-inference gap** — most AI capability investment has gone into retrieval; inference is the next frontier and nobody has cracked it
2. **Why this matters for operators** — if your AI creates more reconciliation work than it saves, net productivity is negative. Most "AI copilot" tools are net-positive on information volume and net-negative on cognitive load
3. **The trust cost** — every time an AI surfaces a stale concern as urgent, operators lose confidence in the signal. They start over-verifying. The tool becomes a source of noise, not signal
4. **What good looks like** — AI that asks "does this fact still apply?" before surfacing it. That's a different architecture from what most tools are built on today

## Context (private — do not publish)

Owen observing his own Claude Code brain session. Was reviewing Parth's Q3 data plan, and Claude flagged the analytics engineer hire as an open concern despite Pearl's hire being logged in Workable, the People notes, and the brain. Parth confirmed he'd observed the same pattern with his own AI tools. This is a real and recurring frustration that generalises beyond NALA.

## First Draft

**Hook**

I gave my AI assistant access to everything. Our hiring system. Our people notes. Our planning documents. All of it, live and current. Then I asked it to review our team plans for Q3.

It came back with a concern: the data team's plan was "too ambitious without the Senior Analytics Engineer hire."

The hire had been made three weeks earlier.

**Setup**

This isn't a story about bad AI. The tool answered every direct question I asked correctly. It retrieved the right information. It found the right files. It synthesised well. What it couldn't do was look at three facts it already held — the plan's dependency flag, the Workable record of the hire, the new joiner's start date on the calendar — and conclude that the concern was already resolved.

That's the gap. Not retrieval. Inference.

**Thesis**

**AI tools are getting very good at finding information. The problem is that finding and reasoning are different skills — and most AI copilots only do the first one.**

**Evidence — The retrieval-inference gap**

There are two kinds of questions you ask an analyst:

Direct: "Find me the salary benchmark for a compliance role in Brussels."

Indirect: "Given what we know about this candidate's situation, how much leverage do we actually have?"

AI handles the first type very well. It handles the second type poorly. The indirect question requires inference — drawing conclusions that aren't explicitly stated anywhere, connecting dots across multiple sources, and applying judgment to figure out what the facts *mean*.

Experienced operators spend the majority of their time on indirect questions. It's not "find me the data." It's "what does the data tell us?" That's the work. And AI copilots, almost without exception, punt it back to you.

**Evidence — The trust cost**

Here's what happens when AI surfaces stale concerns as urgent: you check. You verify. You find out it's already resolved. You move on.

And then it happens again. And again.

At a certain point, you stop trusting the signal. You start treating every AI-generated flag the same way you treat a spam folder — with the assumption that most of it is noise. At which point, you're doing all the filtering work yourself. The tool hasn't saved you time; it's added a verification step to your workflow.

This is the hidden cost of AI tools that can't reason across context. They're not neutral. They actively erode trust in their own outputs, which means the humans around them do more work, not less.

**Evidence — What the pattern looks like**

The failure mode appears consistently across different use cases:

- **Hiring:** flags a candidate as uncontacted when a follow-up email went out yesterday
- **Performance:** surfaces a concern that was raised and resolved in last week's 1:1
- **Project tracking:** marks a dependency as outstanding when it was cleared in a Slack thread the tool was never shown

In each case, the AI had access to the information that would have resolved the flag. It just didn't make the connection.

**Framework — What good looks like**

An AI that reasons across context would ask: "Before I surface this as a concern, does this fact still apply?"

That's a different architecture from what most current tools use. Most tools treat each query as a fresh retrieval problem: find the relevant information, synthesise it, return the answer. They don't hold a persistent model of "what's true right now" and update it as new facts come in.

The tools that will actually replace the analyst role are the ones that maintain a live state model — not just a knowledge base you can query, but a set of beliefs about what's true that get updated automatically when new information contradicts them.

We're not there yet. But it's where this is going.

**So What**

If you're deploying AI tools in your team today, here's what this means practically:

The AI will surface false alarms. Budget for it. Build a verification step into your workflow for high-stakes flags — not because the AI is unreliable, but because inference is genuinely hard and the tools aren't good at it yet.

Be selective about what you ask it to monitor. It's better at "tell me everything about X" than "tell me what's changed about X." The former is retrieval. The latter requires inference.

And when it gets the indirect question right — when it connects the dots without being asked — notice it. That's a meaningful signal that the tool is getting better at the hard thing.

**Action**

- Pull the last 10 AI-generated flags or summaries from your team's tools. How many were stale? That's your inference failure rate.
- Ask your AI copilot a lateral question: "Does X concern still apply given Y?" See how it handles it.
- Separate your AI use cases into retrieval tasks (AI is great) and inference tasks (AI needs a human in the loop). Design your workflows accordingly.
