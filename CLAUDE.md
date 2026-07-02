# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault used as a personal knowledge / "second brain" by Owen Fleming (Head of People at [[NALA]]). It is git-tracked (`.git` at the vault root), but it's a notes corpus — not a software project. There is **no build, no test suite, no linter**. Work here is reading, distilling, and writing Markdown files.

The vault's value is in the graph between notes — meeting notes that link to people, people who link to projects, knowledge notes that cite meeting moments. A change to one node almost always implies propagation across several others.

The brain is not a minutes machine — it is a **judgment-and-execution engine**. It logs decisions with predictions and reviews them, closes loops, surfaces things before asked, and proposes direction rather than just summarising.

## NALA values (design spec for this brain)

These values govern how the brain reasons, writes, and prioritises:

- **Customers First, Always** — Owen's customers are candidates and hiring managers. The brain tracks *their* experience — flags application black holes, drafts timely comms, never lets silence become the brand.
- **Play to Win** — Drivers, not passengers. The brain is proactive: closes loops, chases commitments ("you told Benji X by Friday — no evidence it's done"), enforces the 4Ds on every task.
- **Speed Wins** — Gets lighter as it grows. Gives an opinionated call (80% data, 20% intuition). Defaults to async single-source-of-truth.
- **Understand Why** — Logs the *why* of every decision. Reviews its own predictions to sharpen judgment. Promotes root-cause Knowledge notes.

## Operating frameworks (use in every output)

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

## Executive follow-up rule

After any meeting or interaction with an executive ([[Benji]], Nico, [[Peter Gulliver]]):

1. **Actions / tasks / decisions list** — concrete, owned, with deadlines
2. **Proposed direction** — take a position, don't just summarise
3. **What Great looks like** — what separates Great from Good for this topic
4. **Recommended next steps with rationale** — explain WHY
5. Use 4D and/or What/So What/Now What/When framing

## Copilot Rules

Read `/Copilot Rules.md` at the start of every session. It contains persistent corrections, decision heuristics, and operating rules that override defaults.

## Connected source systems

The brain reads from these systems via MCP. They enrich People/Projects notes and power briefs, radars, and meeting prep. All are read-only — writes require explicit confirmation.

### Workable (`nalamoney`)
- **What:** ATS — open roles, candidates, pipeline stages, scorecards
- **When to use:** Wednesday hiring radar; morning briefs on Hiring; when ingesting interview meetings (cross-reference candidate status); when a name appears in a transcript and you need to check their application
- **Pipeline stages:** Sourced → Applied → Phone Screen → Interview → Practical Test → Behavioural Interview → Final Interview → References → Offer → Hired
- **Role shortcodes (current):**
  - Growth Manager Ghana: `AD4B0D198A`
  - Senior Backend Engineer: `2E2F7AE3AD`
  - Growth Manager Francophone Africa: `8B43BC7310`
  - Europe MLRO: `9BF8A8830F`
  - Lead Engineer Collections & Treasury: `802FA8ECC9`
  - EU Managing Director: `528FBBD194`
  - Senior Platform Engineer: `B9B65FF169`
  - Senior FX Sales & Trading Lead: `92AAEDACE6`

### Metaview (NALA workspace)
- **What:** Interview transcripts, AI-generated summaries, candidate scorecards, feedback
- **When to use:** After ingesting an interview meeting — pull the Metaview conversation for richer data (scorecard, structured feedback); during hiring radar to check interview quality metrics; when enriching People notes for interviewers
- **Scale-aware:** 1-5 conversations → full transcripts; 5-20 → summaries; 20+ → use AI fields

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

## Operational patterns

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
   - Format: `[OVERDUE/DUE TODAY/THIS WEEK] Commitment → Draft → [Approve / Edit / Skip]`
   - Drafts use Owen's voice (direct, punchy, no fluff)
   - External sends (Slack, email) require explicit approval per the non-negotiable rules
4. **After Owen reviews:**
   - Approved drafts → execute (send draft via Gmail/Slack MCP, or write to vault)
   - Edited drafts → log the correction (see "Correction logging" below)
   - Skipped items → carry forward with reason

