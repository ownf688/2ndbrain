# Round 8, generator Q: places where a paying comparable AND unserved buyers are visible at once

Generated 2026-10-04. Research only, no scores. 14 of 14 searches used: **SEARCH LIMIT HIT**. Money labels: VERIFIED = Stripe-linked figure (TrustMRR) or third-party checked; CLAIMED = seller or press says so. All figures are from search snippets; the pages themselves were not opened (see method problems).

## Result in one line

**0 ideas meet both tests.** I found no case where a comparable seller with cited revenue AND at least 3 dated buyer posts asking for the missing thing were both visible. Per the brief, ideas missing either half are dropped. Below: what was tried, what each lead showed, and why it was dropped, so later rounds do not repeat the same searches.

## Method problems (these matter for the next round)

1. **TrustMRR cannot be read directly.** A WebFetch of trustmrr.com was refused: "Access to trustmrr.com is blocked by the network egress proxy" (2026-10-04). TrustMRR data only comes through search-engine snippets, and those return a few listings per query, mostly anonymised ("Confidential Startup", "Hidden Business"), with no category filter.
2. **The search tool does not bring up Reddit threads, Canny/Featurebase boards or G2/Capterra review text.** Four searches built to find "is there an X for Y" or "doesn't work in the UK" posts returned SEO listicles, vendor blogs or unrelated pages (searches 1, 3, 4, 13 below). So the "buyers asking" half could not be counted from the open web with this tool.
3. **Result:** this angle needs a different tool to be tested properly: direct Reddit search or the Reddit API, a G2/Capterra review export, Shopify App Store review pages, or a TrustMRR export (Apify scrapers for TrustMRR exist: https://apify.com/publicmoney/trustmrr-scraper, seen 2026-10-04; cost not checked). OPINION: a round that pulls the full TrustMRR list (about 840+ startups per earlier rounds) and then checks the reviews and forums of the 20-30 small, niche ones would test this angle properly. Doing it with 14 general web searches did not work.

## Leads checked and dropped

### L1. UK visa-sponsored job board (candidate side)
- **Comparable:** SponsoredJobs, "the only UK job board built exclusively for visa seekers", 17 paying customers, **$54 MRR, $649 ARR (VERIFIED, TrustMRR snippet)**, priced £2.99/month billed annually (https://trustmrr.com/startup/sponsoredjobs, seen 2026-10-04).
- **Rivals seen in the same search:** Hunt UK Visa Sponsors (https://huntukvisasponsors.com), VisaPath (lists "125,572 sponsor companies", https://visapath.co.uk/search?page=4608), ApplyWave (https://applywave.app). So the field is crowded, not unserved.
- **Buyer posts asking for a missing version:** not found.
- **Why dropped:** the comparable's revenue is tiny ($54 MRR, which is prize 0-1), there are 3+ rivals, and the free government sponsor register is the raw material (repeats the check 2 and 3 pattern). There is also a perception issue for a Head of People (as with B9).

### L2. Shopify pre-order app for small fashion labels (clothing-label fit)
- **Comparable:** PreProduct, London, founded 2020 by Oli and Eliza; priced free + 5% of pre-order revenue, $29.99, $59.99 and $259.99/month; 4.9 rating with about 100 reviews (https://apps.shopify.com/preproduct, https://preproduct.io/about, seen 2026-10-04). **Revenue: not found.**
- **Buyer posts asking for a missing segment or feature:** not found (search 12 returned only the app listing and pricing pages).
- **Why dropped:** no comparable revenue, no gap evidence. Pre-order apps are a crowded Shopify category, and B21 (pre-order drops for the own label) already covered the user-side use.

### L3. Print-on-demand apparel store (clothing-label fit)
- **Comparable:** an unnamed TrustMRR-listed POD clothing store, **$26k 30-day revenue, $441k total (VERIFIED per TrustMRR snippet; listing name not shown)**; a Southwestern POD apparel brand with $956k lifetime revenue (CLAIMED, Flippa listing https://flippa.com/13287007); Snow Milk, Brooklyn streetwear, $278k/year (CLAIMED, CNBC, https://www.cnbc.com/video/2023/05/24/how-snow-milk-brings-in-money-selling-expensive-t-shirts-in-nyc.html). All seen 2026-10-04.
- **Buyers asking for something these sellers do not do:** not found. These are consumer brands, not tools, so "users asking for a missing version" does not apply in the same way.
- **Why dropped:** half (b) exists, half (a) does not. It also repeats the own-label channel bets (B12, B13, B21-23, E2) that were already killed or scored low.

### L4. HR, employment-law and payroll help for disabled people who employ personal assistants (PAs) through council direct payments
- **Why it looked promising:** these are the least HR-capable employers in the UK, and ERA 2025 changes apply to them too. PA Pages published "Employment Rights Act 2025: what direct payment employers need to know"; day-one SSP and removal of the lower earnings limit from 6 April 2026 (https://pa-pages.org/news/employment-rights-act-2025-what-direct-payment-employers-need-to-know/, seen 2026-10-04).
- **Free supply found:** councils and funded charities already give the help. Payroll services "can be included in your Personal Budget up to a set amount", and free information, advice and guidance comes from user-led organisations such as Independent Lives (same PA Pages snippet). Council employer handbooks are free (e.g. Leicestershire https://leicestershire.gov.uk/sites/default/files/2024-05/Employing-a-Personal-Assistant.pdf; East Lothian https://www.eastlothian.gov.uk/download/downloads/id/27056/personal_assistant_-_employers_handbook.pdf; Norfolk PA payroll https://www.norfolk.gov.uk/papay). All seen 2026-10-04.
- **Comparable seller with revenue:** not found. **Buyer posts asking for paid help:** not found.
- **Why dropped:** fails half (b) and half (a), and check 4 looks like a FAIL (the council or a funded charity supplies it free and pays for it from the budget). Not tested before in this hunt, so it is recorded here so it is not re-run.

### L5. Holiday accrual for irregular-hours staff inside Xero Payroll (UK)
- **Buyer signal:** a Xero Product Ideas post, "UK Payroll Holiday Fund Options", appears in both the payroll and small-business forums (https://productideas.xero.com/forums/967118-payroll-expenses/suggestions/45468799-uk-payroll-holiday-fund-options, seen 2026-10-04). Date, vote count and text: not read (snippet only). That is one post, not three.
- **Comparable with revenue:** not found.
- **Why dropped:** only one buyer post; no comparable. It also repeats the "formula work on the client's own data goes into the software that holds it" kill pattern (R7, R10, G5). Xero or a rota tool is the natural place for the fix.

### L6. Northern Ireland driving-test cancellation alerts (GB-style checker for the DVA)
- **Comparable:** GB cancellation-checker services exist (e.g. https://driving-test-cancellations-4all.co.uk, seen 2026-10-04). **Revenue: not found.**
- **NI buyer posts:** not found. The search returned old DVA COVID-era notices and the nidirect booking page (https://www.nidirect.gov.uk/services/change-cancel-or-view-your-practical-driving-test-online, seen 2026-10-04).
- **Why dropped:** no evidence for either half. There is also a ToS/automation risk on a government booking system, as in O30 (Vinted bans).

### L7. US-centric HR tools whose UK users ask for a UK version
- **Finding:** UKG Pro and Gusto are criticised for limited non-US localisation (rfp.wiki and Gartner snippets, https://www.rfp.wiki/hr-office/hcm-suites-1000-employee-enterprises/neocase/gusto, https://www.gartner.com/reviews/market/cloud-hcm-suites-for-1000-employees/vendor/ukg, seen 2026-10-04). But UK small-business HR is already served by UK-built tools: BreatheHR from £22/month for up to 10 staff, "UK-built for UK employment law" (https://whito.co.uk/tools/best-hr-software-uk/, seen 2026-10-04), plus CitrusHR, Access PeopleHR, Employment Hero and others in the same results.
- **Why dropped:** the gap is closed at the small-business end, so half (b) fails. CitoHR ($24k MRR, VERIFIED in earlier rounds) is the only HR comparable seen again, and its NI version was already killed (G1).

### L8. Companies House software-only accounts filing (checked before searching, to avoid a repeat)
- Already recorded as a dead trigger in round 3: the April 2027 P&L and software-only filing change was **paused in January 2026, with no new date** (round3_genG.md citing Rapid Formations). Not used.

## Why this angle came up empty (OPINION, built on the leads above)

1. **Where a comparable shows a niche product earning money, the niche is already crowded.** SponsoredJobs sits beside 3+ rivals. Pre-order apps and UK HR tools are mature Shopify and SaaS categories. When an indie earns enough to show on TrustMRR in an easy-to-copy category, other indies arrive (the same thing that killed ClaudeKit-style ideas in round 6).
2. **Where buyers are under-served, a public or charity body usually funds a free answer.** The PA employers in L4 are the clearest case in this round; R9, D3 and K10 were the same.
3. **Requests on public feature boards (Xero ideas) are requests to the incumbent.** The incumbent is the natural one to fill them, so they are weak proof of a gap for an outsider.
4. **Timing is still the hidden blocker.** Even a pair with both halves would need timing of 15 or more. Most dated triggers left in the next 12 months have been tested (ERA phases, MTD, PRS, ECCTA), and the Companies House filing date is paused. A pair found by this method would also need to sit in a wave that started in the last 12 months, and every such wave tested so far filled within months.

## Suggestion for round 9 (OPINION, no score)
Re-run this angle with access that this run did not have: (a) a TrustMRR export filtered to under $5k MRR, with B2B categories and a stated segment ("for dentists", "for Shopify", "for UK"); (b) for each of those, a direct check of the Shopify App Store or G2 review pages and Reddit search for "for [other segment]" requests over the last 12 months. Stop a candidate as soon as either half fails. Budget: about 1 hour of scraping, under £20 (Apify pricing not checked).

## Conflicts noted
- L1: Head of People selling a job-seeker product (perception, as in B9).
- L4: no payments or Nudge conflict, but work done for vulnerable adults funded by councils would need safeguarding care.
- None of the leads touched payments or remittance (employer conflict) or interview feedback (Nudge).

## Searches used (14)
1. UK-version app requests on Reddit (nothing usable). 2. TrustMRR HR/recruiting (CitoHR again). 3. "not available in the UK" alternative posts (nothing usable). 4. Canny UK payroll requests (found the Xero idea, L5). 5. TrustMRR UK landlords/trades (nothing). 6. TrustMRR clothing/POD (L3). 7. NI DVA cancellation checker (L6). 8. Indie Hackers "UK version" (nothing). 9. TrustMRR visa-sponsorship jobs (L1). 10. Direct-payment PA employers and ERA (L4). 11. G2/Capterra "not suitable for UK" (L7). 12. PreProduct revenue (L2). 13. TrustMRR HR sub-categories (nothing). 14. r/smallbusinessuk first-employee HR software (L7 supply).
