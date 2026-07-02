---
tags: [knowledge]
source: "[[2026-06-29 - Eng leads weekly]]"
date: 2026-06-29
---

# Running parallel regulatory tracks (own-license + partner integration) hedges risk but doubles engineering surface area

NALA is running Equals Money integration AND own-license (Jubilee) in parallel for EU/UK launch. The rationale: no regulatory certainty on either path, and waiting for one to resolve before starting the other would cost quarters. The cost: engineering builds against two potential architectures, key questions (omnibus accounts, flow of funds, VOP/COP) need answering for both, and resource-constrained teams (T-Rex lost 1.5 engineers) bear double the cognitive load.

Edo's pushback — "we're changing the metrics, which shows we don't know what we're doing" — captures the team's frustration: parallel tracks create the appearance of progress without the clarity of commitment.

**Implication:** Parallel tracks are a valid hedge when (a) the cost of waiting exceeds the cost of throwaway work, and (b) there's a clear decision point where you kill one track. Without (b), you end up permanently building two things. Set the kill criteria upfront: "if own-license gets regulatory green light by X date, we drop Equals Money."
