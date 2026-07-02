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

## Reflection

### What I learned this week
*Not what I did — what's actually new in my head.*



### What surprised me
*Where did reality diverge from expectation?*



### Next week
*What's the one thing that matters most? Who do I need to talk to? What's at risk?*



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
