# How This Second Brain Works

> A comprehensive technical overview for AI agents operating on this vault.

## What this is

This is a personal Obsidian vault functioning as a "second brain" for Owen Fleming, Head of People at NALA (a fintech building cross-border remittances for the African diaspora). It is not a software project — it is a **Markdown knowledge graph** where meetings feed people notes, people notes feed project notes, and project notes feed daily briefs. The graph is the product.

The brain is not a minutes machine — it is a **judgment-and-execution engine**. It logs decisions with predictions and reviews them, closes loops, surfaces things before asked, and proposes direction rather than just summarising. It learns from corrections and gets sharper over time.

The vault is operated by AI agents (primarily Claude Code) using a set of shared skills. The human (Owen) approves all writes, resolves ambiguities, and makes judgment calls. The AI does acquisition, distillation, entity resolution, propagation, trajectory analysis, commitment tracking, and proactive follow-up.

## NALA Values (design spec for this brain)

These values are not inspirational wallpaper — they are the **design specification** that governs how the brain reasons, writes, and prioritises:

- **Customers First, Always** — Owen's customers are candidates and hiring managers. The brain tracks *their* experience — flags application black holes, drafts timely comms, never lets silence become the brand.
- **Play to Win** — Drivers, not passengers. The brain is proactive: closes loops, chases commitments ("you told Benji X by Friday — no evidence it's done"), enforces the 4Ds on every task.
- **Speed Wins** — Gets lighter as it grows. Gives an opinionated call (80% data, 20% intuition). Defaults to async single-source-of-truth.
- **Understand Why** — Logs the *why* of every decision. Reviews its own predictions to sharpen judgment. Promotes root-cause Knowledge notes.

## Operating Frameworks (use in every output)

**The 4D Framework** governs every decision and task:

| D | Must answer |
|---|-------------|
| **Data** | What evidence/context informs this? |
| **Decision** | What was decided and *why*? |
| **DRI** | Who owns it? |
| **Deadline** | By when? |

If any D is missing, flag it — don't proceed as if complete.

**What / So What / Now What / When** governs every output:

| Step | Purpose |
|------|---------|
| **What** | State the situation/finding |
| **So What** | Why it matters — implication, risk, opportunity |
| **Now What** | Concrete action to take |
| **When** | Deadline or urgency |

Every brief, follow-up, and recommendation must follow this structure.

## The Brain's Quality Bar

The brain itself is measured on the same Great/Good/Mediocre/Bad framework it uses for projects:

| Bar | Definition |
|-----|------------|
| **Great** | Decisions changed because the brain surfaced something. Predictions reviewed and calibrated. Unprompted surfacing of risks/opportunities. Run-cost stays flat as the vault grows. Owen trusts it enough to delegate judgment. |
| **Good** | Accurate distillation. Reliable ingestion + propagation. Commitment sweep catches things. But reactive — Owen has to ask for everything. |
| **Mediocre** | Notes are created but the graph doesn't connect. Propagation is incomplete. No decision tracking. No proactive surfacing. |
| **Bad** | Stale notes. Repeated mistakes. Surfacing completed items as overdue. Hedging instead of committing. Losing trust. |

## Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        SOURCES                                       │
│  Google Drive │ Notion │ Slack │ Workable │ Metaview │ Calendar │    │
│  Gmail │ Manual paste                                                │
└──────────────┬───────────────┴────────┴───────┴──────────────────────┘
               │
               ▼
┌──────────────────────────────┐
│     PRODUCER SKILLS          │     Zero-token bash script (gdrive)
│  pull-gdrive-transcripts     │     or agent-mediated (notion)
│  pull-notion-transcripts     │
└──────────────┬───────────────┘
               │  Normalized transcript artifact
               │  (format_version: 1 contract)
               ▼
┌──────────────────────────────┐
│     CONSUMER SKILL           │
│  ingest-meeting              │     Reads artifact → distills →
│                              │     resolves entities → propagates
└──────────┬───────────────────┘
           │
           ▼
