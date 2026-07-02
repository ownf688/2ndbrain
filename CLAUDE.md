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

### Windmill (NALA workspace — admin access)
- **What:** Performance management platform — feedback, 1:1s, pulse surveys, weekly recaps, performance review cycles, org-wide stats
- **Access level:** Admin. Owen can see **all 248 employees** org-wide, not just his direct org. No `my-org` preset needed for cross-org queries.
- **When to use:**
  - **Wednesday Manager Health Pulse (EYS):** `stats_query` for `feedback-given` + `one-on-one-meetings` per manager over last 30 days; `feedback_query` to check quality/recency of feedback
  - **Friday Performance Risk Early Warning:** managers with zero `feedback-given` in 4+ weeks; stale 1:1 prep tasks
  - **Meeting-prep (before 1:1s with directs):** pull recent Windmill feedback about the person + their weekly recaps
  - **People note enrichment:** on-demand feedback history for EYS Evidence sections
  - **Pulse monitoring:** check response rates and results for NALA Feedback Loops (12-week cycle) and weekly kick-offs
  - **Recognition (EYS):** `feedback_create` with shoutout to amplify values-in-action moments
- **Key employee IDs (People team + frequent contacts):**
  - Owen Fleming: `fsx5cs0ee67cgcmluemym6k8`
  - Peter Gulliver (CFO): `vu1zaj7ss6pdzhievxalnmjr`
  - Lynnette Mutugi: `mvhx4jnxfv8iypvm03n0kfbi`
  - Ryan Bolton-Smith: `c82bney6up4kwqzdxv1nmnbe`
  - Sidi Ngade: `p2efd2ldv4bbl6mb1852jxpu`
  - Mark McCracken: `xbkzey8z16ewfqbzv3vaf2yv`
  - Oli Woolf: `zsre1u0k5nlmb02jgwrg5sh0`
  - Jerry Chen: `e6t6aa9lo9doul2syr0ghgbf`
  - Jocyline Owano: `td30uek3ilznqd4trd225ptr`
  - Benjamin Fernandes (CEO): `gy4yo2xkxhamd46u8qgoga07`
  - Nicolai Eddy (COO): `tehctkbuqsrr6su7ub2lir14`
  - Markus Seebacher (HoE): `ez9e8p5fzwio58z4h0fietwi`
  - Joshua Black (HoO): `cthvgnluk4aj26c8t98chu7p`
  - Christos Petropoulos: `qnsl87qoztkq8xnq2beojoxi`
  - Edoardo Foco: `zj4do0xv4eag5x1qdrf9kevc`
  - Alessandro Colaneri: `f4tt2qq5g4sazs3mwca9j9cy`
  - Chidi Onuekwusi: `ziu179q3ny2dzsjbv10j6n4i`
- **Active pulses (recurring):**
  - NALA Feedback Loop x5 (Eng & Prod, Operations, Finance/Treasury/People/IT/Data, Legal & Compliance, Revenue, Leadership & Exec) — 12-week cycle, last ran Jun 29
  - Weekly People Ops Kick-off / Weekly Recruitment Kick-off — manual, paused since Apr 20
  - Performance Review Feedback — one-time, completed May 25
- **Stats available for any employee:** `feedback-given`, `feedback-received`, `one-on-one-meetings`, `one-on-one-agenda-edits`, `proactive-feedback-given`, `shoutouts-sent`, `slack-messages-sent`, `windmill-active-days`, plus code/Jira/Linear/meetings metrics
- **1:1 pairs tracked:** Owen has 40+ pairs. Prep enabled for Lynnette and Ryan.
- **Performance review cycles:** 1 completed — Spring Performance Review (Sep 2025 - Feb 2026)

## Earn Your Spot (EYS) — culture engine rules

EYS is not a document — it's a living system embedded in how the brain processes every meeting, every interaction, every hire. These rules make it real.

### 1. Values-in-action evidence engine (during every meeting ingestion)
When distilling meeting notes, add an extra pass: scan for moments where NALA values were **demonstrated or violated**. Flag each with the value and a verbatim quote. Append to the person's `## EYS Evidence` section in their People note.

Format:
```
### Performance (skills + impact)
- [YYYY-MM-DD, [[Meeting]]] <what they did> — evidence of <skill/impact>

### Values
- [YYYY-MM-DD, [[Meeting]]] Positive: <behavior> — *<Value>*
- [YYYY-MM-DD, [[Meeting]]] Watch: <behavior> — *<Value> gap*
```

Values to flag against:
- **Customers First** — candidate/employee experience, responsiveness, proactive communication
- **Play to Win** — ownership, accountability, driving outcomes, not letting things slide
- **Speed Wins** — bias to action, async-first, opinionated calls, shipping
- **Understand Why** — root-cause thinking, evidence-based reasoning, learning from failure

Don't force it. Only flag genuine signals — not every comment maps to a value. "Watch" items are coaching prompts, not accusations.

### 2. Manager accountability pulse (Wednesday, alongside hiring radar)
Every Wednesday, surface a "Manager Health" check:
- Pull Windmill `stats_query` for `feedback-given` and `one-on-one-meetings` per manager over the last 30 days (admin access = org-wide, no export needed)
- Pull Windmill `feedback_query` for recent feedback by each manager to check quality, not just quantity
- Cross-reference Calendar for 1:1 frequency per manager-report pair
- Check People notes: who hasn't had an interaction logged in 3+ weeks?
- Check meeting notes: which managers have open action items assigned to their reports that haven't closed?

