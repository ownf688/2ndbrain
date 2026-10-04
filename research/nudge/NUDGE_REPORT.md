# Nudge, scrutinised: both methods, findings and outlook

Research date: 2026-10-04. Research only. Inputs: your own Nudge notes in the vault (TPO seeds dated 2026-07-08), and three research files in this folder: `competitors.md`, `footprint_platform_legal.md`, `comparables_base_rates.md` (36 searches). The stage 1 and stage 2 methods are in `../REPORT.md` and `../BETS.md`.

> **Trust note.** This environment blocks nudgebot.ai, Companies House, Slack's docs and most vendor sites, so every external fact was **seen in a search result, not on the original page**. Facts about Nudge itself (pricing, Stripe, OAuth, App Directory, the time Chase saved) come from your own notes and are labelled **CLAIMED (founder)**. Your paying-customer count was not in the notes, so this report cannot say whether the "10 paying customers" gate has been passed. That number changes the verdict more than anything below.

---

## 1. The answer in one page

**Stage 1 verdict (the 7 kill checks): Nudge would be KILLED as a new opening.** It fails check 4 (a big company already ships most of it free) and check 7 (Slack's bundled AI lets a team rough it out themselves), and leans fail on check 3 (rivals). It dies for the same reason 37 of the 38 stage 1 openings died: the incumbent that already has the customer is shipping the feature.
- **Ashby** already lets interviewers fill in the whole feedback form inside Slack. It also has a Slack assistant you can DM, and AI that drafts feedback forms from notes.
- **Lever** bought Pillar and turned it into AI feedback drafting.
- **Zoom** bought BrightHire in November 2025.
- **Slack's Business+ plan** has included an AI agent and AI workflow steps since June 2025.

**Stage 2 verdict (playbooks and base rates): a legitimate playbook, run in the hardest version.** Nudge follows the "build what your own job lacked, sell it to peers" playbook (PB6). That is the playbook with the most verified wins in the stage 2 cases (Userflow, GoProposal, First Derivatives). But in those cases it took 3 to 5 years, and the founders went full-time once demand showed. Nudge sells through Slack (PB3), where bootstrapped apps tend to plateau:
- HeyTaco: about $440k a year (CLAIMED).
- Standuply: fell from $450k to $154k (CLAIMED).
- Geekbot: the only bootstrapped $1m Slack app found (CLAIMED), with a team of 17 or more.

**Score on the stage 2 scale: 47/100** (OPINION, working in section 4). That puts it level with B22 (wholesale your label, 48) and below B13 (TikTok live, 60) and B20 (newsletter sponsors, 58).

**What's genuinely good:**
- It is built and billable (CLAIMED).
- It comes from a pain you measured yourself: 3 to 5 hours a week of chasing (CLAIMED).
- Its two real differences are not yet copied:
  - it needs **no recording bot**, so it works for in-person interviews, phone screens and recording-shy teams;
  - **probe threading** passes interviewer 1's concerns to interviewer 2. No tool found does this live in Slack.

**What's weaker than your notes say:**
1. **"No direct competitor"** is true only in the narrowest sense. Ashby is one feature away.
2. **"93,000 paid Slack orgs, about £111M ARR"** has no source. Slack's last published figure was 169,000 paid customers in 2021. A realistic market at £39 to £79 a month is roughly **2,000 to 4,500 organisations, or £1M to £4M a year in total** (OPINION, working in section 5). Don't put £111M in any pitch.
3. **The Slack App Directory listing could not be found.** Slack now requires **10 active workspaces before you can even apply**, plus up to 12 weeks of review. Until then, unlisted apps are limited to 1 request a minute when reading message history.
4. **The public footprint is a single Hunted Space page.** No Companies House record for Northwall Technologies came up in search, and there are no reviews, logos or Product Hunt page. Search results for "Nudge Slack app" are dominated by **Nudge Security**, which holds a US "NUDGE" trademark.
5. **Your own employer pays for Metaview**, a direct rival in the category. It is listed as a connected system in this vault's CLAUDE.md. The category clearly pays, but Nudge hasn't displaced the incumbent where you have the most influence (and selling to NALA would be a conflict anyway).

**Biggest risk that isn't about the market:** Nudge grew out of **Chase, a bot you built at NALA as Head of People**, the role where fixing hiring is squarely your job. Under UK law, work made "in the course of employment" can belong to the employer (Patents Act s39; Copyright, Designs and Patents Act s11). A short signed waiver from NALA is the single most valuable document Nudge could have, and it must exist before any sale or investment (not legal advice, see section 6).

**Outlook (OPINION):**
- **About 60%:** stalls below 10 paying customers within 12 months.
- **About 30%:** becomes a niche lifestyle SaaS on £15k to £140k a year within 2 to 3 years.
- **Under 10%:** an ATS without its own Slack feedback loop buys it.
- **Low single digits:** £1m within 5 years while you stay part-time.

**Recommendation:** keep going, but only as a **time-boxed sales test with a hard kill date of 31 January 2027**, on a narrower pitch: *"60-second interview feedback in Slack, no recording, for 10-150 person companies on Workable, BambooHR, HiBob, Teamtailor or Pinpoint"*. Don't build the "hiring intelligence layer"; funded players own that ground. Get the NALA waiver first.

---

## 2. Method 1: the stage 1 kill checks

Same 7 checks as `../checks/_brief.md`, plus the stage 2 eighth check (fits your limits).

| # | Check | Result | Evidence (all seen 2026-10-04 in search results) |
|---|---|---|---|
| 1 | Someone pays for this, or a worse version, today? | **PASS for the category, UNCLEAR for Nudge** | The category pays: Metaview Pro about $50-60 per user a month (CLAIMED, third-party pricing pages, e.g. [toolradar](https://toolradar.com/tools/metaview/pricing)); Ashby sells its AI Notetaker as a paid add-on ([Ashby](https://www.ashbyhq.com/add-ons/ai-notetaker)); your own employer pays for Metaview (vault CLAUDE.md). Nudge's paying customers: not found and not in your notes. |
| 2 | Raw material free, output easy to make? | **UNCLEAR** | The input is the interviewer's own thoughts, which is good. But "free text in, AI scorecard out" is already a documented weekend build: an [n8n template](https://growwstacks.com/workflows/audit-interview-feedback-and-report-via-slack-with-gpt-4o-mini-and-google-sheets/), a [custom-GPT guide](https://chatprd.ai/how-i-ai/workflows/how-to-improve-interview-feedback-consistency-with-a-custom-gpt), a [Cassidy AI use case](https://docs.cassidyai.com/use-cases/recruiting/interview-scorecard-summarizer). The moat is the workflow (chasing, writing back to the ATS, probe threading), not the AI. |
| 3 | Rivals selling it at a similar price? | **UNCLEAR, leaning FAIL** | No packaged "Slack free text to scorecard" product was found at £39-79. But the same job is done at or below that price: Metaview's free tier (25 conversations a month, CLAIMED); Ashby's in-Slack feedback forms at no extra cost ([Ashby](https://www.ashbyhq.com/product-updates/improvements-to-feedback-reminders)); GoodTime AI-Assisted Scorecards ([GoodTime](https://support.goodtime.io/hc/en-us/articles/26352216584727)). One unchecked lead, Convo's "Slack to Greenhouse" page ([itsconvo.com](https://www.itsconvo.com/integrations/slack-to-greenhouse)), needs checking by hand. |
| 4 | Could a big company switch it on free? | **FAIL** | Ashby has the in-Slack form, a Slack DM assistant ([Ashby Assistant](https://www.ashbyhq.com/product-updates/ashby-assistant-in-slack)) and AI auto-fill with custom prompts ([Ashby](https://www.ashbyhq.com/product-updates/ai-notetaker-auto-fill)). Lever's AI Interview Companion is ex-Pillar ([Lever](https://lever.co/solutions/ai-interview-companion)). Zoom bought BrightHire in Nov 2025 ([Zoom](https://www.zoom.com/en/blog/zoom-acquires-brighthire/)). |
| 5 | Licence or site rules? | **PASS on licence, UNCLEAR on rules** | No licence is needed. But: Slack's Marketplace needs 10 active installs before you can apply, and review can take up to 12 weeks ([Slack changelog 2026-09-01](https://docs.slack.dev/changelog/2026/09/01/slack-marketplace-install-requirement)). Unlisted apps are capped at 1 request a minute on history reads ([Slack changelog 2025-05-29](https://docs.slack.dev/changelog/2025/05/29/rate-limit-changes-for-non-marketplace-apps)). Training an LLM on Slack data is banned ([Slack dev policy](https://docs.slack.dev/changelog/2024/12/10/dev-policy-update)). Likely EU AI Act "high-risk" if sold into the EU from 2 Dec 2027 (OPINION, section 6). |
| 6 | First 10 buyers reachable online? | **UNCLEAR** | The channels exist: People Geeks (about 44,900 members, per a search snippet), the RecOps Slack community (run by Ashby), Recruiting Brainfood, your own HR-leaders newsletter, LinkedIn content. The friction: a buyer's Slack admin has to approve an **unreviewed AI app that reads candidate feedback**. That is a hard first sale. |
| 7 | Free AI does it within 2 years? | **FAIL** | Slack Business+ includes Slackbot as an AI agent and AI workflow steps at no add-on cost since June 2025 ([Slack](https://slack.com/blog/news/june-2025-pricing-and-packaging-announcement)). A capable People Ops person can approximate the core loop with Workflow Builder today. What they won't easily get: persistent chasing, ATS write-back, probe threading, a dashboard. |
| 8 | Fits your limits? | **PASS, with a cost** | It is already built and sells async. But a B2B SaaS handling candidate data brings support, security questionnaires and DPAs, which are weekday-shaped work. |

**Stage 1 verdict: KILLED** (clear FAILs on checks 4 and 7). If someone pitched Nudge to the stage 1 process as a new idea, it would have been killed alongside O16 (shortlisting) and O17 (interview-fraud checks), and for the same reason. It differs from those openings in two ways that matter: it **already exists**, so the cost of testing is only selling time, and you have a **genuine insider edge** none of the openings had.

---

## 3. Method 2: the millionaire playbooks lens

| Stage 2 question | Nudge | What the 84 cases say |
|---|---|---|
| **Which playbook?** | PB6 (vertical tool from your own job), sold through PB3 (marketplace: Slack), with some PB2 (riding new AI abilities). | PB6 has 6 cases, 2 verified (Userflow, First Derivatives), typically 3 to 5 years. PB3 for apps: "low" money, about 3.5 years (`../millionaires/playbooks.md`). |
| **Head start?** | Rare domain skill plus day-job insight (you measured the pain). Audience: your HR-leaders newsletter, size unknown, apparently not yet used for Nudge. | 14 of 49 known cases had a rare skill and 7 built from their day job. But **audience was the biggest single factor (20 of 49)**, and that is the one you're not using. |
| **Wave ridden?** | Cheap AI structuring (pattern P3) and a hiring funnel under strain (pattern P4). | Riding a wave helped 68 of 84. But the AI file found windows close in 6-18 months, and 7 of 12 AI winners' features are now free elsewhere. **That has already happened here:** Ashby, Lever and Zoom shipped or bought it in 2025. |
| **First-customer channel?** | None visible publicly (one Hunted Space page). | Where known: audience, referrals, or a platform's algorithm. Paid ads 1 case, cold outreach 0. |
| **How many tries?** | Nudge comes after Chase, about 21 tools built, and a dog-groomer SaaS (CLAIMED, your notes). | Only 3 cases state it (Photo AI "70", Jenni AI 4). Many attempts is normal, not a warning sign. |
| **Base rate** | The TrustMRR median indie product makes **$169 a month** (VERIFIED within sample). Bootstrapped Slack apps found peak at $150k-450k a year (CLAIMED). | Base case under $1k MRR in year one (OPINION). |
| **Did they stay part-time?** | Yes, and plans to. | **None of the scaled spin-outs did.** Slack, Recruitee and Teamtailor went full-time once demand showed (`comparables_base_rates.md` section 5). |

**What it would take, in plain numbers (REASONABLE GUESS, arithmetic on your prices):**
- **$10k a month** (about £7,500-8,000) needs **100-200 paying workspaces**.
- **$1m a year** needs **800-1,700**.
- SMB SaaS loses a claimed 3-7% of customers a month, so you'd need to sign roughly 1.5 to 2 times those numbers.
- No bootstrapped, part-time, solo Slack app was found that got there. The two known Slack-app exits (Halp to Atlassian, Troops to Salesforce) were venture-backed.

---

## 4. Score on the stage 2 scale (OPINION)

| Criterion | Max | Nudge | Why |
|---|---|---|---|
| Proof people pay | 25 | 12 | The category pays (Metaview, Ashby add-on, your own employer). No evidence that Nudge has paying customers. |
| How empty the field is | 20 | 7 | Nobody does exactly this. Ashby is one feature away, and funded players (Metaview $35M Series B, BrightHire to Zoom) sit next door. |
| Timing | 20 | 8 | The AI window opened in 2023-24 and incumbents closed most of it in 2025. The EU AI Act adds a compliance cost from Dec 2027. |
| Size of prize | 10 | 3 | A serviceable market of about £1-4M a year in total (OPINION, section 5). |
| Speed to first sale | 10 | 7 | Built, with Stripe live (CLAIMED). Slowed by unlisted-app approval and buyers' security questionnaires. |
| Fit with your limits | 15 | 10 | Uses your expertise and build skills. Costs: support load, the NALA IP question, conflicts. |
| **Total** | 100 | **47** | Level with B22 (48); below B5 (51), B20 (58) and B13 (60). |

---

## 5. Your claims, tested

| Your claim (2026-07-08 notes) | Verdict | Evidence |
|---|---|---|
| "No direct competitor in Slack-native free-text capture" | **Narrowly true, practically misleading** | No packaged product found. But Ashby offers in-Slack forms, a Slack assistant and AI auto-fill; Slack's AI workflows are bundled; Convo is unchecked. |
| "Metaview and BrightHire require recording bots" | **True** | Metaview's Slack integration "only supports Sourcing workflows" ([Metaview support](https://support.metaview.ai/slack.md)). This is your real point of difference. |
| "Every ATS vendor adds Slack notifications assuming the problem is awareness" | **Out of date** | Ashby and Lever have moved to capture and AI drafting, not just reminders. |
| "TAM: 93,000 paid Slack orgs, about £111M ARR" | **Unsupported** | Source not found. Slack's last published figure was 169,000 paid customers in 2021 ([ITPro](https://itpro.com/marketing-comms/business-communications/359769/slack-reports-almost-40-q1-growth-as-salesforce)). A realistic serviceable market is about 2,000-4,500 organisations, or £1-4M ARR (OPINION, working in `footprint_platform_legal.md` section 3). |
| "Listed in the Slack App Directory" | **Not found** | No Marketplace listing came up in search; "Nudge" plus Slack returns Nudge Security. The 10-active-install rule makes a current listing unlikely unless you already have 10 active workspaces. Check and screenshot it. |
| "Chase cut chasing from 3-5 hours a week to zero" | **Plausible, single-site** | Your own measurement at one company. It's a good sales claim, but it's NALA data (see section 6). |

---

## 6. Risks that aren't about the market

1. **IP origin (highest priority).** Chase was built at NALA by its Head of People, to fix NALA's hiring. Any Chase code, prompts, designs or NALA data reused in Nudge could be NALA's under s39 / s11 or your contract's IP clause. Questions for an employment/IP lawyer and for NALA:
   - What does your contract's IP assignment clause cover?
   - Has Nudge been disclosed to NALA and consented to in writing?
   - Can you show a clean rebuild (dated repos, own devices, own accounts)?
   - Will NALA sign a short waiver?
   - Is NALA a customer, pilot or reference?
   - (`footprint_platform_legal.md` section 5. Not legal advice.)
2. **EU AI Act.** AI used to "evaluate candidates" is high-risk from 2 Dec 2027 (date moved by the Digital Omnibus). You could argue the Article 6(3) exemption, "improves the result of a previously completed human activity". That argument weakens with every AI-generated score, ranking or probe suggestion (OPINION). This only applies if you sell into the EU.
3. **UK ICO.** The "Recruitment Rewired" report (31 Mar 2026) found human review is often rubber-stamping. A one-click confirm is exactly what the ICO will ask about. Log how often interviewers edit the AI draft: it's your compliance evidence and a product metric at the same time.
4. **Data processor duties.** You need a DPA, a sub-processor list (LLM provider, Supabase, Vercel, Stripe, Slack), no-training and zero-retention terms from the LLM provider, and a DPIA template customers can reuse. A lawyer-reviewed pack is a guessed £2k-8k (REASONABLE GUESS, no price found). That's heavy for a £39 product.
5. **Slack platform.** Slack changed its terms twice in 18 months in ways that hurt small AI apps. Sources disagree on when the rate limit reached existing installs (2 Sep 2025 vs 3 Mar 2026); either way it applies now. Design around the Events API, store replies when they arrive, and avoid reading message history while unlisted.
6. **Name.** Nudge Security owns the search results and a US trademark. "Nudge" is also a common HR-benefits brand. Run a UK/EU trademark search (UKIPO, EUIPO, classes 9 and 42) before spending more on the brand.
7. **Time.** A full-time job, a clothing label, a newsletter, and now three stage 2 bets. Nudge competes with all of them for the same evenings.

---

## 7. Outlook

| Scenario | Probability (OPINION) | What it looks like at 12-36 months | Signs it's happening |
|---|---|---|---|
| **Stall** | about 60% | Under 10 paying workspaces by mid-2027. Ashby-style features and Slack AI make "good enough" free. Nudge becomes a portfolio piece and the source of strong TPO content. | Pilots don't convert. Prospects say "our ATS does this". Slack admins block the install. |
| **Niche lifestyle SaaS** | about 30% | 30-150 workspaces at £39-79 = **about £14k-142k ARR** (arithmetic) in 2-3 years. Marketplace-listed. Sold to 10-150-person firms on Workable, BambooHR, HiBob or Teamtailor. | 10 active installs reached, then listing approved; churn under 3% a month; probe threading cited as the reason people buy. |
| **Bought as a feature** | under 10% | An ATS without a Slack capture loop buys it. No price evidence: the Slack-app exits found (Halp, Troops) were venture-backed. | An ATS partnership or integration-directory listing; inbound from an ATS product team. |
| **£1m (sales or sale price) within 5 years, part-time** | low single digits | Needs 800-1,700 paying workspaces, or a strategic sale. | Not expected on current evidence. |

---

## 8. What to do (What / So What / Now What / When)

| # | What | So what | Now what | When |
|---|---|---|---|---|
| 1 | The paying-customer count isn't in your notes | It's the one number that can overturn this report | Write down: active workspaces, paying workspaces, pilots, weekly feedback captured, edit rate | This week |
| 2 | Nudge grew from Chase at NALA | An unclear IP origin blocks any sale or investment and could become a disciplinary issue | Read your contract. Disclose Nudge to NALA in writing and ask for a short waiver. Never use NALA data or NALA as a reference without sign-off | Before the next sales push |
| 3 | The pitch is too broad and the TAM is unsourced | Ashby/Greenhouse/Lever shops already have most of this; a £111M claim costs you credibility | Repitch: "60-second feedback in Slack, no recording, any ATS, for 10-150-person firms on Workable, BambooHR, HiBob, Teamtailor or Pinpoint". Sell the outcome (feedback within 24 hours, hours saved), not the AI. Drop the £111M line | Next 2 weeks |
| 4 | The Marketplace needs 10 *active* installs, not 10 *paying* ones | The listing lifts the rate limits and brings discovery; free pilots probably count towards the 10 (REASONABLE GUESS, check the rule's wording) | Run 10+ free 30-day pilots to unlock the Marketplace application. Treat the 10 paying customers as a separate gate | Apply by 31 Dec 2026 |
| 5 | Audience is the biggest single success factor and you're not using yours for Nudge | The cheapest channel you have | Publish the TPO seeds marked "hot" (the "bot that chases hiring managers" piece). One newsletter mention, with disclosure. Post in People Geeks | October-November 2026 |
| 6 | The "hiring intelligence layer" is where the money is raised | You'd be fighting Metaview ($35M Series B) and Zoom | Don't build the dashboard or intelligence layer until 10 customers pay. Make probe threading the hero feature | Ongoing |
| 7 | Compliance and the name | Buyers will ask; EU high-risk from Dec 2027 | Ship a DPA, sub-processor list and LLM no-training terms. Log edit rates. Run a UKIPO/EUIPO search | By first paid enterprise-ish deal |
| 8 | No kill date exists | Without one, Nudge eats the evenings the stage 2 bets need | **Kill date: 31 January 2027.** If there are fewer than 10 paying workspaces, stop building. Keep it as a case study and content engine, or offer the code and customers to an ATS | Set now |

### The two-week test (same format as the stage 2 cards)
- **Spend:** £200 of LinkedIn ads aimed at Heads of People and Talent at UK and Irish companies of 20-200 staff (ATS targeting is not possible on LinkedIn; filter in the sign-up form instead).
- **Outreach:** 30 personal DMs to HR peers who aren't NALA suppliers, plus one disclosed newsletter mention.
- **Offer:** a free 30-day pilot that converts to £39 or £79 a month.
- **Pass:** 10 workspaces installed and actively used within 14 days (unlocks the Marketplace application), **and** 3 converting to paid by day 45.
- **Fail:** fewer than 5 installs in 14 days, or 0 paid by day 45.
- **Cost:** £200 and about 15 hours.

### How Nudge fits the stage 2 bets
Nudge sits in the **newsletter cluster**: the same buyers (HR leads), and the same channel (your list and your TPO content). Two consequences:
1. **Content for Nudge and B20 sponsorship collide.** B20's sponsor exclusion list must rule out Nudge's rivals, and every Nudge mention in the newsletter must say you're the founder.
2. **Don't run Nudge's test in the same fortnight as B20.** Run B13 (TikTok live, no conflict) alongside Nudge instead.

---

## 9. Sources

All seen 2026-10-04 in search results, not on the original page:
- Competitors: links in `competitors.md`
- Footprint, platform, market and legal: links in `footprint_platform_legal.md`
- Comparables and base rates: links in `comparables_base_rates.md`

Founder facts: vault notes `TPO/2026-07-08 - The friction isnt forgetting its that giving feedback is annoying.md`, `TPO/2026-07-08 - I built a bot that chases hiring managers so I never have to again.md`, `TPO/2026-07-08 - I built 21 tools and I am not an engineer.md` (CLAIMED, founder).
