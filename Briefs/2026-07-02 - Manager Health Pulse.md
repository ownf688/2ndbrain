---
date: 2026-07-02
type: manager-health-pulse
cadence: wednesday
tags: [brief, eys, manager-health, windmill]
---

# Manager Health Pulse — Wednesday Jul 2, 2026

## What

16 managers tracked org-wide over the last 30 days (Jun 2 - Jul 2). Data from Windmill (feedback-given + 1:1 meeting count), Google Calendar (Owen's 1:1 cadence), and vault People notes (last interaction logged).

## RAG Board

| RAG | Manager | FB Given | 1:1s | Signal |
|-----|---------|----------|------|--------|
| **GREEN** | [[Me]] | 2 | 30 | Only person giving proactive developmental feedback org-wide |
| **GREEN** | [[Alessandro Colaneri]] | 1 | 49 | Strong 1:1 cadence, gave feedback |
| **GREEN** | [[Markus Seebacher]] | 1 | 54 | Strong 1:1 cadence, gave feedback |
| **GREEN** | Patrick Madhere | 1 | 23 | Solid for a shift lead |
| AMBER | [[Joshua Black]] | 0 | 57 | High 1:1 volume but zero formal feedback |
| AMBER | Leo Sgambato | 0 | 53 | Same pattern - lots of meetings, no feedback logged |
| AMBER | Imaad Ahmed | 0 | 112 | Huge 1:1 count, zero feedback. Meeting-heavy, not coaching-heavy? |
| AMBER | [[Peter Gulliver]] | 0 | 38 | Zero feedback. Owen's own 1:1 with Peter was declined Jun 23. |
| AMBER | [[Christos Petropoulos]] | 0 | 36 | Zero feedback despite 36 1:1s |
| AMBER | Nicolai Eddy | 0 | 25 | Zero feedback |
| AMBER | [[Edoardo Foco]] | 0 | 27 | Zero feedback |
| AMBER | [[Lynnette Mutugi]] | 0 | 17 | Zero feedback given (received 1 from [[Sidi Ngade]], solicited by Owen) |
| AMBER | Adriana Kocylo | 0 | 16 | Zero feedback |
| AMBER | Parth Patel | 0 | 13 | Zero feedback |
| AMBER | [[Petros Kyrkilis]] | 0 | 13 | Zero feedback |
| AMBER | [[Benji]] | 0 | 24 | CEO - not expected to use Windmill feedback, but notable |

## So What

**The feedback muscle is dead outside Owen's team.** Only 4 of 16 managers gave any Windmill feedback in 30 days. Owen accounts for 2 of the 9 total entries org-wide. 1:1 meetings are happening (every manager has them), but the formal feedback loop is broken - managers are meeting, not documenting.

This matters because:
- EYS is built on accumulated evidence. No feedback = blank scorecard at review time.
- The Spring Performance Review cycle just finished. If there's no feedback flowing between cycles, the next review starts from zero again.
- **[[Lynnette Mutugi]]** - Owen's direct report and the person responsible for coaching managers on this - has given zero feedback herself in 30 days. Second-order signalling problem: if the People Partner isn't modelling it, why would line managers?

**Owen's own cadence (Calendar):**
- [[Ryan Bolton-Smith]]: 3 weekly 1:1s held (Jun 17, Jun 25, Jul 2) - consistent
- [[Lynnette Mutugi]]: 2 of 3 held (Jun 18 both declined, Jun 25 + Jul 2 happened)
- [[Peter Gulliver]]: Jun 23 1:1 both declined - gap

**Vault staleness:** [[Jocyline Owano]] has no interactions logged at all. Everyone else is current (Jun 29 or Jul 2).

## Now What

1. **[[Lynnette Mutugi]]** - raise in next 1:1: she needs to be giving feedback to her reports ([[Sidi Ngade]], [[Jocyline Owano]]) and modelling the standard for other managers. She can't hold managers accountable for something she doesn't do herself.
2. **[[Joshua Black]], Leo Sgambato, [[Christos Petropoulos]], [[Edoardo Foco]]** - the four highest-1:1-volume managers with zero feedback. These are the "meeting without coaching" pattern. Decide whether Owen or Lynnette flags this in cross-functional check-ins.
3. **[[Jocyline Owano]]** - no vault interactions logged. Either ingest is behind or she's falling off the radar. Investigate.
4. **[[Peter Gulliver]]** - Owen's own 1:1 with his manager was declined. Reschedule.

## When

- Lynnette conversation: next 1:1 (this week)
- Jocyline gap: investigate today
- Peter reschedule: this week
- Cross-functional feedback nudge (Josh, Leo, Christos, Edo): decide approach in Lynnette 1:1, execute next week

## Methodology Note: Agenda edits are NOT feedback

We investigated whether Windmill 1:1 agenda edits could serve as a proxy for coaching activity, which would give a blended view beyond formal feedback counts. Several managers showed high edit volumes (Markus 1,148, Christos 521, Edoardo 514, Lynnette 454).

**Spot-check results (Owen/Lynnette agendas loaded and reviewed):**
- Content is operational task checklists: litigation sign-offs, budget approvals, project status, probation reminders, recruitment updates
- Not coaching observations, developmental feedback, or performance notes
- Owen/Ryan agenda was completely empty (`content: null`, last updated March 30)

**Conclusion:** Agenda edit counts reflect how actively a pair uses Windmill for meeting coordination, not how much coaching or developmental feedback is flowing. High edits = good task management, not evidence of the feedback muscle working.

**Standing rule for future pulses:** Do not count `one-on-one-agenda-edits` as a feedback proxy. The RAG board uses `feedback-given` (formal Windmill feedback via Windy bot or web UI) as the coaching signal. 1:1 meeting count is a hygiene check (are they meeting?), not a quality signal.

## Data Sources

- Windmill `stats_query`: `feedback-given`, `one-on-one-meetings`, `proactive-feedback-given`, `shoutouts-sent`, `one-on-one-agenda-edits` (Jun 2 - Jul 2, all employees, aggregateBy total)
- Windmill `feedback_query`: 3 entries in 30 days (Sidi on Lynnette, Owen on Sidi, Owen on Lynnette)
- Windmill `one-on-ones_agenda_load`: spot-checked Owen/Lynnette (Jul 2 + Jun 25) and Owen/Ryan (Jul 2) - operational content, not coaching
- Google Calendar: Owen's 1:1 events (last 2 weeks)
- Vault `/People/` notes: last interaction dates
