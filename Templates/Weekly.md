---
date: 
week: 
status: in-progress
previous: 
tags: [weekly]
---

# Week 

*Start:           End:           Duration:*

## Pass checklist
- [ ] **1. Inbox swept** (5 min)
- [ ] **2. Meetings reviewed** (15 min)
- [ ] **3. Knowledge promoted** (15 min)
- [ ] **4. State refreshed** (10 min)
- [ ] **5. Reflected** (10 min)

---

## Reflection (What / So What / Now What / When)

### What happened this week
*Key meetings, decisions, hires, pipeline moves, people items.*



### So What — why it matters
*What shifted in trajectory? What surprised me? Where was I wrong?*



### Now What — actions for next week
*Concrete, 4D-validated: Data, Decision, DRI, Deadline.*

- [ ] DRI: [[Me]] —
- [ ] DRI: [[Me]] —

### When — deadlines carrying forward

| Item | DRI | Deadline | Status |
|------|-----|----------|--------|

## Decision reviews due this week
*Decisions from `/Decisions/` whose `review_date` falls this week. Score: right-for-right-reasons / right-but-lucky / wrong-but-learned / too-early.*



## Calibration
*Predictions I got right. Predictions I got wrong. What I'd tell last-Monday-me.*



---

## This week's meetings
*Set `date:` to any day inside the week. Query derives Mon–Sun from it.*

```dataview
LIST
FROM "Meetings"
WHERE date >= this.date - dur(1 day) * (this.date.weekday - 1)
  AND date <  this.date + dur(1 day) * (8 - this.date.weekday)
SORT date ASC
```

## Knowledge promoted this week
*Atomic notes written from candidate flags. Link to each.*



## Notable meetings
*Meetings worth remembering beyond this week — one line on why.*



## Active projects: state at week end
*One line per active project. Honest, not aspirational.*



## Open follow-ups carrying forward
*Things from this week that didn't get resolved and aren't bound to a specific person/project note.*



---

## Bad-week fallback
*10-minute version: sweep inbox, write three sentences in the reflection section, done. Better than nothing. Don't let perfect be the enemy.*
