# Nudge, scrutinised: both methods, findings and outlook

Research date: 2026-10-04. Research only. Inputs:
- your own Nudge notes in the vault (TPO seeds dated 2026-07-08);
- three research files in this folder: `competitors.md`, `footprint_platform_legal.md` and `comparables_base_rates.md` (36 searches);
- a critic's attack on the first draft, `critic.md` (10 searches). Its corrections are applied below.

The stage 1 and stage 2 methods are in `../REPORT.md` and `../BETS.md`.

> **Trust note.** This environment blocks nudgebot.ai, Companies House, Slack's docs and most vendor sites, so every external fact was **seen in a search result, not on the original page**. Facts about Nudge itself (pricing, Stripe, OAuth, App Directory, the time Chase saved) come from your own notes and are labelled **CLAIMED (founder)**. Your paying-customer count was not in the notes, so this report gives the outlook both ways (section 7). That number changes the verdict more than anything else here.

---

## 1. The answer in one page

**Stage 1 (the 7 kill checks): Nudge would not pass as a new idea.** It fails check 4 (big companies already ship most of it) and check 7 (Slack's bundled AI lets a team rough it out themselves), and leans fail on check 3. Stage 1 was built to screen *new* openings, so it doesn't decide whether to carry on with a product that already exists. That decision belongs to the two-week test in section 8.

**Stage 2 (playbooks and base rates): a legitimate playbook, run in its hardest form.**
- Nudge follows "build what your own job lacked, sell it to peers" (PB6). That playbook has the most verified wins among the stage 2 cases (Userflow, First Derivatives). But in those cases it took 3 to 5 years, and every scaled spin-out found went full-time once demand showed.
- Nudge sells through Slack, where bootstrapped apps plateau:
  - HeyTaco: about $440k a year (CLAIMED).
  - Standuply: fell from $450k to $154k (CLAIMED).
  - Geekbot: the only bootstrapped $1m Slack app found (CLAIMED), with a team of 17 or more.

**Score on the stage 2 scale: 47/100** (OPINION; the critic says it holds within about 5 points). That puts it level with B22 (wholesale, 48) and below B5 (51), B20 (newsletter sponsors, 58) and B13 (TikTok live, 60).

**What's genuinely good:**
- It is built and billable (CLAIMED).
- It comes from a pain you measured yourself: 3 to 5 hours a week of chasing (CLAIMED).
- Of the 8 applicant tracking systems checked, **none** lets interviewers type free-text feedback into Slack and get a scorecard.
- **Probe threading** (passing interviewer 1's concerns to interviewer 2 inside Slack) was found nowhere else.

**What's weaker than your notes say:**
1. **Competition.** "No direct competitor" holds only in the narrowest sense.
   - Ashby already has the whole feedback form inside Slack, a Slack assistant and AI auto-fill.
   - Lever bought Pillar. Zoom bought BrightHire.
   - Teamtailor, Pinpoint and Screenloop bundle AI interview notes or AI scorecards into the price of their ATS. Screenloop's pitch is almost word for word Chase's.
   - Interviewsly is already listed in the Slack App Directory with interview feedback sharing.
   - Scribbl sells "bot-free" notetaking, which blurs your "no recording bot" message.
2. **Market size.** "93,000 paid Slack orgs, about £111M ARR" has no source. Slack's last published figure was 169,000 paid customers in 2021. A realistic market at £39 to £79 a month is roughly **2,000 to 4,500 organisations, about £1M to £4M a year in total** (OPINION).
3. **App Directory.** The listing could not be found. Slack now requires **10 active workspaces before you can apply**, and those must stay active through up to 12 weeks of review.
4. **Traction.** The public evidence of pull is almost nil. Nudge **did launch on Product Hunt: 0 upvotes, 1 comment, #32 on the day** ([Hunted Space](https://webmail.hunted.space/product/nudge-interview-feedback-in-60-seconds)). No Companies House record for Northwall Technologies came up in search, and there are no reviews or customer logos. Search results for "Nudge Slack app" are dominated by **Nudge Security**, which holds a US "NUDGE" trademark.
5. **Your insider edge cuts both ways.** Per this vault's CLAUDE.md, NALA runs **Workable plus Metaview**. The Workable company you know best chose the recording route. (Selling Nudge to NALA would be a conflict anyway.)

**Biggest risk that isn't about the market:** Nudge grew out of **Chase, a bot you built at NALA as Head of People**. Under UK law, work made "in the course of employment" can belong to the employer (Patents Act s39; Copyright, Designs and Patents Act s11). A short signed waiver from NALA is the most valuable document Nudge could have (not legal advice; section 6).

**Outlook (OPINION, section 7).** If Nudge has **0 paying customers today**:
- about 70-80%: it stalls;
- about 15-25%: it becomes a niche lifestyle SaaS on £14k-142k a year within 2 to 3 years;
- low single digits: £1m within 5 years while you stay part-time.

If it already has **5 or more paying customers**, the lifestyle case rises to roughly 30-40%.

**Recommendation:** keep going only as a **time-boxed sales test, with a hard kill date of 31 March 2027**, on a narrower pitch: *"60-second interview feedback for the interviews nobody records (in person, phone screens, recording-shy teams), in Slack, with any ATS"*. Don't build the "hiring intelligence layer"; that is where Metaview raised $35M and Zoom bought BrightHire. Get the NALA waiver first.

---

## 2. Method 1: the stage 1 kill checks

The same 7 checks as `../checks/_brief.md`, plus the stage 2 eighth check (fits your limits).

| # | Check | Result | Evidence (all seen 2026-10-04 in search results) |
|---|---|---|---|
| 1 | Someone pays for this, or a worse version, today? | **PASS for the category, UNCLEAR for Nudge** | Metaview Pro costs about $50-60 per user a month (CLAIMED, third-party pricing pages, e.g. [toolradar](https://toolradar.com/tools/metaview/pricing)). Ashby sells its AI Notetaker as a paid add-on ([Ashby](https://www.ashbyhq.com/add-ons/ai-notetaker)). Screenloop sells AI scorecards ([Screenloop](https://www.screenloop.com/blog/introducing-ai-scorecards)). NALA uses Metaview (vault CLAUDE.md; whether it pays is not known, as Metaview has a free tier). Nudge's own paying customers: not found. Its Product Hunt launch drew 0 upvotes. |
| 2 | Inputs free, output easy to make? | **UNCLEAR** | The input is the interviewer's own thoughts, which is good. But "free text in, AI scorecard out" is already documented as a weekend build: [n8n template](https://growwstacks.com/workflows/audit-interview-feedback-and-report-via-slack-with-gpt-4o-mini-and-google-sheets/), [custom-GPT guide](https://chatprd.ai/how-i-ai/workflows/how-to-improve-interview-feedback-consistency-with-a-custom-gpt), [Cassidy AI](https://docs.cassidyai.com/use-cases/recruiting/interview-scorecard-summarizer). The moat is the workflow (chasing, writing back to the ATS, probe threading), not the AI. |
| 3 | Rivals selling it at a similar price? | **UNCLEAR, leaning FAIL** | No packaged Slack free-text-to-scorecard product was found at £39-79. But the same job is done at or below that price: Metaview's free tier (25 conversations a month, CLAIMED); Ashby's in-Slack forms at no extra cost ([Ashby](https://www.ashbyhq.com/product-updates/improvements-to-feedback-reminders)); GoodTime AI-Assisted Scorecards ([GoodTime](https://support.goodtime.io/hc/en-us/articles/26352216584727)); Teamtailor Co-pilot and Pinpoint AI scorecards bundled into the ATS (CLAIMED, [Teamtailor](https://www.teamtailor.com/en/content-hub/discover-how-teamtailors-new-ai-feature-co-pilot-can-improve-your-recruitment-today/), [Cronofy/Pinpoint](https://www.cronofy.com/case-studies/pinpoint-interview-scheduling-ai-notetaking)). Interviewsly is on the Slack App Directory ([Slack](https://slack.com/apps/AUNQK1L5D-interviewsly)). Convo's "Slack to Greenhouse" page looks like a generic notetaker SEO page running through Zapier or Make, not a direct rival (critic, OPINION). |
| 4 | Could a big company switch it on free? | **FAIL against the whole market. UNCLEAR in the recommended niche** | Ashby has the in-Slack form, a Slack DM assistant ([Ashby Assistant](https://www.ashbyhq.com/product-updates/ashby-assistant-in-slack)) and AI auto-fill ([Ashby](https://www.ashbyhq.com/product-updates/ai-notetaker-auto-fill)). Lever's AI Interview Companion is ex-Pillar ([Lever](https://lever.co/solutions/ai-interview-companion)). Zoom bought BrightHire ([Zoom](https://www.zoom.com/en/blog/zoom-acquires-brighthire/)). In the niche, none of Workable, BambooHR, HiBob, Teamtailor, Pinpoint, Recruitee, Personio or JazzHR was found offering capture in Slack. Workable's Slack integration is an open beta that sends notifications ([Workable](https://resources.workable.com/backstage-at-workable/integration-with-slack)). |
| 5 | Licence or site rules? | **PASS on licence, UNCLEAR on rules** | No licence needed. Slack Marketplace: 10 active installs before you can apply, up to 12 weeks of review ([Slack changelog 2026-09-01](https://docs.slack.dev/changelog/2026/09/01/slack-marketplace-install-requirement)). Unlisted apps: 1 request a minute on history reads ([Slack changelog 2025-05-29](https://docs.slack.dev/changelog/2025/05/29/rate-limit-changes-for-non-marketplace-apps)). No training LLMs on Slack data ([Slack dev policy](https://docs.slack.dev/changelog/2024/12/10/dev-policy-update)). Likely EU AI Act high-risk from 2 Dec 2027 if sold into the EU (OPINION, section 6). |
| 6 | First 10 buyers reachable online? | **UNCLEAR** | The channels exist: People Geeks (about 44,900 members, per a search snippet), the RecOps Slack community (run by Ashby), Recruiting Brainfood, your HR-leaders newsletter, LinkedIn content. The friction: a buyer's Slack admin must approve an unreviewed AI app that reads candidate feedback. The Product Hunt launch shows passive launch channels won't do it. |
| 7 | Free AI does it within 2 years? | **FAIL for Business+ customers** | Slack Business+ has included Slackbot as an AI agent and AI workflow steps at no add-on cost since June 2025 ([Slack](https://slack.com/blog/news/june-2025-pricing-and-packaging-announcement)). This only covers firms on Business+; the plan mix of 10-150-person firms is not known. What a do-it-yourself build won't easily give: persistent chasing, ATS write-back, probe threading. |
| 8 | Fits your limits? | **PASS, at a cost** | It is built and sells async. But B2B SaaS that handles candidate data brings support, security questionnaires and data processing agreements (DPAs). |

**Stage 1 verdict: would not pass as a new idea** (fails checks 4 and 7). It sits with O16 (shortlisting) and O17 (interview-fraud checks), for the same reason: incumbents are shipping the feature. Two things set it apart from those openings:
- it **already exists**, so testing costs only selling time;
- you have a real insider edge (with the NALA counter-example noted above).

---

## 3. Method 2: the millionaire playbooks lens

| Stage 2 question | Nudge | What the 84 cases say |
|---|---|---|
| **Which playbook?** | PB6 (vertical tool from your own job), sold through PB3 (Slack as the marketplace), with some PB2 (riding new AI abilities). | PB6: 6 cases, 2 verified, typically 3 to 5 years. PB3 for apps: "low" money, about 3.5 years (`../millionaires/playbooks.md`). |
| **Head start?** | Rare domain skill and day-job insight. Your HR-leaders newsletter (size unknown) doesn't appear to be used for Nudge yet. | 14 of 49 known cases had a rare skill and 7 built from their day job, but **audience was the biggest single factor (20 of 49)**. That is the head start you aren't using. |
| **Wave ridden?** | Cheap AI structuring (pattern P3) and a hiring funnel under strain (pattern P4). | 68 of 84 rode a wave. The AI file found windows close in 6-18 months. **That has happened here**: Ashby, Lever, Zoom, Teamtailor, Pinpoint and Screenloop all shipped or bought AI feedback in 2025-26. |
| **First-customer channel?** | Product Hunt (0 upvotes). Nothing else visible. | Where known: audience, referrals or a platform's algorithm. Launch sites: 0 stated. Paid ads: 1. Cold outreach: 0. |
| **How many tries?** | Nudge comes after Chase, about 21 tools and a dog-groomer SaaS (CLAIMED, your notes). | Many attempts is normal (Photo AI claims "70"). |
| **Base rate** | The median TrustMRR product makes **$169 a month** (VERIFIED within sample). Bootstrapped Slack apps found peak at $150k-450k a year (CLAIMED). | Base case: under $1k a month in year one (OPINION). |
| **Stayed part-time?** | Yes, and plans to. | **None of the scaled spin-outs did** (Slack, Recruitee, Teamtailor; `comparables_base_rates.md` section 5). |

**What it takes, in numbers** (REASONABLE GUESS: arithmetic on your prices, at about $1 = £0.75):
- **$10k a month** (about £7,500) needs **100-200 paying workspaces**.
- **$1m a year** (about £750k) needs **800-1,700**.
- At the claimed SMB churn of 3-7% a month, you'd have to sign roughly 1.5 to 2 times those numbers.
- No bootstrapped, part-time, solo Slack app was found that got there. The two Slack-app exits found (Halp to Atlassian, Troops to Salesforce) were venture-backed.

---

## 4. Score on the stage 2 scale (OPINION)

| Criterion | Max | Nudge | Why |
|---|---|---|---|
| Proof people pay | 25 | 10 | The category pays (Metaview, Ashby add-on, Screenloop). No evidence that Nudge has paying customers, and the Product Hunt launch drew no pull. |
| How empty the field is | 20 | 9 | In the recommended niche, no ATS was found doing capture in Slack. But Teamtailor and Pinpoint bundle recording-based AI notes, Screenloop sells the same anti-chasing pitch, and Interviewsly is on the Slack App Directory. |
| Timing | 20 | 8 | The AI window opened in 2023-24, and incumbents closed most of it in 2025-26. EU AI Act compliance cost from Dec 2027. |
| Size of prize | 10 | 3 | A serviceable market of about £1-4M a year in total (OPINION). |
| Speed to first sale | 10 | 7 | Built, with Stripe live (CLAIMED). Slowed by approving an unlisted app and buyers' security questionnaires. |
| Fit with your limits | 15 | 10 | Uses your expertise and build skill. Costs: support load, the NALA IP question, conflicts. |
| **Total** | 100 | **47** | Level with B22 (48); below B5 (51), B20 (58) and B13 (60). |

---

## 5. Your claims, tested

| Your claim (2026-07-08 notes) | Verdict | Evidence |
|---|---|---|
| "No direct competitor in Slack-native free-text capture" | **Narrowly true, practically misleading** | No packaged product found. But Ashby (in-Slack forms plus AI auto-fill), Slack's bundled AI workflows, and recording-based AI scorecards bundled by Teamtailor, Pinpoint and Screenloop all compete for the same job. Interviewsly is on the Slack App Directory. |
| "Metaview and BrightHire require recording bots" | **True** | Metaview's Slack integration "only supports Sourcing workflows" ([Metaview support](https://support.metaview.ai/slack.md)). Recording-free capture is your real point of difference. Lead with *recording-free*, not *bot-free* (Scribbl already sells "bot-free"). |
| "Every ATS vendor adds Slack notifications assuming the problem is awareness" | **Out of date** | Ashby and Lever have moved to capture and AI drafting. Screenloop markets "eliminates the need to hunt down hiring managers for their interview feedback". |
| "TAM: 93,000 paid Slack orgs, about £111M ARR" | **Unsupported** | Source not found. Slack's last published figure was 169,000 paid customers in 2021 ([ITPro](https://itpro.com/marketing-comms/business-communications/359769/slack-reports-almost-40-q1-growth-as-salesforce)). A serviceable market of about 2,000-4,500 organisations, or £1-4M ARR (OPINION; working in `footprint_platform_legal.md` section 3). |
| "Listed in the Slack App Directory" | **Not found** | No Marketplace listing came up in search. The 10-active-install rule makes a current listing unlikely unless you already have 10 active workspaces. Check and screenshot it. |
| "Chase cut chasing from 3-5 hours a week to zero" | **Plausible, one site only** | Your own measurement at one company, and it's NALA data (section 6). |

---

## 6. Risks that aren't about the market

1. **IP origin (top priority).** Chase was built at NALA, by its Head of People, to fix NALA's hiring. Any reused Chase code, prompts, designs or NALA data could belong to NALA under s39 / s11 or under your contract's IP clause. Questions for an employment/IP lawyer and for NALA:
   - What does your IP assignment clause cover?
   - Has Nudge been disclosed to NALA and consented to in writing?
   - Can you show a clean rebuild (dated repos, your own devices and accounts)?
   - Will NALA sign a short waiver?
   - Is NALA a customer, pilot or reference?
   - (Not legal advice.)
2. **EU AI Act.** AI used to "evaluate candidates" counts as high-risk from 2 Dec 2027 ([NatLawReview](https://natlawreview.com/article/eu-digital-omnibus-ai-enters-force)). You could argue the Article 6(3) exemption ("improves the result of a previously completed human activity"), but that argument weakens with every AI-generated score or probe suggestion (OPINION). This only applies to EU sales.
3. **UK ICO.** The ICO's "Recruitment Rewired" report (31 Mar 2026, [ICO](https://ico.org.uk/about-the-ico/what-we-do/recruitment-rewired/)) found human review is often rubber-stamping. A one-click confirm is exactly what the ICO will probe. Log how often interviewers edit the AI draft: it is compliance evidence and a product metric at the same time.
4. **Data processor duties.** You need a DPA, a sub-processor list (LLM provider, Supabase, Vercel, Stripe, Slack), no-training and zero-retention terms from the LLM provider, and a DPIA template customers can reuse. A lawyer-reviewed pack is a guessed £2k-8k (REASONABLE GUESS, no price found). Heavy for a £39 product.
5. **Slack platform.** Slack has changed its rules for third-party apps at least three times since December 2024: an LLM data policy (Dec 2024), rate limits for unlisted apps (May 2025), and a Marketplace install requirement (Sep 2026). Links are in check 5. **Our two research files disagree** on when the rate limit reached existing installs (2 Sep 2025 vs 3 Mar 2026), though both cite the same Slack page. Open the changelog to settle it; either way it applies now. Design around the Events API: store replies when they arrive and avoid reading message history while unlisted.
6. **Name.** Nudge Security owns the search results and holds a US trademark ([Justia](https://trademarks.justia.com/owners/nudge-security-inc-5114852)). Run a UK/EU trademark search (UKIPO, EUIPO, classes 9 and 42) before spending more on the brand.
7. **Time.** A full-time job, a clothing label, a newsletter and three stage 2 bets all compete for the same evenings.

---

## 7. Outlook (OPINION)

| Scenario | If 0 paying today | If 5+ paying today | What it looks like at 12-36 months | Signs it's happening |
|---|---|---|---|---|
| **Stall** | about 70-80% | about 50-60% | Under 10 paying workspaces by mid-2027. Free or bundled tools look "good enough". Nudge becomes a portfolio piece and strong TPO content. | Pilots don't convert; "our ATS records interviews"; Slack admins block the install. |
| **Niche lifestyle SaaS** | about 15-25% | about 30-40% | 30-150 workspaces at £39-79 = **about £14k-142k ARR** (arithmetic) in 2-3 years. Listed on the Marketplace. Sold for interviews nobody records. | 10 workspaces still active at day 28; listing approved; churn under 3% a month; buyers cite probe threading. |
| **Bought as a feature** | under 5% | under 10% | An ATS without a capture loop in Slack (e.g. one of the 8 checked) buys it. No price evidence: the Slack-app exits found were venture-backed. | An integration-directory listing; inbound from an ATS product team. |
| **£1m (sales or sale price) within 5 years, part-time** | low single digits | low single digits | Needs 800-1,700 paying workspaces, or a strategic sale. | Not expected on current evidence. |

---

## 8. What to do (What / So What / Now What / When)

| # | What | So what | Now what | When |
|---|---|---|---|---|
| 1 | The paying-customer count isn't in your notes | It's the number that decides which column of the outlook applies | Write down: active workspaces, paying workspaces, pilots, feedback captured per week, edit rate | This week |
| 2 | Nudge grew from Chase at NALA | An unclear IP origin blocks any sale or investment and creates employment risk | Read your contract. Disclose Nudge to NALA in writing and ask for a short waiver. No NALA data or reference without sign-off | Before the next sales push |
| 3 | The pitch is too broad and the TAM unsourced | Ashby/Lever shops already have most of this, and Teamtailor/Pinpoint/Screenloop bundle recording AI; £111M costs you credibility | Repitch: "feedback for the interviews nobody records: in person, phone screens, recording-shy teams; in Slack; any ATS; for 10-150-person firms". Sell feedback within 24 hours and hours saved, not "AI". Drop £111M | Next 2 weeks |
| 4 | The Marketplace needs 10 *active* installs, held through review | A listing lifts the rate limits and brings discovery; nothing found says installs must be paid, so free pilots very likely count (REASONABLE GUESS from the rule's wording in a search snippet) | Run 90-day free pilots (not 30-day ones, so they stay active through up to 12 weeks of review). Apply as soon as 10 are still active at day 28. Treat the 10 paying customers as a separate gate | Apply by 31 Dec 2026 |
| 5 | Audience is the biggest single success factor, and you aren't using yours for Nudge | The Product Hunt launch shows passive launches won't bring buyers | Publish the TPO seeds marked "hot" (the "bot that chases hiring managers" piece); one disclosed newsletter mention; post in People Geeks | Oct-Nov 2026 |
| 6 | The "hiring intelligence layer" is where the money has been raised | You'd be fighting Metaview ($35M Series B) and Zoom | Don't build the dashboard or intelligence layer until 10 customers pay. Make probe threading the hero feature | Ongoing |
| 7 | Compliance and the name | Buyers will ask; EU high-risk rules from Dec 2027 | Ship a DPA, a sub-processor list and LLM no-training terms. Log edit rates. Run a UKIPO/EUIPO search | Before the first paid deal with a security review |
| 8 | No kill date exists | Without one, Nudge eats the evenings the stage 2 bets need | **Kill date: 31 March 2027** (leaves room for Marketplace review). Stop building if fewer than **10 paying workspaces**, listing or not. Then keep it as a case study and content engine, or offer the code and customers to an ATS | Set now |

### The two-week test (same format as the stage 2 cards)
- **Spend:** £200 of LinkedIn ads to Heads of People and Talent at UK and Irish firms of 20-200 staff. Add a sign-up question: "Do you record your interviews?"
- **Outreach:** 30 personal DMs to HR peers who aren't NALA suppliers, plus one disclosed newsletter mention.
- **Offer:** a free 90-day pilot that converts to £39 or £79 a month.
- **Pass:** 10 workspaces installed within 14 days **and** still active at day 28 (this unlocks the Marketplace application), **and** 3 converting to paid by day 45 (by agreeing to early billing).
- **Fail:** fewer than 5 installs in 14 days, or 0 paid by day 45.
- **Cost:** £200 and about 15 hours.

### How Nudge fits the stage 2 bets
Nudge sits in the **newsletter cluster**: the same buyers (HR leads) and the same channel (your list and your TPO content).
- B20's sponsor exclusion list must rule out Nudge's rivals.
- Every Nudge mention in the newsletter must say you're the founder.
- Don't run Nudge's test in the same fortnight as B20's. Pair it with B13 (TikTok live), which shares nothing with it.

---

## 9. Sources

All seen 2026-10-04 in search results, not on the original page:
- Competitors: links in `competitors.md`.
- Footprint, platform, market and legal: `footprint_platform_legal.md`.
- Comparables and base rates: `comparables_base_rates.md`.
- Critic: `critic.md` (niche check across 8 ATSs, the Product Hunt launch, Screenloop, Interviewsly, Scribbl, Convo).

Founder facts (CLAIMED, founder):
- `TPO/2026-07-08 - The friction isnt forgetting its that giving feedback is annoying.md`
- `TPO/2026-07-08 - I built a bot that chases hiring managers so I never have to again.md`
- `TPO/2026-07-08 - I built 21 tools and I am not an engineer.md`
- NALA's ATS and Metaview use: the vault's `CLAUDE.md`.
