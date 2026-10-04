# Nudge: competitor landscape (kill checks 3, 4, 7)

Date seen for every link: 2026-10-04. Method: 12 web searches (budget used in full). Direct page fetches were attempted for itsconvo.com, ashbyhq.com, support.goodtime.io and lever.co and were all blocked by the network proxy, so almost every fact below was **seen in a search result, not checked at the original page**. Names in the brief that I could not cover inside the search budget are listed as "not checked this pass" rather than guessed.

Labels: FACT (sourced), CLAIMED (vendor or founder says), REASONABLE GUESS, OPINION. Money: VERIFIED or CLAIMED.

---

## 1. Direct substitutes (Slack free text to scorecard)

**Nudge itself is visible.** A search for Slack interview feedback scorecard tools returned Nudge's Hunted Space page ("nudge interview feedback in 60 seconds"), describing a Slack bot that asks "How did it go?" and uses AI to structure the reply. FACT that the page exists: https://webmail.hunted.space/product/nudge-interview-feedback-in-60-seconds

**No dedicated, packaged rival found** that does exactly "DM the interviewer, take free text, AI structures it into a scorecard, one-click confirm". FACT for this search pass only; absence of evidence across 12 searches is not proof of absence.

Closest things found:

- **Convo (itsconvo.com), "Slack to Greenhouse" integration page.** Search snippet: integration tools "convert Slack interview notes into Greenhouse scorecards with ratings, strengths, and concerns formatted and filed automatically". It is unclear whether that snippet comes from Convo or from an automation blog in the same result set. CLAIMED, not checked (page blocked). https://www.itsconvo.com/integrations/slack-to-greenhouse . Pricing, funding: not found. **This is the one lead that most needs a manual check.**
- **US Tech Automations blog (2026)** describes a Greenhouse to Slack recipe including turning Slack notes into scorecards. A how-to, not a product. https://ustechautomations.com/resources/blog/connect-greenhouse-to-slack-recruiting-automation-2026
- **DIY templates:** an n8n workflow that audits interview feedback with GPT-4o-mini and sends coaching via Slack (https://growwstacks.com/workflows/audit-interview-feedback-and-report-via-slack-with-gpt-4o-mini-and-google-sheets/); a "custom GPT for interview feedback consistency" guide (https://chatprd.ai/how-i-ai/workflows/how-to-improve-interview-feedback-consistency-with-a-custom-gpt); Cassidy AI's "Interview scorecard summarizer" use case (https://docs.cassidyai.com/use-cases/recruiting/interview-scorecard-summarizer). FACT these exist; they show the pattern is already documented as a weekend build.
- **candidate.fyi** sends post-interview Workday feedback forms in Slack, completable inside Slack. Structured form, not free text. FACT (search result): https://support.candidate.fyi/articles/4293269639-workday-feedback-forms
- **GoodTime "AI-Assisted Scorecards"**: speeds interviewers "from interview feedback to submitted scorecard", includes an "AI-Polish" button; available for Lever and Workday customers. FACT (search result, page blocked): https://support.goodtime.io/hc/en-us/articles/26352216584727 . Price not found.

**Not checked this pass (budget):** HireLogic, HireVue, Juicebox, Kula, Gem, Spark Hire, Interviewer.AI, any "Feedback bot" on Slack Marketplace, Product Hunt and G2 category pages. The earlier 2026-10-03 pass said Spark Hire Recruit and GoodTime send Slack reminders; not re-verified.

## 2. ATS native features (the big threat)

| ATS | Feedback inside Slack? | AI-drafted scorecard? | Extra cost | Source |
|---|---|---|---|---|
| **Ashby** | Yes. Feedback reminders are interactive Slack messages; interviewers "open and complete the full feedback form without leaving Slack". Also **Ashby Assistant in Slack** (open beta, all customers): DM the Ashby app to ask about candidates, interviews and feedback. FACT (search result) | Yes. **AI Notetaker** records, transcribes and auto-fills feedback forms; custom org-level prompts for auto-fill available to all customers. FACT (search result) | Slack features: no add-on found. AI Notetaker is a separate add-on bundle with a free trial; price not found | https://www.ashbyhq.com/product-updates/improvements-to-feedback-reminders , https://www.ashbyhq.com/product-updates/ashby-assistant-in-slack , https://www.ashbyhq.com/product-updates/ai-notetaker-auto-fill , https://www.ashbyhq.com/add-ons/ai-notetaker |
| **Greenhouse** | Slack reminders with links to scorecards (via native or third-party integrations). Native free-text-in-Slack submission: not found | Via partners: Metaview Notetaker "auto-fills Greenhouse scorecards from interview transcripts" with a submit-to-ATS button. FACT (search result) | Partner pricing (Metaview below) | https://www.metaview.ai/resources/blog/greenhouse-ats-integrations |
| **Lever** | Not found this pass | Yes. **AI Interview Companion (formerly Pillar)** automates interview summaries and feedback, prompts for evidence-based feedback, summarises consensus and discrepancies. CLAIMED (vendor page via search) | Not found | https://lever.co/solutions/ai-interview-companion |
| **Workable** | Not found this pass (only interview kits and auto-generated scorecards in Workable itself) | Not found this pass | n/a | https://resources.workable.com/backstage/interview-kits-scorecards |
| **Teamtailor, Pinpoint, BambooHR, HiBob, Recruitee** | Not checked this pass | Not checked this pass | n/a | n/a |

FACT: Pillar (seed funded, about $2.83M total) was acquired by Employ in March 2025 (search result citing CB Insights), and is now Lever's AI Interview Companion. https://www.cbinsights.com/company/pillar-2/financials

OPINION: Ashby is one small step from Nudge's core loop. It already has (a) the feedback form inside Slack, (b) a Slack DM assistant that knows about interviews, and (c) AI that drafts a feedback form from unstructured input with custom prompts. Wiring "type your thoughts to the Ashby bot, we fill the form" is a feature ticket, not a product.

## 3. AI notetakers moving into hiring

- **Metaview.** Notetaker auto-fills ATS scorecards from transcripts (Greenhouse example above). Pricing seen in third-party pricing pages: Free notetaker 25 conversations/month with 14-day history; Pro notetaker about $50 per user/month billed annually (another source says $60). CLAIMED, third-party pages, not Metaview's own: https://toolradar.com/tools/metaview/pricing , https://www.noon.ai/blog/articles/254-metaview-pricing-2026 , https://www.pin.com/blog/metaview-pricing/ . **Slack:** Metaview's own support docs say its Slack integration "only supports Sourcing workflows"; notes notifications "are not yet available". FACT (search result): https://support.metaview.ai/slack.md
- **BrightHire.** Interview intelligence (record, transcribe, analyse). **Acquired by Zoom in November 2025**, undisclosed sum. FACT (search results incl. Zoom blog): https://www.zoom.com/en/blog/zoom-acquires-brighthire/ . This puts interview scorecard AI inside a platform with hundreds of millions of meeting users.
- **Screenloop.** London hiring intelligence platform: post-interview analytics, candidate feedback, interviewer coaching. Pricing not found.
- **Otter, Fireflies, Granola, Google Meet/Teams built-in notes.** Not checked this pass. REASONABLE GUESS: generic notetakers produce summaries but not ATS-mapped scorecards without setup.

OPINION on "brain-dump is unnecessary": for recorded video interviews at companies that accept a bot on the call, transcript-to-scorecard already exists (Metaview, Ashby, Lever, BrightHire/Zoom) and is better evidence than a 60-second recollection. Nudge's brain-dump only wins where recording does not happen: in-person interviews, candidates or jurisdictions uneasy with recording, phone screens, debriefs, and teams that refuse bot fees.

## 4. Slack's own AI and free assistants

- FACT (Slack blog, June 2025): Business+ rose from $12.50 to $15 per user/month (annual) and now includes Slackbot as a personal AI agent, AI search, recaps, AI workflow generation "with AI-powered steps", and Agentforce and partner AI agents can be deployed on all paid plans. The standalone $10 AI add-on was retired. https://slack.com/blog/news/june-2025-pricing-and-packaging-announcement
- FACT: ChatGPT, Claude and Gemini all have free consumer tiers in 2026 (search result guides, e.g. https://cut-the-saas.com/the-cut/best-free-ai-tools-2026 ). Whether each has a Slack app on a free plan: not found this pass.

OPINION: a People team on Slack Business+ can today build "after the calendar event, DM the interviewer, take their reply, run an AI step against our scorecard template, post the result" in Workflow Builder with no extra licence. What it will not do well out of the box: write back into the ATS, chase persistently, thread probes between interviewers, or give a dashboard. Those gaps are real but small and are exactly what Slack and Salesforce agents are being pointed at.

## 5. Who has money

| Player | Funding | Status | Money label |
|---|---|---|---|
| Metaview | $35M Series B led by GV, June 2025; about $50M total since 2018 | Independent | CLAIMED (press: https://www.unleash.ai/hr-technology/news/google-ventures-leads-35-million-series-b-funding-in-metaview ) |
| BrightHire | About $36M total ($12.5M A 2021, $20.5M B Oct 2021) | Acquired by Zoom, Nov 2025 | CLAIMED (search results, CB Insights) |
| Pillar | About $2.83M | Acquired by Employ (Lever) Mar 2025 | CLAIMED (CB Insights via search) |
| Screenloop | About $7M seed total (incl. $2.5M Dec 2021); one source says EUR 8.8M over 2 rounds | Independent | CLAIMED (https://screenloop.com/blog/screenloop-raises-7m-for-its-hiring-intelligence-platform , https://uktech.news/recruitment/screenloop-funding-20211203 ) |
| Ashby | Not searched this pass (budget) | n/a | Not found |

---

## Rival table

| Name | Overlap with Nudge | Price | Funding | Link |
|---|---|---|---|---|
| Ashby | Full feedback form in Slack; Slack DM assistant; AI auto-fill of feedback forms with custom prompts | Slack features included; AI Notetaker add-on, price not found | Not found this pass | https://www.ashbyhq.com/product-updates/improvements-to-feedback-reminders |
| Metaview | Transcript to ATS scorecard auto-fill; no Slack notes features yet | Free 25 conv/month; about $50-60/user/month Pro (CLAIMED, 3rd party) | $35M B (2025), about $50M total (CLAIMED) | https://support.metaview.ai/slack.md |
| BrightHire (Zoom) | Interview intelligence, AI summaries | Not found | About $36M, then acquired by Zoom | https://www.zoom.com/en/blog/zoom-acquires-brighthire/ |
| Lever AI Interview Companion (ex-Pillar) | AI summaries and feedback drafting inside ATS | Not found | Pillar about $2.83M, acquired by Employ | https://lever.co/solutions/ai-interview-companion |
| GoodTime | AI-Assisted Scorecards, AI-Polish, Slack reminders | Not found | Not checked | https://support.goodtime.io/hc/en-us/articles/26352216584727 |
| Greenhouse + Metaview | Slack reminders; partner AI fills scorecards | Partner pricing | n/a | https://www.metaview.ai/resources/blog/greenhouse-ats-integrations |
| Convo (itsconvo.com) | Possibly Slack notes to Greenhouse scorecards (unverified) | Not found | Not found | https://www.itsconvo.com/integrations/slack-to-greenhouse |
| candidate.fyi | Structured feedback forms completed inside Slack (Workday) | Not found | Not checked | https://support.candidate.fyi/articles/4293269639-workday-feedback-forms |
| Screenloop | Interview feedback analytics and coaching | Not found | About $7M seed (CLAIMED) | https://screenloop.com/blog/screenloop-raises-7m-for-its-hiring-intelligence-platform |
| Slack Business+ (Slackbot, AI workflow steps, Agentforce) | DIY DM-and-structure flow with no add-on | $15/user/month annual, AI included | Salesforce | https://slack.com/blog/news/june-2025-pricing-and-packaging-announcement |
| DIY (n8n, custom GPT, Cassidy) | Same AI-structuring step, self-built | Free to low | n/a | links in section 1 |

---

## Verdicts

**Check 3, rivals at similar price: UNCLEAR (leans FAIL).** No packaged Slack free-text-to-scorecard rival was found at GBP 39-79/month, so on a narrow definition Nudge is alone. But the job ("get a scorecard filed fast without effort") is already served at or below Nudge's price: Metaview free tier (25 conversations/month), Ashby's in-Slack forms bundled at no extra cost, GoodTime AI scorecards. One unverified lead (Convo, Slack notes to Greenhouse) must be checked by hand before calling this PASS.

**Check 4, could a big company switch it on free: FAIL.** Ashby already ships the three pieces (form inside Slack, Slack DM assistant, AI auto-fill with custom prompts). Lever has AI feedback drafting. Zoom now owns BrightHire. Each could add a "type your notes, we fill the form" mode as a feature at no extra charge.

**Check 7, free AI assistants within 2 years: FAIL.** Slack Business+ already includes Slackbot as an agent and AI workflow steps at no add-on cost (since June 2025), and public templates already chain Slack plus GPT for interview feedback. A competent People Ops person can approximate Nudge's core today. Remaining gaps (ATS write-back, chasing, probe threading) are narrowing, not widening.

## OPINION: does "no direct competitor" hold?

Only in the narrowest literal sense. The claim "Metaview and BrightHire need a recording bot" is true for them, but it ignores the real threat: Ashby already lets interviewers complete feedback inside Slack and drafts forms with AI, and Slack itself now bundles the AI to build the rest. The founder's other claim, "every ATS vendor assumes the problem is awareness", is no longer accurate for Ashby or Lever. Note also Metaview's Slack support is sourcing-only today, which is a window, not a moat.

Where a real point of difference might live:
1. **No recording, by design.** In-person interviews, phone screens, and teams or regions where recording candidates is legally or culturally awkward (EU, parts of Africa). Sell this as privacy-first, not as a missing feature.
2. **ATS-agnostic for the long tail.** Small companies on Workable, BambooHR, HiBob, Teamtailor, Pinpoint, where nothing like Ashby's Slack loop was found this pass. That is the most defensible segment, and it is also where NALA sits.
3. **Cross-interviewer intelligence ("probe threading").** Nobody found does live hand-off of concerns from interviewer 1 to interviewer 2 inside Slack. Strongest genuinely new idea, but also the easiest for Ashby to copy once proven.
4. **The chasing outcome** (founder claim: 3-5 hours/week of manual chasing to zero). Sell the time saved and feedback completion rate, not the AI.

Net: a feature-sized wedge with a 12-24 month window, best aimed at non-Ashby, non-Greenhouse SMBs and in-person-heavy hiring.