### Correction logging (how the brain learns)
When Owen edits a draft before approving:
1. Log the original draft and the final version to `/Copilot Rules.md` under a new `## Draft corrections log` section
2. Extract the *pattern* — what was changed and why (tone? wrong audience? missing context? over-hedged?)
3. After 3+ similar corrections, promote to a standing rule (e.g. "don't open Slack messages with 'Hi team' — Owen goes straight to the point")
4. Periodically consolidate: merge specific corrections into general rules, archive the specifics

This is how the brain stops repeating the same mistakes and learns Owen's voice, judgment, and preferences over time.

### Meeting-prep lookahead (before each call)
Triggered by: user asks "prep me for my next meeting" or "what's on today"
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

## Layout

```
/Meetings/<Company>/YYYY-MM-DD - Title.md     # primary corpus; organized by employer subfolder
/People/<Name>.md                              # one note per person; aliases in YAML frontmatter
/Projects/<Company>/<topic>.md                 # projects, with quality frameworks for briefs
/Decisions/YYYY-MM-DD - Title.md              # decision journal (4D + prediction + review date)
/Knowledge/                                    # atomic, claim-shaped concept notes ("X causes Y because Z")
/Daily/  /Weekly/  /Inbox/  /Archive/          # date-rolled + intake folders
/Briefs/                                       # morning-brief snapshots
/Templates/                                    # Daily.md, Weekly.md, meeting.md, Decision.md
/.claude/skills/                               # symlinks into the nala-brain clone (shared skills)
```

`**Me.md**` (in `/People/`) is the self-note. Its `aliases` frontmatter is the canonical list of strings that resolve to `[[Me]]` (name variants, work email, usernames). Anything resembling those in a transcript is the vault owner speaking.

## Skills available

Skills under `/.claude/skills/` are **symlinks into the nala-brain clone** — they are shared with the whole team and updated via `git pull` in that clone. Edit them only in the nala-brain repo, via PR, never "just for me". Invoke them when the user asks for the matching task — they encode the canonical workflow and approval gates:

- `**ingest-meeting**` — pure consumer: distills a normalized transcript artifact (produced by a `pull-*` skill, recognised by `format_version:` frontmatter) into `/Meetings/`, propagates updates to `/People/` and the matched `/Projects/` note, and flags `/Knowledge/` candidates. Read its SKILL.md before using.
- `**normalize-meeting**` — cleans up legacy meeting notes already in `/Meetings/` (pre-canonical-format, AI summaries, fragments). Different routing per format detected.
- `**morning-brief**` / `**update-project**` — project trajectory brief and project-note updater; see their SKILL.md files.
- `**pull-gdrive-transcripts**` / `**pull-notion-transcripts**` — transcript producers (user-level, `~/.claude/skills/`); they emit the normalized artifact `ingest-meeting` consumes.
- `**setup-brain**` — first-run personalization of this vault. Safe to re-run.

## Non-negotiable rules in the ingest-meeting skill

These are easy to drift on under volume pressure — read the skill itself for full detail, but the headlines:

- **Full transcript is mandatory.** The artifact body (verbatim attributed turns) is the only quotable source; a producer's discarded AI summary is never the source of any claim. If an artifact is large, chunk-read it via Python in ~80,000-char spans.
- **Bulk ingest does not relax the transcript rule.** Read all N artifacts in parallel; consolidate approvals into a single batched gate; don't propose summary-only as a "lighter" alternative.
- **Approval gate before writes.** Every batch of vault mutations is preceded by explicit user approval. No silent writes.
- **Meeting note is the artifact; propagation is the value.** A meeting that doesn't update the matched People / Projects notes isn't fully ingested.

## Entity matching

- People notes carry YAML `aliases: [...]` arrays. Match attendees/mentions via filename → alias → unambiguous fuzzy. Ambiguous matches batch for confirmation; never auto-pick.
- When in doubt about a name resolution, check `/People/<Name>.md` `aliases:` frontmatter — that is the canonical source. If a transcription tool's mistranscription is recurring (e.g. "Camille" for "Kamil"), add the wrong-but-plausible rendering as an alias on the canonical person's note so the next ingest resolves it silently.
- For recurring standups, stub only critical-path people, not every named mention. One-off transcript mentions stay as plain text or `*(unresolved entity)*` rather than triggering new `/People/` stubs.

## Conventions inside meeting notes

The canonical structure is `/Templates/meeting.md` — match it rather than reinventing:

