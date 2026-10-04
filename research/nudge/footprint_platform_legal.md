# Nudge: public footprint, platform risk, market size, legal

Research date: 2026-10-04. Covers stage-1 kill checks 1 (footprint), 5 (platform), 6 (regulation) and the TAM claim.

Method note: direct fetches of nudgebot.ai, hunted.space, docs.slack.dev, api.slack.com and Companies House were all blocked by the network proxy (EGRESS_BLOCKED). Everything below comes from search results. "Seen in search result, not checked at the original page" applies to every link unless stated. 12 of 12 searches used; budget now exhausted.

---

## 1. Public footprint

| Item | Finding | Label |
|---|---|---|
| nudgebot.ai | Could not load (proxy block). Pricing on the site not checked. | Not found |
| Hunted Space | Page exists: "nudge interview feedback in 60 seconds". Says a Slack bot DMs interviewers "How did it go?", AI structures free text, rolls up to a role page. Target: "teams of 10-150 people" hiring without a recruiting ops team. [hunted.space/product/nudgebot](https://www.hunted.space/product/nudgebot), [mirror](https://webmail.hunted.space/product/nudge-interview-feedback-in-60-seconds) | FACT (page exists); CLAIMED (description) |
| Northwall Technologies Ltd (Companies House) | Not found in search. Closest hits were unrelated: Northwall Services Ltd (SC482005, Aberdeen, incorporated 11 Jul 2014, formerly Northwall Software Ltd) and NWC Technologies Ltd. [ltds.uk SC482005](https://northwall-services-limited.ltds.uk/) | Not found. Incorporation date, number, accounts, officers: not found |
| Slack Marketplace listing | No Nudge interview app found in any Slack Marketplace search result. Search for "Nudge" + Slack returns Nudge Security's Slack integration instead. | Not found. Founder's "Slack App Directory listing" claim is UNVERIFIED |
| Product Hunt | Not found | Not found |
| LinkedIn (company page) | Not found | Not found |
| Reviews, customer logos, case studies | Not found | Not found |

OPINION: the footprint is a single Hunted Space page. No third-party evidence of customers, reviews or a Marketplace listing. Owen should check Companies House directly (the company may be very new, or registered under a slightly different name) and screenshot the Slack Marketplace page if it exists.

Note a positioning mismatch: Hunted Space says 10-150 staff; the brief's founder notes imply a broader market. Pick one.

### Name clashes and trademark risk

- **Nudge Security, Inc.** (US SaaS security) filed a "NUDGE" trademark on 25 Feb 2022 for SaaS cybersecurity software. [Justia trademarks](https://trademarks.justia.com/owners/nudge-security-inc-5114852). It also ships a Slack integration ([help.nudgesecurity.com](https://help.nudgesecurity.com/en/articles/8312724-configuring-nudge-slack-integration)), so "Nudge Slack app" searches return them first. FACT.
- **nudge.ai**: appears to be a sales/relationship-intelligence product (now linked to Affinity per a Nudge Security profile). [security-profiles.nudgesecurity.com](https://security-profiles.nudgesecurity.com/app/nudge-ai). REASONABLE GUESS, not confirmed.
- **Nudgify** (social-proof marketing tool) appears on Capterra comparisons. [capterra.in](https://www.capterra.in/compare/135003/193486/slack/vs/nudgify). FACT.
- **"Nudge Platform"** behavioural comms tool referenced on SharePoint Europe. [sharepointeurope.com](https://www.sharepointeurope.com/tag/nudge/). FACT (mention only).
- **Nudge Global** (financial wellbeing): not surfaced in search. Not found, but widely known in HR benefits; Owen should check, because HR buyers are exactly Nudge Global's buyers.
- "Nudge bot" is also a generic phrase (n8n templates, Upwork gigs for "Recruiting Nudge Bot").

OPINION: trademark conflict is moderate, search clash is high. Nudge Security holds a US "NUDGE" mark in a different class (security), so a direct infringement claim is unlikely for an HR tool, but a UK/EU trademark search (UKIPO, EUIPO) in Class 9/42 is needed before spending on brand. The bigger practical cost is discoverability: "Nudge Slack app" is owned by Nudge Security, and HR buyers will confuse it with Nudge Global.

---

## 2. Slack platform risk

FACTS (all seen in search results):
- **Rate limits for unlisted commercial apps.** From 29 May 2025, `conversations.history` and `conversations.replies` for non-Marketplace, commercially distributed apps dropped to **1 request per minute, max 15 objects per request**. Immediate for new apps and new installs; applied to existing installs on 2 Sep 2025. Marketplace apps and internal (single-workspace) apps are not affected. [Slack changelog 2025-05-29](https://docs.slack.dev/changelog/2025/05/29/rate-limit-changes-for-non-marketplace-apps), [Terms + FAQ](https://api.slack.com/changelog/2025-05-terms-rate-limit-update-and-faq)
- **API Terms update** effective 29 May 2025 (new apps) and 30 Jun 2025 (existing). Same sources.
- **LLM data rules.** Slack's developer policy prohibits using Slack data to train an LLM "under any circumstances"; Marketplace apps must follow a "zero-copy and zero LLM training" policy; RAG (send data at inference only) is the accepted pattern. [Dev policy update Dec 2024](https://docs.slack.dev/changelog/2024/12/10/dev-policy-update), [Understand AI apps in Slack](https://slack.com/intl/en-au/help/articles/33076000248851-Understand-AI-apps-in-Slack), [Marketplace guidelines](https://docs.slack.dev/slack-marketplace/slack-marketplace-app-guidelines-and-requirements/)
- **Marketplace entry bar has risen.** Search summary: apps must have **at least 10 installs on active workspaces** (active = used in last 28 days) and stay at 10+ throughout review; review clock can reach **12 weeks**. A dedicated changelog entry exists: [Slack Marketplace install requirement, 2026-09-01](https://docs.slack.dev/changelog/2026/09/01/slack-marketplace-install-requirement); see also [Marketplace review guide](https://docs.slack.dev/slack-marketplace/slack-marketplace-review-guide). This updates the earlier "5-10 workspaces, up to 10 weeks" finding. Exact wording not checked at the original page.

What this means for Nudge (OPINION):
- **Rate limits: low direct impact.** Nudge's core flow (bot sends DM, interviewer replies, bot reads its own DM thread) mostly uses events and `chat.postMessage`, not bulk history reads. But any feature that reads threads via `conversations.replies` (for example re-reading a long DM thread, or V2 probe threading across channels) is throttled to 1 call/minute per install while unlisted. Design around the Events API, store the reply on receipt.
- **Chicken and egg on Marketplace.** Nudge needs 10 active installs before it can even apply, then up to 12 weeks of review. So the first 10 customers must be won with an unlisted app, direct install links and a buyer's IT/Slack admin approving an unreviewed AI app that reads candidate feedback. That is a real sales friction for the exact gate the founder set ("first 10 paying customers").
- **Data use: manageable but must be documented.** Candidate feedback passes from Slack to an LLM provider. Nudge must not train on it, must state zero-retention terms with the LLM provider, and must publish this in its privacy policy and DPA. Slack reviewers will check.
- **Platform dependency.** Slack has changed terms twice in 18 months in ways that hurt small third-party AI apps. Single-platform risk is structural.

---

## 3. Market size: testing "93,000 paid Slack orgs"

FACTS:
- Slack's last published figure: **169,000 paid customers** (Q1 FY2022, reported mid-2021), up 39% YoY; 142,000 in Oct 2020. Slack stopped reporting separately after Salesforce closed the acquisition. [ITPro](https://itpro.com/marketing-comms/business-communications/359769/slack-reports-almost-40-q1-growth-as-salesforce), [Statista](https://statista.com/chart/22859/paid-customers-of-slack), [Slack Q3 FY2021](https://slack.com/intl/fr-fr/blog/news/slack-announces-strong-third-quarter-fiscal-year-2021-results)
- The founder's 93,000 figure: source not found. It is lower than Slack's own 2021 number, so it is not inflated on that dimension, but it is unsourced. CLAIMED.
- Count of companies running structured interviews or using a scorecard ATS: not found in this search budget.

Founder claim: 93,000 x ~GBP 100/month = ~GBP 111M ARR. CLAIMED. This treats every paid Slack org as a buyer, which is not a serviceable market.

OPINION: realistic serviceable market (show the working, every step is a guess):
1. Start: ~170,000+ paid Slack orgs (2021 fact; likely higher now, REASONABLE GUESS 200,000).
2. Keep companies of 20-500 staff that hire at least monthly and run panel interviews: REASONABLE GUESS 25-35% = 50,000-70,000.
3. Keep those using an ATS with scorecards (Ashby, Greenhouse, Lever, Workable, Teamtailor etc.): REASONABLE GUESS 50-60% = 25,000-40,000.
4. Remove those whose ATS already sends Slack feedback reminders and who are satisfied (Ashby, Greenhouse, Lever do this free per the 2026-10-03 pass; [Ashby update](https://www.ashbyhq.com/product-updates/improvements-to-feedback-reminders)): keeps perhaps a third with a felt pain = **8,000-13,000 orgs**.
5. Geography Nudge can actually sell to as a solo founder (UK + English-speaking, outbound-led): perhaps 25-35% = **2,000-4,500 orgs**.

At GBP 39-79/month, that is a serviceable market of roughly **GBP 1M-4M ARR**, and a realistic 3-year capture of 1-5% is **GBP 10k-200k ARR**. OPINION: fine as a side business or lifestyle SaaS, not a venture-scale market at this price point. The GBP 111M figure should not appear in any pitch.

---

## 4. Regulation and legal

### EU AI Act
- FACT: The Digital Omnibus got final Council approval on 29 Jun 2026, moving Annex III stand-alone high-risk obligations (including employment and recruitment) from 2 Aug 2026 to **2 Dec 2027**. Requirements are delayed, not removed. [CSA research note](https://labs.cloudsecurityalliance.org/research/csa-research-note-eu-ai-act-omnibus-vii-deadline-delay-20260/), [Cuatrecasas](https://www.cuatrecasas.com/en/global/labor-and-employment/art/digital-omnibus-on-ai-how-does-it-impact-employment-relations), [NatLawReview](https://natlawreview.com/article/eu-digital-omnibus-ai-enters-force)
- Annex III point 4 covers AI used for recruitment or selection, "in particular to... analyse and filter job applications, and to evaluate candidates". (Text of the Act, from knowledge; not re-checked today.)
- OPINION on whether Nudge is high-risk: **plausibly yes.** Structuring interviewer feedback into a scorecard that feeds a hire/no-hire decision is close to "evaluate candidates". Probe threading (telling interviewer 2 what to probe) actively shapes the evaluation. Article 6(3) offers an exemption for systems doing a "narrow procedural task" or that "improve the result of a previously completed human activity", and Nudge could argue it only reformats a human's own judgement. That argument weakens with every AI-generated score, summary, ranking or probe suggestion. Questions for a lawyer: does AI-produced scoring count as evaluation? Does probe threading? If high-risk, Nudge as "provider" faces risk management, documentation, logging, human oversight design and conformity assessment by Dec 2027. Only bites if Nudge sells to EU customers or candidates.

### UK
- FACT: Data (Use and Access) Act 2025 relaxed the old Article 22 near-ban; since **5 Feb 2026** automated decision-making is allowed with safeguards and a right to challenge. [DLA Piper Privacy Matters](https://privacymatters.dlapiper.com/2026/04/uk-ico-report-on-automated-decision-making-in-recruitment/), [Kingsley Napley](https://www.kingsleynapley.co.uk/our-insights/articles/recruitment-rewired-what-employers-need-to-know-about-automated-recruitment/)
- FACT: ICO **"Recruitment Rewired"** report, 31 Mar 2026, evidence from 30+ employers (Mar 2025 to Jan 2026). Key finding: human-in-the-loop is often not meaningful; rubber-stamping means the decision counts as automated. [ICO page](https://ico.org.uk/about-the-ico/what-we-do/recruitment-rewired/)
- FACT: ICO AI recruitment audit outcomes report, 6 Nov 2024: 296 recommendations, 42 advisory notes; themes: transparency to candidates, data minimisation, clear controller/processor roles, early DPIAs. Generative AI was out of scope. [ICO news](https://ico.org.uk/about-the-ico/media-centre/news-and-blogs/2024/11/ico-intervention-into-ai-recruitment-tools-leads-to-better-data-protection-for-job-seekers), [Hunton](https://www.hunton.com/privacy-and-cybersecurity-law-blog/uk-ico-publishes-report-on-audit-of-ai-recruitment-tools)
- OPINION: Nudge keeps a human writing and confirming the feedback, which is a good fit with "meaningful human involvement". The one-click confirm is the weak point: ICO would ask whether interviewers genuinely edit or just accept. Log edit rates; it is both a compliance artefact and a product metric.

### Data processor duties (OPINION, standard UK GDPR practice)
Nudge is a processor for the customer (controller). It needs: a DPA (Art. 28 terms), a published sub-processor list (LLM provider, Supabase, Vercel, Stripe, Slack), international transfer mechanisms (US LLM providers: UK IDTA/addendum or UK-US data bridge), a DPIA template customers can reuse, retention and deletion rules for candidate feedback, a candidate-facing transparency line customers can paste into privacy notices, and zero-retention/no-training terms from the LLM provider. Security questionnaires will come from every buyer with a security function.

### Licence
No licence found or expected for selling interview software in the UK or EU. FACT (absence in sources) + OPINION. Compliance cost is the real cost: estimate GBP 2k-8k for a lawyer-reviewed DPA, privacy policy and DPIA template (REASONABLE GUESS), plus ongoing time.

---

## 5. Founder-employment risk (not legal advice; questions to ask)

Generic UK law (from knowledge, not searched today):
- **Patents Act 1977 s39**: an employee's invention belongs to the employer if made in the course of normal or specifically assigned duties where an invention might reasonably be expected. [legislation.gov.uk s39](https://www.legislation.gov.uk/ukpga/1977/37/section/39)
- **Copyright, Designs and Patents Act 1988 s11(2)**: copyright in a work made by an employee "in the course of employment" belongs to the employer. Software code is a literary work. [legislation.gov.uk s11](https://www.legislation.gov.uk/ukpga/1988/48/section/11)
- Employment contracts usually widen this with IP assignment clauses (sometimes covering anything "relating to the business") and moonlighting/outside-interest clauses needing consent. Confidentiality duties also apply.

Specific risk here: Nudge grew out of **Chase**, an internal NALA bot the founder (Head of People, so hiring process is squarely his duty) built to fix NALA's feedback chasing. That makes it a strong candidate for "in the course of employment". Risk points: any Chase code, prompts, designs or data reused in Nudge; work done on NALA time or devices; NALA's hiring data used to test; the "3-5 hours/week saved" claim (NALA performance data used in marketing).

Questions to ask (an employment/IP lawyer and NALA):
1. What does my contract's IP assignment clause cover, and does it reach work outside hours?
2. Did I get written consent for outside business interests? Is Nudge disclosed to NALA?
3. Was any Chase code, prompt or design copied into Nudge? Can I evidence a clean-room rebuild (dated repos, separate accounts, own devices)?
4. Will NALA sign a short written waiver/assignment confirming it claims no rights in Nudge? This is the single most valuable document for any future investor or acquirer.
5. Is NALA (or its data) a customer, pilot or reference? If so, conflict of interest needs a sign-off from someone other than me.
6. Non-compete/non-solicit: do they restrict selling to NALA's contacts or approaching NALA colleagues?

OPINION: this is a stage-1 kill-level risk only if unaddressed. A signed NALA waiver resolves most of it cheaply.

---

## 6. First 10 buyer channels

| Channel | What it is | Link | Label |
|---|---|---|---|
| RecOps Community (Slack, run by Ashby) | Private, ATS-agnostic Slack of 1,000+ recruiting ops practitioners; requires a current/recent RecOps role. Note: hosted by an ATS that ships free Slack reminders. | [ashbyhq.com/community/recops](https://www.ashbyhq.com/community/recops) | FACT (seen in search) |
| RecOps newsletter (Substack) | Weekly recruiting ops roundup | [recops.substack.com](https://recops.substack.com/p/week-of-june-30th-2025) | FACT |
| Recruiting Brainfood (Hung Lee) | Leading TA newsletter, podcast, live shows | [recruitingbrainfood.podbean.com](https://recruitingbrainfood.podbean.com/e/brainfood-live-on-air-ep173-how-to-source-candidates-on-slack) | FACT |
| People Geeks (Culture Amp) | Slack/community of ~44,900 people/culture leaders | Seen in search summary; direct URL not captured | FACT (count from search snippet) |
| Indeed list of Slack communities for recruiting | Directory of more recruiting Slack groups | [indeed.com](https://indeed.com/hire/c/info/slack-communities-for-recruiting-and-hiring) | FACT |
| Hunted Space / Product Hunt | Launch traffic; Hunted Space page already exists | [hunted.space/product/nudgebot](https://www.hunted.space/product/nudgebot) | FACT |
| Founder's own network | Heads of People at VC-backed fintechs in London; NALA investor portfolios (only with care, see section 5) | n/a | OPINION |

Other names (Talent Ops communities, RecOps Collective consultancy, [designrush profile](https://www.designrush.com/agency/profile/recops-collective)) were found but are consultancies or not verified as buyer communities. OPINION: the best fit for the 10-150 staff target is Heads of People at Series A-B startups without a recruiting ops function, who are reachable through People Geeks, founder-led LinkedIn content and warm intros, rather than RecOps (whose members already have tooling and staff).

---

## Headline

- Footprint: one Hunted Space page; no Companies House record, Slack Marketplace listing, Product Hunt, LinkedIn or customer evidence found.
- Platform: Marketplace now needs 10 active installs and up to 12 weeks of review; unlisted apps get 1 req/min on history/replies. First 10 customers must be won unlisted.
- Market: 93,000 is unsourced; realistic serviceable market is about 2,000-4,500 orgs, GBP 1M-4M ARR (OPINION).
- Legal: likely EU AI Act high-risk by Dec 2027 if sold in EU; UK DUAA/ICO stress meaningful human review; Chase-at-NALA IP origin needs a written NALA waiver.
