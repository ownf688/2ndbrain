# The 70+ hunt: pre-registered rules

Written and committed 2026-10-04, BEFORE any idea in this hunt was generated. These rules may be made stricter during the hunt, never looser. Any change is logged at the bottom with a reason.

## The user's limits (unchanged from stage 2)
Alone; evenings and weekends alongside a full-time job (Head of People at NALA, a payments firm); up to £500 and 2 weeks to test; UK and Ireland first, worldwide fine; nothing needing a licence or outside funding to start. Assets: UK (GB and NI) employment law, a hiring/People leadership role, an HR-leaders newsletter (size unknown), builds production tools with Claude Code/Supabase/React (21 tools built, per vault notes), a small clothing label, Belfast location, Nudge (existing product).

## Gate 1: the stage 1 kill checks (all 8)
Same checks and wording as `../millionaires/checks/_brief.md`. An idea is eligible for scoring only with **no clear FAIL and at most one UNCLEAR**. Must not repeat a reason in `../killed.md` or the B1-B32 kills unless new evidence changes that reason (state it).

## Gate 2: the stage 2 playbook test
The idea must map to a named playbook in `../millionaires/playbooks.md` section 5 AND cite at least one real case (from `../millionaires/cases/` or newly found) that did something similar, with its VERIFIED/CLAIMED label.

## Gate 3: the score (same weights as stage 1 and 2), with fixed anchors
A score may only be given at a level whose evidence is cited (link + date). Missing evidence = the lower band.

| Criterion | Max | Anchors |
|---|---|---|
| Proof people pay | 25 | **21-25:** buyers pay today for this same offer (not a substitute) at roughly the target price, shown by 3+ independent priced sellers or a public VERIFIED revenue figure. **15-20:** buyers pay for a close substitute at a similar price. **8-14:** an adjacent category pays; nothing direct. **0-7:** no evidence of payment. |
| How empty the field is | 20 | **16-20:** at most 2 direct rivals in the target segment, no free version, no incumbent bundling it. **10-15:** rivals exist but the target segment is demonstrably under-served (a cited gap: segment not covered, or a 3x+ price gap with buyers evidenced in between). **5-9:** several rivals; difference is only niche or brand. **0-4:** crowded, or free versions are good enough. |
| Timing | 20 | **16-20:** a dated trigger within the next 12 months that forces buyers to act (law with penalty, platform change, deadline), and no free incumbent fix shipped yet; OR a new wave whose paid demand first appeared within the last 12 months. **10-15:** a live wave with cited growth data, not dated. **5-9:** steady demand. **0-4:** window closing or demand falling. |
| Size of prize | 10 | **8-10:** a cited comparable solo/tiny operator at £250k+/yr in this category, and a reachable market to match. **5-7:** £50k-250k/yr plausible with a cited comparable. **2-4:** £10k-50k. **0-1:** under £10k. |
| Speed to first sale | 10 | **8-10:** first paid sale feasible inside the 2-week, £500 test (pre-sale or service). **5-7:** within 1-2 months. **0-4:** longer. |
| Fit with the user | 15 | **12-15:** uses 2+ of the user's assets, no unmanageable conflict, evenings/weekends only. **7-11:** uses 1 asset, or a manageable conflict. **0-6:** needs weekday presence, a serious conflict, or skills the user lacks. |

**Pass mark: 70.**

## Process rules (anti-gaming)
1. **Separation of duties.** The agent that generates an idea does not score it. Scoring is done by a separate scorer agent that sees the rubric, the kill-test file and the evidence, not this hunt's goal of "find a 70".
2. **Critic must agree.** Any idea scored 70+ goes to a critic agent told to find reasons it is below 70. The critic's score stands if lower, unless the critic's reasons are factually wrong (shown with a link).
3. **Calibration.** Before trusting any score, the scorer also re-scores B13, B20 and Nudge under these anchors. If any comes out more than 3 points above its earlier score (60, 58, 47), the anchors are being read too loosely and must be tightened.
4. **No moving the target.** User limits, kill checks, weights and anchors stay fixed. "Make the test bigger", "assume the newsletter has 20k readers", "assume a co-founder" are not allowed. Unknowns score at the lower band.
5. **Evidence rules as before.** Never invent a number; VERIFIED vs CLAIMED on every money figure; link and date on every claim; "not found" where missing.
6. **Keep going.** If a round finds nothing at 70+, write down why the best ones fell short, then generate the next round aimed at those gaps. Log each round in `ROUNDS.md`.

## Change log
- 2026-10-04, after calibration (`calibration.md`: B13 49, B20 52, Nudge 36, all lower than before, so the anchors read stricter): **tightened** "Proof people pay": the 21-25 band also requires the price the user would charge to be knowable now; if it depends on an unknown (e.g. list size), cap at 20.
