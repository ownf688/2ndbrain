---
aliases: [EU UK Launch, Equals Money, EU Launch, UK Launch, Jubilee]
company: NALA
status: active
tags: [project]
---

# EU UK Launch

Launching NALA's remittance product in EU and UK markets. Running two parallel tracks: Equals Money integration (partner) and own-license via Jubilee (preferred but uncertain). Led by [[Markus Seebacher]] with [[Christos Petropoulos]], [[Edoardo Foco]], and [[Joshua Black]] (own-license workstream).

## Quality framework

| Bar | Definition |
|-----|-----------|
| **Great** | Flow of funds confirmed; engineering building against clear API spec; own-license regulatory feedback positive; resource plan covers summer holidays; launch date credible |
| **Good** | Equals Money integration progressing with known blockers being worked; own-license still alive as parallel option; engineering has enough clarity to start key workstreams |
| **Mediocre** | Waiting on partnership/regulatory blockers with no engineering work unblocked; key people on leave without coverage; parallel tracks creating confusion about what to build |
| **Bad** | Neither track has regulatory certainty; engineering idle on EU/UK; critical resources (Bailey, Simeon) pulled to other priorities; Q3 launch timeline not credible |

### Notes on use

- "Bad" is not about delays per se — it's about losing optionality (both tracks stalling simultaneously)
- Resource constraints (T-Rex lost 1.5 engineers) are a structural headwind, not a temporary blip

## Project keywords

EU, UK, Equals Money, Jubilee, Modulr, own-license, remediation, flow of funds, omnibus account, VOP, COP, ledger, regulatory, FCA, EMI, True Layer

## Slack channels to monitor

- #engineering
- #eng-leads
- #payments
- #compliance

## Critical-path items

- [ ] Flow of funds from Equals Money — expected 2026-06-29, determines if omnibus account (no per-user wallets) is viable
- [ ] Equals Money API feasibility — can API hold pooled funds without per-user wallet?
- [ ] Own-license (Jubilee) regulatory feedback — Josh running this workstream
- [ ] True Layer SDK release — regression fix, targeting Wednesday 2026-07-02
- [ ] Christos deep-dive on Equals once flow of funds received (with Simeon, Bailey, Chi)
- [ ] Daily standups running with Nico, Peter, Christos (program cadence set by Markus)
- [ ] Resource plan for summer — Alessandro off 3 weeks, Christos off August, Edo covering

## Project owners

- [[Markus Seebacher]]
- [[Christos Petropoulos]]
- [[Edoardo Foco]]
- [[Joshua Black]]

## Updates

### 2026-07-07 — EU MD Pipeline

- Jan Rozumbersky screened for EU MD. Fit-and-proper experience (CZ, NL) but no Belgium market knowledge. NBB process timeline: ~12 months per NL precedent. Open question on relocation budget for non-Belgium candidates.

### 2026-06-29 — Health: Mediocre

**Deltas:**
- Markus set up program structure with daily standups (Nico, Peter, Christos)
- Flow of funds expected today — key gating item for technical approach
- Running Equals Money and own-license in parallel (preferred: own-license, but no regulatory certainty)
- True Layer SDK regression delaying release to Wednesday
- T-Rex lost 1.5 engineers (one left + Simeon acting as EM)
- Bailey confirmed staying in Rafiki 1-2 months — cannot be moved without killing that squad
- Edo pushed back on changing Q3 metrics — "shows we don't know what we're doing"
- Parf's team reportedly moving to engineering (pending Benji confirmation)

**Risks:**
- Neither Equals Money nor own-license has confirmed technical viability yet
- Resource crunch: BEE team bears most Q3 weight with only 2 engineers
- Summer holidays (Alessandro 3 weeks, Christos August) create coverage gaps
- "This can go south so easily now" — Christos on the resource/scope situation

## Decision log

- [2026-06-29] Run Equals Money and own-license in parallel; preferred is own-license — source: [[2026-06-29 - Eng leads weekly]]
- [2026-06-29] Bailey stays in Rafiki 1-2 months, not moving — source: [[2026-06-29 - Eng leads weekly]]
- [2026-06-29] Christos/Joseph to own Apple developer account — source: [[2026-06-29 - Eng leads weekly]]
