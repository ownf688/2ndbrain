# How This Second Brain Works

> A comprehensive technical overview for AI agents operating on this vault.

## What this is

This is a personal Obsidian vault functioning as a "second brain" for Owen Fleming, Head of People at NALA (a fintech building cross-border remittances for the African diaspora). It is not a software project — it is a **Markdown knowledge graph** where meetings feed people notes, people notes feed project notes, and project notes feed daily briefs. The graph is the product.

The vault is operated by AI agents (primarily Claude Code) using a set of shared skills. The human (Owen) approves all writes, resolves ambiguities, and makes judgment calls. The AI does acquisition, distillation, entity resolution, propagation, and trajectory analysis.

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        SOURCES                                   │
│  Google Drive (Gemini notes) │ Notion │ Slack │ Manual paste     │
└──────────────┬───────────────┴────────┴───────┴──────────────────┘
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
┌──────────────────────────────────────────────────────────────────┐
│                     OBSIDIAN VAULT                                │
│                                                                   │
│  /Meetings/NALA/    ←── distilled meeting notes with raw transcript│
│  /People/           ←── one note per person, interaction log       │
│  /Projects/NALA/    ←── project notes with quality frameworks      │
│  /Knowledge/        ←── atomic claim-shaped concept notes          │
│  /Briefs/           ←── morning brief snapshots                    │
│  /Daily/ /Weekly/   ←── date-rolled journals                       │
│  /Inbox/ /Archive/  ←── intake + cold storage                      │
│  /Templates/        ←── canonical note templates                   │
│                                                                   │
└──────────────────────────────────────────────────────────────────┘
           │
           ▼
┌──────────────────────────────┐
│     ANALYSIS SKILLS          │
│  morning-brief               │     Reads project + Slack → trajectory call
│  update-project              │     Gathers deltas → health update
│  daily-pulse                 │     Cross-team attention digest
│  normalize-meeting           │     Cleans legacy meeting notes
└──────────────────────────────┘
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
2. Decisions — each with verbatim source quote (≤15 words)
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

### Knowledge notes (`/Knowledge/`)

Atomic, claim-shaped concept notes ("X causes Y because Z"). Flagged during meeting ingestion but promoted during weekly review, not auto-created.

### Briefs (`/Briefs/YYYY-MM-DD - <Project>.md`)

Morning brief snapshots. Each brief:
- Commits to a trajectory bar (Great/Good/Mediocre/Bad) — no hedging
- Lists deltas since last snapshot with Slack thread references
- Flags stale vault notes
- Surfaces newly discovered Slack channels
- Names open risks
- Suggests one concrete first action
- Includes a Slack-pasteable summary (≤100 words, no framework jargon)

## Entity Resolution

Entity matching is the backbone of the graph. Without it, meetings don't connect to people, and people don't connect to projects.

### Resolution priority

1. **Exact filename match** (case-insensitive): "Lynnette Mutugi" → `People/Lynnette Mutugi.md`
2. **Exact alias match**: "Lynette" → matches `aliases: [..., Lynette]` in `Lynnette Mutugi.md`
3. **Fuzzy first-name match** (only if unambiguous across the vault): "Lynnette" → only one Lynnette exists
4. **Ambiguous** → batch for user confirmation. Never auto-pick.

### Known mistranscription aliases in this vault

| Transcript renders as | Resolves to | Why |
|----------------------|-------------|-----|
| "City" | [[Sidi Ngade]] | Gemini mistranscription of "Sidi" |
| "Lynette" | [[Lynnette Mutugi]] | Alternate spelling |
| "Ollie" | [[Oli Woolf]] | Nickname |
| "Edo" | [[Edoardo Foco]] | Shortened name |
| "Chris" (eng context) | [[Christos Petropoulos]] | Shortened name |
| "AL", "Ali", "Alia" | [[Alessandro Colaneri]] | Shortened name |
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
| `ingest-meeting` | Distills normalized transcript artifact → meeting note + propagation |

Workflow: Read artifact → match entities → distill (summary, decisions, actions, discussion points, knowledge candidates) → resolve ambiguities (batched) → present for approval → write.

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

The `.mcp.json` in the vault root also has local MCP configs (Notion + Slack with `SLACK_MCP_TOKEN`), but the cloud integrations via claude.ai are the primary path.