┌──────────────────────────────────────────────────────────────────────┐
│                     OBSIDIAN VAULT                                    │
│                                                                       │
│  /Meetings/NALA/    ←── distilled meeting notes with raw transcript   │
│  /People/           ←── one note per person, interaction log          │
│  /Projects/NALA/    ←── project notes with quality frameworks         │
│  /Decisions/        ←── decision journal (4D + prediction + review)   │
│  /Knowledge/        ←── atomic claim-shaped concept notes             │
│  /Briefs/           ←── morning brief snapshots                       │
│  /Daily/ /Weekly/   ←── date-rolled journals                          │
│  /Inbox/ /Archive/  ←── intake + cold storage                         │
│  /Templates/        ←── canonical note templates                      │
│  /Copilot Rules.md  ←── persistent corrections + voice + heuristics   │
│                                                                       │
└──────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌──────────────────────────────┐
│     ANALYSIS SKILLS          │
│  morning-brief               │     Reads project + Slack → trajectory call
│  update-project              │     Gathers deltas → health update
│  daily-pulse                 │     Cross-team attention digest
│  normalize-meeting           │     Cleans legacy meeting notes
└──────────────────────────────┘
           │
           ▼
┌──────────────────────────────────────────────────────────────────────┐
│     OPERATIONAL PATTERNS (proactive, session-cron-driven)            │
│                                                                       │
│  commitment-sweep            │     Scans for open commitments →       │
│                              │     auto-drafts responses              │
│  meeting-prep                │     Lookahead: enriches each call with │
│                              │     People/Projects/Metaview/Workable  │
│  hiring-radar (Wed)          │     RAG board across open reqs         │
│  weekly-reflection (Fri)     │     Decision review + calibration      │
└──────────────────────────────────────────────────────────────────────┘
```

## The Transcript Contract

The key architectural insight: **producers and consumers are decoupled via a versioned contract**. Any source (Google Drive, Notion, future sources) emits the same normalized artifact. The consumer (`ingest-meeting`) never knows or cares where it came from.

### Contract format (v1)

```yaml
---
format_version: 1          # Required. Identifies this as a contract artifact.
source: gdrive              # Required. Producer ID (gdrive | notion | <custom>).
title: "Meeting Title"      # Required. Human-readable.
date: 2026-07-02            # Required. YYYY-MM-DD.
participants:               # Required. List of attendee names.
  - Owen Fleming
  - Lynnette Mutugi
source_file: "..."          # Provenance. Original filename.
source_url: "https://..."   # Provenance. Link to source.
empty: true                 # Optional. Set when no audio was captured.
diarized: false             # Optional. Set when speaker labels are missing.
---

## Meeting Title - Transcript

### 00:06:08

**Owen Fleming:** Hey, how's it going?

**Lynnette Mutugi:** Good. All good.

### 00:07:08

**Lynnette Mutugi:** So on litigation, we are good to go...

### Transcription ended after 00:45:16
```

**Rules:**
- The transcript body is the **only quotable source**. AI summaries from the producer are stripped.
- If `empty: true`, write a placeholder meeting note — don't distill.
- If `diarized: false`, attribution is unknown — infer cautiously and flag.
- If the body looks truncated, stop — don't distill from a partial source.

## Vault Node Types

### Meeting notes (`/Meetings/NALA/YYYY-MM-DD - Title.md`)

The primary corpus. Each note follows `/Templates/meeting.md`:

```
Frontmatter: date, time, timezone, type, attendees (wikilinks), project, duration,
             status, source, source_file, source_url, tags

Sections (in order):
1. TL;DR callout — "what changed because this meeting happened"
2. Decisions — each with verbatim source quote (<=15 words)
3. Action items — owner as [[Person]] link, due date if mentioned
4. Open questions — unresolved items
5. Key discussion points — synthesized paragraphs with foldable source quotes
6. Candidate Knowledge notes — flagged atomic insights (not drafted)
7. Propagation — proposed additions to People/Projects notes
8. Raw transcript — full artifact body in foldable callout
```

**Meeting types:** standup, 1on1, interview, weekly, cross-tribe-sync, working-session.

### People notes (`/People/<Name>.md`)

One per person. The `aliases` frontmatter is the canonical entity resolution source.

```yaml
---
aliases: [Lynnette Mutugi, Lynnette, Lynette]
company: NALA
role: Senior People Partner, Africa | Asia
tags: [person]
---
```

The `## Interactions` section is append-only:

```markdown
## Interactions

- [2026-07-02, [[2026-07-02 - Owen Lynette 1-1]]] Building Claude payroll tool — "she's defensive"
- [2026-06-29, [[2026-06-29 - People Ops Check-in]]] Planned birthday cake-cutting
```

**`/People/Me.md`** is special — its aliases define how the vault owner is recognized in transcripts (name variants, email, usernames, known mistranscriptions).

### Project notes (`/Projects/NALA/<Project>.md`)

Track ongoing initiatives. Required sections for `morning-brief` eligibility:

