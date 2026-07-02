# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault used as a personal knowledge / "second brain" by Owen Fleming (Head of People at [[NALA]]). It is git-tracked (`.git` at the vault root), but it's a notes corpus — not a software project. There is **no build, no test suite, no linter**. Work here is reading, distilling, and writing Markdown files.

The vault's value is in the graph between notes — meeting notes that link to people, people who link to projects, knowledge notes that cite meeting moments. A change to one node almost always implies propagation across several others.

## Layout

```
/Meetings/<Company>/YYYY-MM-DD - Title.md     # primary corpus; organized by employer subfolder
/People/<Name>.md                              # one note per person; aliases in YAML frontmatter
/Projects/<Company>/<topic>.md                 # projects, with company subfolders
/Knowledge/                                    # atomic, claim-shaped concept notes ("X causes Y because Z")
/Daily/  /Weekly/  /Inbox/  /Archive/          # date-rolled + intake folders
/Briefs/                                       # morning-brief snapshots
/Templates/                                    # Daily.md, Weekly.md, meeting.md templates
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
