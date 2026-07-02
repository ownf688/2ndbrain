---
tags: [knowledge, performance, ql, eys]
source: QuantumLight Playbook (Revolut performance system)
claim: Structured performance assessment on three independent dimensions with exponential rewards for top performers and fast exits for underperformers produces a self-reinforcing high-talent-bar culture.
---

# The QuantumLight system: three dimensions, five grades, exponential rewards

## The claim

Performance management works when it measures three things independently (Deliverables, Skills, Culture), grades against a defined talent bar, and rewards the top tier exponentially rather than linearly. This is the system behind Revolut's scale from startup to 6,000+ employees while maintaining a 0.1% hire rate.

## Three dimensions (each scored independently)

1. **Deliverables** - how well output is delivered. Scored on Speed, Quality, Complexity. Formula: `[Speed + Quality] x Complexity`. Separates discipline from expertise - someone can be an expert but lack the discipline to ship.
2. **Skills** - technical competencies required for the role. Same scorecards used in hiring AND reviews (single bar, no drift). Scored per-skill with competency matrices by seniority.
3. **Culture** - alignment with company values. Scored per-value with yes/no behaviour statements. Critical rule: **Poor in any single value = overall Poor regardless of other scores.**

All three use 5-level scorecards (Poor / Basic / Intermediate / Advanced / Exceptional) with ascending yes/no statements - the first "No" fixes the level.

## Five grades (proficiency vs talent bar)

| Grade | vs Bar | Target ratio | Action |
|-------|--------|-------------|--------|
| Unsatisfactory | Significantly below | <10% | Accelerate exit |
| Below Bar | Below | - | Below-bar Choice: enhanced separation or PIP |
| Above Bar | At/slightly above | 60-80% | Push to become Strong |
| **Strong** | Significantly above | **15-25%** | **Target segment for retention + promotion** |
| Exceptional | Way above + novel complexity | <5% | Special tier |

**Strong is the gold standard.** The same proficiency yields different grades by seniority - a Junior beating a low bar = Strong; a Senior at the same proficiency against a higher bar = Above Bar.

## Exponential rewards

| Grade | Bonus multiplier |
|-------|-----------------|
| Below Bar | 0.0x |
| Above Bar | 0.5x |
| Strong | **3.0x** |
| Exceptional | **5.0x** |

The gap between Above Bar (0.5x) and Strong (3.0x) is the whole point - it makes the difference between meeting expectations and exceeding them feel enormous. A-players are worth disproportionately more, so they should capture disproportionately more.

## Key principles for NALA application

- **Promotion is a reward for proven A-players, not a retention tool.** Promoting someone before they're ready sets a bad precedent.
- **Scoring decoupled from pay.** Managers score purely on performance; the reward budget is set separately (at NALA, by Peter). This prevents managers from gaming scores to get people raises.
- **Same scorecards for hiring and reviews.** The bar that gets someone in is the bar they're measured against. No drift.
- **Calibration is mandatory.** Managers are too generous by default. The Performance Team (at NALA: Owen) recalibrates to keep Strong at 15-25%.
- **Culture scoring has a veto.** Poor in any single value overrides everything else. Values are non-negotiable.

## Source

- Notion: [Performance Management - Retaining Top Talent & Exiting Poor Performers](https://app.notion.com/p/38c56eaacda581cca8e6cbd1e7f335ee) (7 child pages)
- Raw files: `~/Library/Application Support/Claude/local-agent-mode-sessions/78f912e0-9802-4efe-a625-21554022833f/.../outputs/QuantumLight-Performance-Raw/` (10 files including transcribed scorecards)
- Original: `docs.quantumlightcapital.com` (gated)