## Automation

### System cron (permanent, zero tokens)

```
0 8 * * 1-5  ~/.claude/skills/pull-gdrive-transcripts/scripts/pull-gdrive-transcripts yesterday -o /tmp/transcripts
```

Every weekday at 8am, pulls yesterday's Google Drive meeting transcripts to `/tmp/transcripts/`. No AI agent involved. Output is normalized transcript artifacts ready for ingestion.

### Daily workflow (human-initiated)

1. **Transcripts arrive automatically** at 8am via cron
2. Owen starts Claude Code: `"ingest yesterday's transcripts"` → agent reads artifacts from `/tmp/transcripts/`, distills, resolves entities, presents approval gate, writes
3. Optionally: `"morning brief on Hiring"` → agent reads project note + Slack + vault → commits to trajectory bar → saves brief + updates critical-path

### What is NOT automated

- Meeting note ingestion (requires approval gate — by design)
- Slack posting (morning briefs include a pasteable summary but posting is manual)
- Project note bar/framework changes (user owns the quality definitions)
- Entity resolution ambiguities (batched for user confirmation)
- Knowledge note promotion (flagged during ingest, promoted during weekly review)

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
5. **Decision sources are ≤15 words, verbatim from the transcript.**
6. **Entity ambiguities are batched, never auto-picked.**
7. **Compensation figures stay in meeting notes, not People notes.**
8. **External actions (push, Slack post, Notion edit) require explicit confirmation.**
9. **This vault is private.** Notes never go into the shared nala-brain repo.
10. **Shared skills are edited only via PR in nala-brain**, never locally.

## File Layout Summary

```
/Users/owen.fleming/dev/my-brain/          ← Vault root (private git repo)
├── CLAUDE.md                               ← Agent instructions (personalized)
├── SYSTEM.md                               ← This file
├── .mcp.json                               ← MCP server configs
├── .claude/
│   ├── settings.json                       ← Permissions & allowed tools
│   └── skills/                             ← Symlinks → nala-brain/skills/
│       ├── ingest-meeting → ...
│       ├── morning-brief → ...
│       ├── normalize-meeting → ...
│       ├── update-project → ...
│       ├── setup-brain → ...
│       └── daily-pulse → ...
├── Meetings/NALA/                          ← Distilled meeting notes
├── People/                                 ← Entity notes (15 currently)
│   ├── Me.md                               ← Self-note (alias source)
│   ├── Lynnette Mutugi.md
│   ├── Benji.md
│   └── ...
├── Projects/NALA/                          ← Project notes (3 currently)
│   ├── Hiring.md
│   ├── EU UK Launch.md
│   └── Earn Your Spot.md
├── Knowledge/                              ← Atomic concept notes
├── Briefs/                                 ← Morning brief snapshots
├── Templates/                              ← meeting.md, Daily.md, Weekly.md
├── Daily/ Weekly/ Inbox/ Archive/          ← Date-rolled + intake folders
└── .git/                                   ← Private version control

/Users/owen.fleming/dev/nala-brain/         ← Shared skill repo (team)
├── skills/                                 ← Canonical skill definitions
├── vault-template/                         ← Scaffold template
├── docs/                                   ← Contracts & architecture
├── scripts/                                ← init-brain, init-team-brain
└── test/                                   ← Fixtures & validation

~/.claude/skills/                           ← User-level skills
├── pull-gdrive-transcripts/
│   └── scripts/
│       ├── pull-gdrive-transcripts         ← Zero-token bash script
│       └── setup                           ← One-time rclone/pandoc bootstrap
└── pull-notion-transcripts/
```

## Current State (as of 2026-07-02)

- **15 People notes** — Owen (self), 8 from setup (direct reports + key peers), 6 from first ingest (eng leads + CEO)
- **4 Meeting notes** — 3 from Mon Jun 29, 1 from Thu Jul 2
- **3 Project notes** — Hiring (Good), EU UK Launch (Mediocre), Earn Your Spot (Good)
- **1 Brief** — Hiring 2026-07-02
- **System cron active** — weekday 8am transcript pulls
- **All MCP servers connected** — Drive, Notion, Slack (cloud integrations)
- **rclone + pandoc installed** — `~/.local/bin/` (no Homebrew, no sudo)
