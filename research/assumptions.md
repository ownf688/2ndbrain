# Assumptions log

Research run started 2026-10-03. "Last 18 months" = April 2025 to October 2026.

1. **Output location.** Research saved inside the 2ndbrain vault at `/research/` (the only repo in this session). It is not a NALA note, so no People/Projects propagation was done.
2. **Vault boot steps skipped.** CLAUDE.md session-boot crons (transcript pulls, briefs) are for the brain pipeline, not this task. Skipped deliberately.
3. **Currency.** Money in GBP unless the source uses another currency; converted figures are marked as conversions.
4. **"Solo builder" constraint.** Openings must be runnable by one person, part-time alongside a day job, with under ~£2,000 to start and no regulated licence on day one.
5. **Conflict of interest.** Openings that would compete with the user's employer (payments/remittance) or that rely on NALA confidential data are excluded or flagged. Openings close to Nudge (interview feedback) are flagged as overlapping with an existing venture.
6. **Web search is US-routed.** The search tool is US-only; UK/IE/EU results may be thinner. Agents were told to go to primary UK/EU sources directly via fetch where possible.
7. **Evidence labels.** fact = from a primary or reputable published source with a number and date; reasonable guess = inference from facts; opinion = judgment.
8. **Scoring "my fit" (15 pts).** Per instruction, background is a minor factor; fit scores mainly reflect build stack (Claude Code/Supabase/React), UK/NI location, and HR/employment-law knowledge as a tiebreaker.
9. **Primary-source sites blocked (material limitation).** This container's network policy denies direct connections to gov.uk, ons.gov.uk, NISRA, CSO, CAA and several others (proxy `connect_rejected`, confirmed 2026-10-03). Web *search* works, so agents found figures via search results that quote those sources and linked the original page, but most numbers were **not checked on the original page**. Each scan file says which. Treat any figure as "sourced but unverified at origin" unless stated otherwise. Fix: widen the environment's network allowlist and re-run verification.
10. **Per-agent search budget.** Several scan agents hit a 200-search cap and stopped early; gaps are marked "not found" in each file rather than filled from memory.