Output: RAG per manager. Red = no feedback + cancelled 1:1s + stale interactions. Green = consistent feedback rhythm + active coaching evidence.

### 3. Performance risk early warning (Friday reflection add-on)
During the Friday reflection, scan for leading indicators across this week's meeting notes and Slack:
- Same person named as blocker in 2+ meetings with no ownership taken
- Manager hasn't given Windmill feedback in 4+ weeks (check via `stats_query` with `feedback-given`, aggregateBy `week`)
- 1:1s cancelled 2+ weeks running (from Calendar)
- Action items assigned but repeatedly not closed
- Defensive communication patterns noted across multiple notes (like Sidi's)
- Person mentioned only in negative/concern contexts, never in positive

Surface as: "Performance signals to investigate" — not conclusions. The brain flags, Owen investigates.

### 4. "Cost of doing nothing" evidence (accumulating, surfaced monthly)
Track and quantify the cost of mediocre performance across Owen's domain:
- **Hiring:** roles open 60+ days, candidates ghosted (applications unreviewed from Workable), time-to-response on scheduling requests
- **People:** overdue probation reviews, stale 1:1s, unactioned performance concerns carried for 3+ meetings
- **Ops:** same person as a bottleneck across multiple project critical-paths

Accumulate in a `/Briefs/Cost of Mediocrity/` rolling note. Surface the strongest data points in Owen's monthly "State of People" brief and in exec prep. This is the 4D *Data* that makes the case for EYS as a CEO initiative.

### 5. Hiring as culture carrier (during interview ingestion)
When ingesting interview meetings (from Metaview or transcripts):
- Score the candidate's responses against NALA values — not just competence
- Flag value-positive and value-concerning signals with verbatim quotes
- Add a `## Values alignment` section to the interview meeting note, after Key Discussion Points

Format:
```
## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Positive | "I always think about the candidate experience first" |
| Play to Win | Neutral | No strong signal either way |
| Understand Why | Positive | Asked probing questions about NALA's regulatory strategy |
```

This means the hiring process embodies EYS before someone even joins — and gives calibration-quality evidence from day zero.

### 6. Recognition amplification (during every meeting ingestion)
When the brain detects positive signals during ingestion — someone shipping under pressure, a values moment, exceptional ownership — auto-draft a recognition post for Owen to approve:
- **Windmill Shoutout** (if the evidence is specific enough for public praise)
- **Slack recognition** (for team-facing channels)
- **People note highlight** (always — this is the living scorecard)

Present alongside the meeting note approval gate: "Recognition draft: [Approve / Edit / Skip]". Make recognition a system output, not something Owen has to remember.

### 7. Living scorecard (People notes — EYS Evidence section)
Every NALA employee's People note has a `## EYS Evidence` section with two subsections: `### Performance (skills + impact)` and `### Values`. This accumulates throughout the quarter from:
- Meeting ingestion (values-in-action engine)
- Interview ingestion (for new hires, from day zero)
- Recognition events
- Coaching observations (from 1:1 notes)
- Performance risk signals

When review time comes, the packet is already built. Managers don't write from a blank page; they curate from months of accumulated evidence. Owen and Lynnette act as stewards of evidence quality.

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

### Wednesday hiring + manager health radar
Triggered by: user asks "hiring radar" or on Wednesday cadence
**Part 1 — Hiring radar:**
1. Pull all open roles from Workable with candidate counts per stage
2. Search Slack `hiring-*` channels for new channels not in Hiring.md canonical list
3. Pull Metaview interview counts by role for the last 7 days
4. Cross-reference with Hiring.md critical-path items
5. Output: RAG board (Red/Amber/Green per role), stale pipelines, suggested actions

**Part 2 — Manager health pulse (EYS):**
1. Check People notes: which reports haven't had an interaction logged in 3+ weeks?
2. Check Calendar: which 1:1s were cancelled or didn't happen this week?
3. Check EYS Evidence sections: which managers have zero values/performance entries in the last month?
4. Output: RAG per manager with specific coaching prompts
5. Format: What/So What/Now What/When

### Friday weekly reflection
Triggered by: user asks "weekly reflection" or on Friday cadence
1. Pull this week's calendar events to reconstruct the week
2. Read all meeting notes from `/Meetings/` this week
3. Surface decisions from `/Decisions/` whose `review_date` falls this week
4. Check Knowledge note candidates flagged but not promoted
5. **Performance risk early warning (EYS):** scan for leading indicators — blockers without owners, stale 1:1s, defensive patterns, unresolved action items
6. **Recognition check:** did anything positive happen this week that deserves a Shoutout or recognition post? Draft if yes.
7. Output: Weekly template (What/So What/Now What/When + decision reviews + calibration + performance signals + recognition drafts)

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

- **Daily** — 8am: ingest yesterday's transcripts (with values-in-action flagging + recognition drafts) + morning brief + commitment sweep. Before each call: meeting-prep lookahead.
- **Wednesday** — Hiring radar + Manager health pulse (EYS). RAG per role AND per manager.
- **Friday** — Weekly reflection (What/So What/Now What/When): review decisions due, score predictions, promote Knowledge notes, performance risk early warning, recognition check.
- **Monthly** — Full memory consolidation + "State of People" brief + Cost of Mediocrity evidence summary for exec use.

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