```markdown
## Quality framework       — Great/Good/Mediocre/Bad definitions (project-specific)
## Project keywords        — terms for Slack keyword search
## Slack channels to monitor — canonical channel allowlist
## Critical-path items     — checkbox list, updated in place by briefs
## Project owners          — [[Person]] links (optional)
## Updates                 — dated Health + Deltas blocks
## Decision log            — chronological decisions with meeting sources
```

### Decision journal (`/Decisions/YYYY-MM-DD - Title.md`)

Material decisions logged with the 4D template (see `/Templates/Decision.md`). Each decision includes:

```
Frontmatter: date, decision (one-line), status, review_date, confidence (0-100%),
             outcome (pending | right-right | right-lucky | wrong-learned | too-early), tags

Sections:
1. The 4Ds — Data, Decision (with why), DRI, Deadline
2. Options considered — chosen option + why, alternatives + why not
3. Prediction — expected outcome with confidence %
4. What Great looks like — what separates great from good for this decision
5. Review — filled on review_date: what happened, score, calibration note
6. Source — meeting notes, Slack threads, links
```

**Decision practice rules:**
- Log at decision time, not after the fact. Include options considered and why the winner won.
- Predict + state confidence %. This calibrates judgment over time.
- Set a review date. The Friday reflection surfaces decisions due for review.
- Score honestly on review: right-for-right-reasons, right-but-lucky, wrong-but-learned, too-early.
- Promote patterns to Knowledge notes after 3+ similar decisions.

### Knowledge notes (`/Knowledge/`)

Atomic, claim-shaped concept notes. The title is a claim, not a topic:
- "Restricting hiring geography tanks top-of-funnel" (not "Hiring geography")
- "Decoupling performance scoring from compensation prevents gaming" (not "Performance management")
- "Parallel regulatory tracks hedge risk but double engineering surface area" (not "EU launch")

Flagged as candidates during meeting ingestion. Promoted during weekly review (1-3 per week). Currently 3 promoted notes in the vault.

### Copilot Rules (`/Copilot Rules.md`)

A persistent corrections file read at the start of every session. Contains:

1. **Corrections** — specific things the brain got wrong, with instructions not to repeat (e.g., "Peter req pack is noise", "CFO Directorate meeting is NOT an exec 1:1")
2. **Decision heuristics** — Owen's reasoning patterns and Jerry's principles (e.g., "cost of doing nothing", "second-order signalling", "80% data, 20% intuition")
3. **Operating rules** — standing rules like "every task needs the 4Ds", "don't hedge trajectory calls", "triangulate, don't trust single sources"
4. **Temporal invalidation rule** — when durable facts change, write the new fact and mark the old one superseded
5. **Voice** — Owen's writing style: direct, punchy, no corporate fluff. Short sentences. Active voice. Lead with the ask or the decision.
6. **Draft corrections log** — when Owen edits a draft, log original vs final + the pattern. After 3+ similar corrections, promote to a standing rule. This is how the brain learns.

### Briefs (`/Briefs/YYYY-MM-DD - <Project>.md`)

Morning brief snapshots. Each brief:
- Commits to a trajectory bar (Great/Good/Mediocre/Bad) — no hedging
- Lists deltas since last snapshot with Slack thread references
- Flags stale vault notes
- Surfaces newly discovered Slack channels
- Names open risks
- Suggests one concrete first action
- Includes a Slack-pasteable summary (<=100 words, no framework jargon)

## Connected Source Systems

The brain reads from these systems via MCP (Model Context Protocol). They enrich People/Projects notes and power briefs, radars, and meeting prep. All are read-only — writes require explicit confirmation.

### Workable (`nalamoney`)
- **What:** ATS — open roles, candidates, pipeline stages, scorecards
- **When to use:** Wednesday hiring radar; morning briefs on Hiring; when ingesting interview meetings (cross-reference candidate status); when a name appears in a transcript and you need to check their application
- **Pipeline stages:** Sourced -> Applied -> Phone Screen -> Interview -> Practical Test -> Behavioural Interview -> Final Interview -> References -> Offer -> Hired
- **Role shortcodes (current, 8 open roles):**
  - Growth Manager Ghana: `AD4B0D198A`
  - Senior Backend Engineer: `2E2F7AE3AD`
  - Growth Manager Francophone Africa: `8B43BC7310`
  - Europe MLRO: `9BF8A8830F`
  - Lead Engineer Collections & Treasury: `802FA8ECC9`
  - EU Managing Director: `528FBBD194`
  - Senior Platform Engineer: `B9B65FF169`
  - Senior FX Sales & Trading Lead: `92AAEDACE6`

