# Critic: NUDGE_REPORT.md, attacked from both sides

Date: 2026-10-04. 10 web searches used. Direct page fetches are blocked here, so every external fact below was **seen in a search result, not checked at the original page**. Labels: FACT (sourced), CLAIMED (vendor or founder says), REASONABLE GUESS, OPINION.

## Headline

The draft is mostly sound, but it has one internal contradiction that matters. It scores Nudge low because **Ashby** is "one feature away", then recommends a niche (Workable, BambooHR, HiBob, Teamtailor, Pinpoint) where Ashby is irrelevant. It never tested whether that niche is actually open. I checked: the niche does **not** collapse, but it is more crowded than the draft implies, and the threat there is a different one (bundled recording notetakers, not Slack capture).

---

## 1. The recommended niche: checked

| Vendor | Slack-native feedback submission? | AI notes or scorecard drafting? | Source |
|---|---|---|---|
| Workable | Not found. Slack integration is in **Open Beta** and pushes updates on candidates, comments, evaluations and completed video interviews (notifications, not capture). FACT | Has an "AI Recruiting Agent" (banner). Interview AI notes: not found | [Workable backstage](https://resources.workable.com/backstage-at-workable/integration-with-slack) |
| Teamtailor | Not found | **Yes.** Co-pilot transcribes and summarises recorded video interviews and fills candidate answers into the Interview Kit. CLAIMED (vendor) | [Teamtailor Co-pilot](https://www.teamtailor.com/en/content-hub/discover-how-teamtailors-new-ai-feature-co-pilot-can-improve-your-recruitment-today/) |
| Pinpoint | Not found | **Yes.** AI notetaking (built in about 4 weeks with Cronofy) plus AI scorecards that surface transcript sections per question; a "Copilot" agent layer. CLAIMED (vendor case study) | [Cronofy case study](https://www.cronofy.com/case-studies/pinpoint-interview-scheduling-ai-notetaking) |
| BambooHR | Not found | Says it uses AI to "streamline note-taking" and analyse interview data; Fireflies integration syncs notes to candidate profiles. CLAIMED | [BambooHR AI page](https://www.bamboohr.com/about-bamboohr/careers/ai-guidelines-for-candidates), [Fireflies](https://fireflies.ai/integrations/applicant-tracking-system/bamboohr) |
| HiBob (Hiring) | Not found. HiBob has a Slackbot HCM integration, but no interview feedback capture found | Not found (third-party Skima AI does screening) | [Skima](https://skima.ai/integrations/hibob-ai-screening) |
| Recruitee, Personio Recruiting, JazzHR | Not found | Not found | [rfp.wiki](https://www.rfp.wiki/hr-office/talent-acquisition-recruiting-suites/applicant-tracking-systems-ats/jazzhr/recruitee) |

**Verdict on the niche (OPINION):** it survives on the narrow claim "no ATS in this list lets an interviewer type feedback into Slack and get a scorecard". It does **not** survive as "nobody here gives you AI feedback drafting". Teamtailor and Pinpoint already bundle recording-based AI notes into the ATS price. So the pitch must be **"for interviews nobody records"** (in person, phone screens, debriefs, recording-shy teams), not "faster feedback in general". The draft's pitch line should say this outright.

**A fact the draft missed that cuts against it (FACT, vault):** this vault's CLAUDE.md lists **Workable** as NALA's ATS and **Metaview (NALA workspace)** as a connected system. The one Workable shop the founder knows best chose the recording route. That is the most relevant single data point in the whole report for the niche, and it is a warning, not a tailwind. (Also note it proves NALA *uses* Metaview, not that it *pays*; Metaview has a free tier. The draft's "your employer pays for Metaview" should read "NALA uses Metaview".)

## 2. Convo (itsconvo.com)

Search returned a family of identical-pattern pages on the same site: "Slack to Greenhouse", "WhatsApp to Greenhouse", "Dialpad to Greenhouse", "BlueJeans to Greenhouse", "phone to Greenhouse" and more. The snippet says the connection runs **through Zapier, Make or IFTTT** and sends "meeting summaries, action items" to Greenhouse. FACT (search result): [itsconvo.com](https://www.itsconvo.com/integrations/slack-to-greenhouse). Price: not found.

REASONABLE GUESS: this is a general meeting notetaker with programmatically generated SEO pages, not a dedicated Slack free-text-to-scorecard product. The draft should downgrade it from "lead that needs checking" to "probably not a direct rival; adjacent notetaker".

## 3. Slack Marketplace: do free installs count?

Search snippet of Slack's docs: apps need "at least 10 installations on active workspaces", active means used in the **past 28 days**, and the app must **stay at 10 or more throughout the entire review**. A temporary 5-workspace threshold existed and was raised back to 10 "as of July 2026". FACT (search result): [Slack changelog](https://docs.slack.dev/changelog/2026/09/01/slack-marketplace-install-requirement), [guidelines](https://docs.slack.dev/slack-marketplace/slack-marketplace-app-guidelines-and-requirements/). Nothing in the snippet mentions payment, so free pilots very likely count (REASONABLE GUESS).

**Two problems this creates for the draft's plan (OPINION):**
- **30-day pilots are too short.** Review can take up to 12 weeks and the 10 must hold for all of it. A pilot that ends or churns at day 30 drops you below the bar mid-review. Pilots need to run 90+ days or convert.
- **The kill date and the listing timeline clash.** Apply by 31 Dec 2026 plus up to 12 weeks of review means approval could land late March 2027, after the 31 Jan 2027 kill date. Yet the "niche lifestyle" scenario assumes a listing. Either move the kill date to about 31 March 2027, or make the kill test independent of listing.

Also: the draft dates the 10-install rule to the 2026-09-01 changelog while the snippet says "as of July 2026". Minor, but say "July to September 2026" or check the page.

## 4. Missed rivals

| Name | What | Threat | Source |
|---|---|---|---|
| **Screenloop** (UK ATS for startups and SMEs) | Records interviews, AI scorecards pushed into the ATS; markets "eliminates the need to hunt down hiring managers for their interview feedback", which is almost the Chase pitch word for word. Slack: not found | Medium, same buyer and same pain | [Screenloop blog](https://www.screenloop.com/blog/introducing-ai-scorecards) CLAIMED |
| **Interviewsly** | Listed in the Slack App Directory; interview management for Slack teams incl. "feedback sharing". AI and activity: not found | Low to medium; proves a Slack-listed interview app exists, so the "no direct competitor" claim needs one more caveat | [Slack apps](https://slack.com/apps/AUNQK1L5D-interviewsly) |
| **Scribbl** | "Bot-free" interview notetaker | Weakens "no recording bot" as a differentiator: bot-free is not the same as recording-free, but buyers may not see the difference | [pin.com](https://www.pin.com/blog/best-ai-note-taking-tools-recruiters/) CLAIMED |
| Microsoft Teams equivalent | Not searched (budget) | Not found | n/a |

## 5. Too harsh on Nudge

1. **"KILLED" is the wrong headline for a product that exists.** Stage 1 asks "should you start this?". For Nudge the money is spent; the only question is whether the *next* 15 hours of selling beats the next-best use of those hours. Suggested framing: **"Would not pass stage 1 as a new idea (fails checks 4 and 7). Stage 1 does not decide whether to continue; the two-week test does."** (OPINION)
2. **Check 4 and the "emptiness" score (7/20) are scored against Ashby, but the recommendation excludes Ashby shops.** Scored against the niche, Slack-native capture is not shipped by any of the eight ATSs checked. Raise emptiness to about 9-10, but add the Teamtailor/Pinpoint bundled-notetaker point so it does not go higher (OPINION).
3. **Check 7 relies on Slack Business+.** The bundled AI agent and AI workflow steps are on Business+ ($15/user/month). Whether firms of 10-150 people are mostly on Business+ or on Pro: not found. The draft should say the FAIL is strongest for Business+ customers and unverified for the rest.
4. **"No Product Hunt page" is wrong.** Hunted Space (a Product Hunt tracker) shows Nudge was submitted to Product Hunt. FACT (search result): [Hunted Space](https://webmail.hunted.space/product/nudge-interview-feedback-in-60-seconds). Launch date: not found.

## 6. Too soft on Nudge

1. **That same Product Hunt launch got 0 upvotes and 1 comment, #32 on the day.** FACT (search result, same link). The draft says the footprint is thin; it is thinner than thin, it is a launch that drew no pull. Say so.
2. **The 30% "niche lifestyle" scenario is not conditioned on the unknown customer count.** If paying customers today are zero (nothing in the notes or footprint suggests otherwise), reaching 30+ paying workspaces part-time is closer to 15-25% (OPINION) given the TrustMRR median of $169 a month. Present the outlook as two rows: "if 0 paying today" and "if 5+ paying today".
3. **The insider edge cuts both ways.** The draft sells "genuine insider edge", but the insider's own company (Workable + Metaview) is the counter-example (see section 1).
4. **The pass bar in the two-week test is soft on retention.** "10 installed and actively used" should mean 10 workspaces still active at day 28 (Slack's own definition), not 10 installs.

## 7. Factual and sourcing fixes

- **Slack rate limit for existing installs:** `footprint_platform_legal.md` says 2 Sep 2025, `comparables_base_rates.md` says 3 Mar 2026, both citing the same [changelog](https://docs.slack.dev/changelog/2025/05/29/rate-limit-changes-for-non-marketplace-apps). I could not open it. Keep "sources disagree", but the draft should not present this as an external disagreement; it is an internal transcription conflict. Either way, it applies now.
- **"Slack changed its terms twice in 18 months"**: no source given. Cite the May 2025 terms update and name the second change, or cut "twice".
- **"Your employer pays for Metaview"**: change to "uses" (see section 1).
- **Arithmetic checks out** (FACT, my own working): 30 x £39 x 12 = £14,040; 150 x £79 x 12 = £142,200. $10k a month at roughly £7,500 is 95 (at £79) to 192 (at £39) workspaces. The $1m figures assume an unstated exchange rate of about 0.75; state it.
- **Score 47/100:** defensible within ±5 (OPINION). My adjustments (+2 to +3 emptiness, -1 to -2 proof-people-pay for the 0-upvote launch) roughly cancel, so 47 stands, but the reasons should change.