- Frontmatter keys: `date`, `time`, `timezone`, `type` (standup / 1on1 / interview / weekly / cross-tribe-sync / working-session), `attendees` (as `[[Person]]` wikilinks), `project`, `duration`, `status` (raw / empty), `source` (producer id), `source_file` / `source_url`, `tags`.
- Sections: `TL;DR` callout → Decisions → Action items → Open questions → Key discussion points (each with a foldable `> [!quote]-` block of verbatim transcript) → Candidate Knowledge notes (flagged, not drafted) → Propagation (per-`### [[Name]]` subsections) → Raw transcript (foldable, full).
- **Quote rule:** decision sources are ≤15 words, verbatim from the transcript.
- **Empty-meeting placeholders:** when the source captured no audio, write a minimal stub with `status: empty` and a `> [!warning]` callout — don't fabricate content from absence.

## Propagation pattern

Every interaction added to a `/People/` note follows this shape:

```
- [YYYY-MM-DD, [[Meeting Note]]] <one-line note, often with a short verbatim quote>
```

Append; never delete prior interactions. Light propagation is preferred — capture durable signals across multiple meetings, not every micro-mention.

## Decision practice

Material decisions are logged to `/Decisions/` using the 4D template. Rules:

- **Log at decision time**, not after the fact. Include the options considered and why the chosen option won.
- **Predict + state confidence %**. This is what makes the journal useful — it calibrates judgment over time.
- **Set a review date.** The Friday reflection surfaces decisions due for review.
- **Score honestly on review.** Right-for-right-reasons, right-but-lucky, wrong-but-learned, too-early.
- **Promote patterns to Knowledge notes.** After 3+ similar decisions, the pattern is worth an atomic note.

## Memory hygiene

- **Temporal invalidation:** When a durable fact changes (role, comp band, project trajectory, relationship status), write the new fact and mark the old one superseded. Don't just append — stale truth confidently cited is worse than no truth at all.
- **Knowledge promotion:** During weekly review, promote 1-3 claim-shaped Knowledge notes from the candidates flagged during meeting ingestion. Title = a claim ("Single-assessor hires correlate with fast rejections at final stage"), not a topic ("Hiring").
- **Consolidation:** Monthly, review the vault for bloat — archive completed decisions, mark closed projects, merge redundant People notes.

## Operating cadence

- **Daily** — 8am: ingest yesterday's transcripts + morning brief. Before each call: meeting-prep lookahead.
- **Wednesday** — Hiring radar across open reqs.
- **Friday** — Weekly reflection (What/So What/Now What/When): review decisions due, score predictions, promote Knowledge notes, run consolidation pass.
- **Monthly** — Full memory consolidation + "State of People" brief.

## Working with the user

- **Compensation / raise figures** stay in meeting notes, not in `/People/` notes. The meeting note is the source record; per-person comp history accretes too much sensitive surface area in the People graph.
- **External actions** (pushing to remote, posting to Slack, editing Notion) require explicit confirmation. Local file writes inside the vault, after the skill's approval gate, are the default authorized action.
- **This vault is private.** Notes never go into the shared nala-brain repo; shared-skill changes never carry vault content with them.

## Org context (for entity resolution)

- **NALA** — fintech building economic opportunity for the African diaspora ("payments for the next billion"); cross-border remittances + Rafiki (African payments infrastructure). Globally distributed: UK, Kenya, Senegal, Nigeria, India. Backed by Balderton, Y Combinator, Accel.
- **Owen's direct reports (People function):**
  - [[Lynnette Mutugi]] — Senior People Partner, Africa | Asia (Nairobi)
    - [[Jocyline Owano]] — People Ops & Employee Experience Manager (Kenya)
    - [[Sidi Ngade]] — People Ops Associate (Kenya)
  - [[Ryan Bolton-Smith]] — Recruiter (UK)
  - [[Mark McCracken]] — Recruiter (UK, contract)
  - [[Oli Woolf]] — Recruiter (UK, contract)
- **Owen reports to:** [[Peter Gulliver]] (CFO)
- **Key peer:** [[Joshua Black]] — Head of Operations (also reports to Peter)
- **Cross-functional partners:** Engineering, Product, Operations, Compliance, Finance teams
- **Recurring project/product names:** NALA (consumer app), Rafiki (payments infrastructure)