### Metaview (NALA workspace)
- **What:** Interview transcripts, AI-generated summaries, candidate scorecards, structured feedback
- **When to use:** After ingesting an interview meeting — pull the Metaview conversation for richer data (scorecard, structured feedback); during hiring radar to check interview quality metrics; when enriching People notes for interviewers
- **Owen's participant_id:** `c84eda9a-94d8-11f0-b197-0bdabd580c1d`
- **Access:** Admin, paying plan, full data access (org 10833)
- **Scale-aware:** 1-5 conversations -> full transcripts; 5-20 -> summaries; 20+ -> use AI fields

### Google Calendar
- **What:** Owen's schedule — meetings, attendees, locations, Workable interview links
- **When to use:** Meeting-prep lookahead (before each call, surface relevant People/Projects notes + last interaction + open action items); daily morning brief (what's on today); identifying exec meetings for follow-up triggers
- **Exec meeting detection:** Any event with Benji, Nico (nicolai.eddy@nala.money), or Peter Gulliver triggers the executive follow-up rule after ingestion

### Gmail
- **What:** Email threads, drafts
- **When to use:** When a brief or meeting references an email action ("I sent Peter the req pack"); to check if an expected reply arrived; to draft follow-up emails after exec meetings
- **Privacy:** Never read email bodies unless explicitly asked. Search by subject/sender to confirm existence, not to surveil.

### HiBob (via Workable employees endpoint)
- **What:** Employee data — active/inactive status, departments, roles
- **When to use:** People-risk radar (who's new, who's leaving, probation dates); enriching People notes with current role/department; morning briefs when team changes are relevant

## Entity Resolution

Entity matching is the backbone of the graph. Without it, meetings don't connect to people, and people don't connect to projects.

### Resolution priority

1. **Exact filename match** (case-insensitive): "Lynnette Mutugi" -> `People/Lynnette Mutugi.md`
2. **Exact alias match**: "Lynette" -> matches `aliases: [..., Lynette]` in `Lynnette Mutugi.md`
3. **Fuzzy first-name match** (only if unambiguous across the vault): "Lynnette" -> only one Lynnette exists
4. **Ambiguous** -> batch for user confirmation. Never auto-pick.

### Known mistranscription aliases in this vault

| Transcript renders as | Resolves to | Why |
|----------------------|-------------|-----|
| "City" | [[Sidi Ngade]] | Gemini mistranscription of "Sidi" |
| "Lynette" | [[Lynnette Mutugi]] | Alternate spelling |
| "Ollie" | [[Oli Woolf]] | Nickname |
| "Edo" | [[Edoardo Foco]] | Shortened name |
| "Chris" (eng context) | [[Christos Petropoulos]] | Shortened name |
| "AL", "Ali", "Alia" | [[Alessandro Colaneri]] | Shortened name |
| "Chi" | [[Chidi]] | Shortened name (Owen's usage) |
| "Twiga - Meeting Room" | NOT A PERSON | London office conference room mic; captures all in-room speakers without diarization |

### Self-recognition

`/People/Me.md` aliases = `[Owen Fleming, Owen, owen.fleming@nala.money, owen.fleming]`. Any of these in a transcript = the vault owner speaking.

### Stub creation

When a new entity is confirmed (not every mention — only critical-path people for recurring meetings):

```yaml
---
aliases: [Full Name, Short Name]
company: NALA
role: <if known>
tags: [person]
---

# Full Name

First met in [[YYYY-MM-DD - Meeting Title]].

## Context
<1-2 lines>

## Interactions
- [YYYY-MM-DD, [[Meeting Note]]] — <one-line note>
```

## Propagation Pattern

Every meeting ingestion proposes updates to People and Projects notes. This is the **value** — the meeting note is just the artifact.

Format (append-only, never delete):

```markdown
- [YYYY-MM-DD, [[Meeting Note Title]]] <one-line note> — "verbatim quote"
```

Rules:
- Light propagation preferred — durable signals across multiple meetings, not micro-mentions
- Compensation/raise figures stay in meeting notes, not People notes
- Action items with owners become `- [ ]` items in the meeting note, not in the People note

## Executive Follow-Up Rule

After any meeting or interaction with an executive ([[Benji]], Nico, [[Peter Gulliver]]):

1. **Actions / tasks / decisions list** — concrete, owned, with deadlines
2. **Proposed direction** — take a position, don't just summarise
3. **What Great looks like** — what separates Great from Good for this topic
4. **Recommended next steps with rationale** — explain WHY
5. Use 4D and/or What/So What/Now What/When framing

This applies to ingested meetings AND any Slack/ad-hoc interaction surfaced during briefs.

## Operational Patterns

### Commitment sweep + auto-draft (proactive, runs daily + on demand)

Triggered by: morning cron, or user asks "what do I owe people" / "sweep"

1. **Scan for open commitments Owen made:**
   - Meeting notes: action items where DRI = [[Me]] that are still `- [ ]`
   - Slack: messages where Owen said "I'll", "I will", "let me", "I owe you", "I need to" — cross-referenced against evidence of completion
   - Gmail: threads where Owen is expected to reply (tagged, unanswered >24h)
   - Calendar: upcoming deadlines from the Decisions log
2. **For each open commitment, auto-research and draft:**
   - Research what's needed (check Slack threads, Notion, Workable, People notes for context)
   - Draft the deliverable: Slack message, email, document, or vault update
   - Label each draft with confidence: "ready to send" vs "needs your input on X"
3. **Present as a batch for review:**
   - Format: `[OVERDUE/DUE TODAY/THIS WEEK] Commitment -> Draft -> [Approve / Edit / Skip]`
   - Drafts use Owen's voice (direct, punchy, no fluff)
   - External sends (Slack, email) require explicit approval per the non-negotiable rules
4. **After Owen reviews:**
   - Approved drafts -> execute (send via Gmail/Slack MCP, or write to vault)
   - Edited drafts -> log the correction (see "Correction logging" below)
   - Skipped items -> carry forward with reason

**Critical rule:** Before flagging something as "not done", search Slack DMs and Gmail for evidence Owen already actioned it. Surfacing completed items as overdue erodes trust.

### Correction logging (how the brain learns)

When Owen edits a draft before approving:
1. Log the original draft and the final version to `/Copilot Rules.md` under `## Draft corrections log`
2. Extract the *pattern* — what was changed and why (tone? wrong audience? missing context? over-hedged?)
3. After 3+ similar corrections, promote to a standing rule (e.g. "don't open Slack messages with 'Hi team' — Owen goes straight to the point")
4. Periodically consolidate: merge specific corrections into general rules, archive the specifics

This is how the brain stops repeating the same mistakes and learns Owen's voice, judgment, and preferences over time.

### Meeting-prep lookahead (before each call)

Triggered by: user asks "prep me for my next meeting" / "what's on today", or session cron (every 30 min)

1. Pull today's calendar events
2. For each upcoming meeting with attendees:
   - Surface their `/People/` note (last interaction, open items, coaching notes)
   - Surface relevant `/Projects/` note if the meeting touches a tracked project
   - Check Slack for recent messages from/about attendees
   - For interview meetings: pull Metaview conversation + Workable candidate status
3. Output: What/So What/Now What/When for each meeting

### Wednesday hiring radar

Triggered by: user asks "hiring radar" or on Wednesday cadence

1. Pull all open roles from Workable with candidate counts per stage
2. Search Slack `hiring-*` channels for new channels not in Hiring.md canonical list
3. Pull Metaview interview counts by role for the last 7 days
4. Cross-reference with Hiring.md critical-path items
5. Output: RAG board (Red/Amber/Green per role), stale pipelines, suggested actions
6. Format: What/So What/Now What/When

### Friday weekly reflection

Triggered by: user asks "weekly reflection" or on Friday cadence

1. Pull this week's calendar events to reconstruct the week
2. Read all meeting notes from `/Meetings/` this week
3. Surface decisions from `/Decisions/` whose `review_date` falls this week
4. Check Knowledge note candidates flagged but not promoted
5. Output: Weekly template (What/So What/Now What/When + decision reviews + calibration)

## Operating Cadence

| Cadence | What |
|---------|------|
| **Daily** | 8am: ingest yesterday's transcripts + morning brief + commitment sweep. Before each call: meeting-prep lookahead. |
| **Wednesday** | Hiring radar across open reqs (Workable + Metaview + Slack). |
| **Friday** | Weekly reflection: review decisions due, score predictions, promote Knowledge notes, run consolidation pass. |
| **Monthly** | Full memory consolidation + "State of People" brief. Archive completed decisions, mark closed projects, merge redundant People notes. |

## Automation

### System cron (permanent, zero tokens — survives restarts)

```
0 8 * * 1-5  ~/.claude/skills/pull-gdrive-transcripts/scripts/pull-gdrive-transcripts yesterday -o /tmp/transcripts
```

Every weekday at 8am, pulls yesterday's Google Drive meeting transcripts to `/tmp/transcripts/`. No AI agent involved. Output is normalized transcript artifacts ready for ingestion.

### Session crons (ephemeral — die when Claude Code closes, re-set each session)

These must be re-created at the start of each conversation. They expire after ~3 days.

| Schedule | Pattern |
|----------|---------|
| `*/30 * * * *` | **Meeting-prep lookahead** — calendar check, People/Projects/Metaview/Workable enrichment |
| `3 8 * * 1-5` | **Daily ingest** — pull-gdrive-transcripts yesterday + ingest-meeting |
| `17 8 * * 1-5` | **Commitment sweep + auto-draft** — scan Slack/Gmail/meeting notes for things Owen owes, draft responses |
| `7 8 * * 3` | **Wednesday hiring radar** — Workable pipeline + Metaview + Slack hiring channels |
| `13 8 * * 5` | **Friday weekly reflection** — decision review + prediction scoring + Knowledge promotion |

### Daily workflow (human-initiated)

1. **Transcripts arrive automatically** at 8am via system cron
2. Owen starts Claude Code: `"ingest yesterday's transcripts"` -> agent reads artifacts from `/tmp/transcripts/`, distills, resolves entities, presents approval gate, writes
3. Optionally: `"morning brief on Hiring"` -> agent reads project note + Slack + vault -> commits to trajectory bar -> saves brief + updates critical-path
4. Commitment sweep runs automatically at 8:17am, or on demand ("what do I owe people")

### What is NOT automated

- Meeting note ingestion (requires approval gate — by design)
- Slack posting (morning briefs include a pasteable summary but posting is manual)
- Project note bar/framework changes (user owns the quality definitions)
- Entity resolution ambiguities (batched for user confirmation)
- Knowledge note promotion (flagged during ingest, promoted during weekly review)
- External actions (push, Slack post, Notion edit, Gmail send) — all require explicit confirmation

## Memory Hygiene

### Temporal invalidation
When a durable fact changes (role, comp band, project trajectory, relationship status):
1. Write the new fact
2. Mark the old one superseded — don't just append as if both are current
3. If the old fact appears in a brief or active context, correct it in the next output

Stale truth confidently cited is worse than no truth at all.

### Knowledge promotion
During weekly review, promote 1-3 claim-shaped Knowledge notes from the candidates flagged during meeting ingestion. Title = a claim ("Single-assessor hires correlate with fast rejections at final stage"), not a topic ("Hiring").

### Consolidation (monthly)
Review the vault for bloat — archive completed decisions, mark closed projects, merge redundant People notes. Keep the graph lean.

## Skills Reference

All skills live in `/Users/owen.fleming/dev/nala-brain/skills/` and are symlinked into `.claude/skills/`. They are shared across the team — edit only via PR in the nala-brain repo, never locally.

### Transcript producers (user-level, `~/.claude/skills/`)

| Skill | Source | Technology | Token cost |
|-------|--------|------------|------------|
| `pull-gdrive-transcripts` | Google Drive (Gemini notes, Meet recordings) | Bash script + rclone + pandoc | Zero |
| `pull-notion-transcripts` | Notion AI Meeting Notes | Agent-mediated (Notion MCP) | Normal |

Both emit the same normalized transcript contract. The gdrive producer also has a standalone bash script at `~/.claude/skills/pull-gdrive-transcripts/scripts/pull-gdrive-transcripts` that runs without any AI agent (zero tokens).

**Date specs for gdrive:** `today`, `yesterday`, `this-week`, `last-week`, `last-7`, `YYYY-MM-DD`, `YYYY-MM-DD..YYYY-MM-DD`.

### Transcript consumer (vault-level)

| Skill | Purpose |
|-------|---------|
| `ingest-meeting` | Distills normalized transcript artifact -> meeting note + propagation |

Workflow: Read artifact -> match entities -> distill (summary, decisions, actions, discussion points, knowledge candidates) -> resolve ambiguities (batched) -> present for approval -> write.

**Bulk ingest:** Read all N artifacts in parallel, distill independently, consolidate into one approval gate. The transcript-as-source-of-truth rule is never relaxed.

### Analysis skills (vault-level)

| Skill | Purpose | Requires |
|-------|---------|----------|
| `morning-brief` | Opinionated project trajectory call (Great/Good/Mediocre/Bad) with Slack deltas | Slack MCP, project note with quality framework |
| `update-project` | Bring a project note current with dated Health + Deltas update | Slack MCP (optional) |
| `daily-pulse` | Cross-team attention digest from standups + Slack | Slack MCP |
| `normalize-meeting` | Clean up legacy/pre-canonical meeting notes | None |

### Setup skills

| Skill | Purpose |
|-------|---------|
| `setup-brain` | First-run personalization: interviews owner, fills CLAUDE.md + Me.md, verifies toolchain |

## MCP Servers

The vault connects to external services via MCP (Model Context Protocol):

| Server | Purpose | Auth |
|--------|---------|------|
| Google Drive | Read meeting transcripts, search files | Cloud integration (claude.ai) |
| Notion | Read meeting notes, search pages | Cloud integration (claude.ai) |
| Slack | Search messages, read channels/threads, search users | Cloud integration (claude.ai) |
| Workable | ATS — roles, candidates, pipeline, scorecards | Cloud integration (claude.ai) |
| Metaview | Interview transcripts, scorecards, structured feedback | Cloud integration (claude.ai) |
| Google Calendar | Schedule, attendees, event details | Cloud integration (claude.ai) |
| Gmail | Email threads, drafts, send confirmation | Cloud integration (claude.ai) |

The `.mcp.json` in the vault root also has local MCP configs (Notion + Slack with `SLACK_MCP_TOKEN`), but the cloud integrations via claude.ai are the primary path.

## Diarization Issues

Google Meet via Gemini has a known limitation: the London office conference room mic ("Twiga - Meeting Room") captures all in-room speakers as a single label. Remote participants are individually attributed.

| Meeting type | In-room (undiarized) | Remote (diarized) |
|-------------|---------------------|-------------------|
| Talent standups | Owen, Ryan, Mark | — |
| Eng leads weekly | Markus, Owen, Ryan | Alessandro, Christos, Edoardo |
| Owen <> Lynette 1:1 | — | Both diarized (separate locations) |

When a transcript has undiarized room speech, meeting notes include a `> [!note] Attribution` callout explaining the limitation.

## Non-Negotiable Rules

These are enforced by the skills and should never be overridden:

1. **Full transcript is mandatory.** The artifact body is the only quotable source. Producer AI summaries are never the source of any claim.
2. **Bulk ingest does not relax the transcript rule.** Read all N artifacts; don't offer "summary-only" as a lighter alternative.
3. **Approval gate before writes.** Every batch of vault mutations is preceded by explicit user approval. No silent writes.
4. **Meeting note is the artifact; propagation is the value.** A meeting that doesn't update People/Projects notes hasn't been fully ingested.
5. **Decision sources are <=15 words, verbatim from the transcript.**
6. **Entity ambiguities are batched, never auto-picked.**
7. **Compensation figures stay in meeting notes, not People notes.**
8. **External actions (push, Slack post, Notion edit) require explicit confirmation.**
9. **This vault is private.** Notes never go into the shared nala-brain repo.
10. **Shared skills are edited only via PR in nala-brain**, never locally.
11. **Before flagging something as "not done", search Slack DMs and Gmail for evidence Owen already actioned it.** Surfacing completed items as overdue erodes trust.
12. **Read `/Copilot Rules.md` at the start of every session.** It contains persistent corrections that override defaults.

## File Layout Summary

```
/Users/owen.fleming/dev/my-brain/          <-- Vault root (private git repo)
|-- CLAUDE.md                               <-- Agent instructions (personalized)
|-- SYSTEM.md                               <-- This file
|-- Copilot Rules.md                        <-- Persistent corrections + voice + heuristics
|-- .mcp.json                               <-- MCP server configs
|-- .claude/
|   |-- settings.json                       <-- Permissions & allowed tools
|   +-- skills/                             <-- Symlinks -> nala-brain/skills/
|       |-- ingest-meeting -> ...
|       |-- morning-brief -> ...
|       |-- normalize-meeting -> ...
|       |-- update-project -> ...
|       |-- setup-brain -> ...
|       +-- daily-pulse -> ...
|-- Meetings/NALA/                          <-- Distilled meeting notes (4 currently)
|-- People/                                 <-- Entity notes (16 currently)
|   |-- Me.md                               <-- Self-note (alias source)
|   |-- Lynnette Mutugi.md
|   |-- Benji.md
|   |-- Chidi.md                            <-- Added today (Chi alias)
|   +-- ...
|-- Projects/NALA/                          <-- Project notes (3 currently)
|   |-- Hiring.md
|   |-- EU UK Launch.md
|   +-- Earn Your Spot.md
|-- Decisions/                              <-- Decision journal (1 currently)
|   +-- 2026-07-02 - Disqualify Himanshu Roy from GHoC.md
|-- Knowledge/                              <-- Atomic concept notes (3 currently)
|   |-- Restricting hiring geography tanks top-of-funnel.md
|   |-- Decoupling performance scoring from compensation prevents gaming.md
|   +-- Parallel regulatory tracks hedge risk but double engineering surface area.md
|-- Briefs/                                 <-- Morning brief snapshots (1 currently)
|   +-- 2026-07-02 - Hiring.md
|-- Templates/                              <-- Note templates
|   |-- meeting.md
|   |-- Decision.md
|   |-- Daily.md
|   |-- Weekly.md
|   |-- Article.md, Post.md, Video.md
|-- Daily/ Weekly/ Inbox/ Archive/          <-- Date-rolled + intake folders
+-- .git/                                   <-- Private version control

/Users/owen.fleming/dev/nala-brain/         <-- Shared skill repo (team)
|-- skills/                                 <-- Canonical skill definitions
|-- vault-template/                         <-- Scaffold template
|-- docs/                                   <-- Contracts & architecture
|-- scripts/                                <-- init-brain, init-team-brain
+-- test/                                   <-- Fixtures & validation

~/.claude/skills/                           <-- User-level skills
|-- pull-gdrive-transcripts/
|   +-- scripts/
|       |-- pull-gdrive-transcripts         <-- Zero-token bash script
|       +-- setup                           <-- One-time rclone/pandoc bootstrap
+-- pull-notion-transcripts/
```

## Current State (as of 2026-07-02)

- **16 People notes** — Owen (self), 8 from setup (direct reports + key peers), 6 from first ingest (eng leads + CEO), + Chidi (added today, "Chi" alias resolved from eng leads weekly)
- **4 Meeting notes** — 3 from Mon Jun 29 (People Ops Check-in, Talent Kick-off, Eng Leads Weekly), 1 from Thu Jul 2 (Owen Lynette 1:1)
- **3 Project notes** — Hiring (Good), EU UK Launch (Mediocre), Earn Your Spot (Good)
- **1 Decision** — Disqualify Himanshu Roy from GHoC (85% confidence, review date 2026-08-01)
- **3 Knowledge notes** — promoted today (hiring geography, performance scoring, regulatory tracks)
- **1 Brief** — Hiring 2026-07-02
- **System cron active** — weekday 8am transcript pulls (permanent)
- **Session crons defined** — daily ingest, commitment sweep, meeting-prep (30min), Wed hiring radar, Fri weekly reflection (ephemeral, re-set each session)
- **All MCP servers connected** — Drive, Notion, Slack, Workable, Metaview, Calendar, Gmail (cloud integrations)
- **rclone + pandoc installed** — `~/.local/bin/` (no Homebrew, no sudo)
- **Copilot Rules active** — 7 corrections logged, 6 decision heuristics, voice guidance established, draft corrections log initialized (no corrections yet)

## What Was Built Today (2026-07-02)

This vault went from empty scaffold to operational second brain in one session, across three phases:

### Phase A — Decision practice + frameworks + learning loop
- Created `/Decisions/` folder and `/Templates/Decision.md` (4D + prediction + confidence + review date)
- Added NALA values as design spec to CLAUDE.md (not just values — operating rules derived from them)
- Added operating frameworks to CLAUDE.md: 4D (Data/Decision/DRI/Deadline) and What/So What/Now What/When
- Added executive follow-up rule (triggered after Benji/Nico/Peter meetings)
- Created `/Copilot Rules.md` — persistent corrections, decision heuristics, voice guidance, draft corrections log
- Added memory hygiene rules (temporal invalidation, Knowledge promotion cadence)
- Added operating cadence (daily/Wed/Fri/monthly)
- Updated Weekly template with reflection structure

### Phase B — Connected source systems + operational patterns
- Connected Workable ATS (nalamoney, 8 open roles with shortcodes)
- Connected Metaview (NALA workspace, admin access, participant_id mapped)
- Connected Google Calendar (meeting-prep, exec meeting detection)
- Connected Gmail (commitment verification, follow-up drafts)
- Defined operational patterns: commitment sweep + auto-draft, meeting-prep lookahead, Wednesday hiring radar, Friday weekly reflection
- Added correction logging pattern (how the brain learns from Owen's edits)

### Phase C — Session crons + quality bar
- Defined session crons: daily ingest (8:03am), commitment sweep (8:17am), meeting-prep (every 30min), Wed hiring radar (8:07am), Fri reflection (8:13am)
- Documented that session crons are ephemeral (die when Claude Code closes) vs system cron (permanent)
- Established the brain's own quality bar (Great/Good/Mediocre/Bad)
- Promoted 3 Knowledge notes from meeting ingestion candidates
- Created Chidi People note (resolved "Chi" alias from eng leads weekly)
- Logged first Decision (Himanshu Roy disqualification — 85% confidence, review 2026-08-01)
- Logged 7 corrections to Copilot Rules from the day's work
