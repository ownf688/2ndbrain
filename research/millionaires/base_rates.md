# Phase 2: The other side (base rates and documented failures)

Date seen for all links: 2026-10-03. 14 of 14 searches used (budget reached, not a tool limit). Most figures were seen in search-result summaries, not checked at the original page. Where a number comes from a blog or aggregator rather than the platform itself, it is labelled CLAIMED even if the blog says it is "data".

Labels:
- VERIFIED = platform-wide or official data (ONS, Stripe-verified datasets, platform-published numbers, a company's own filings).
- CLAIMED = blog, aggregator, founder post, survey of unknown method.

## Headline

- **UK, all businesses (VERIFIED, ONS):** 38.4% of new VAT/PAYE-registered businesses born in 2019 were still alive after five years. So about 6 in 10 are gone by year five. In 2024 the UK business death rate was 9.8% (280,000 deaths), birth rate 11.1% (317,000 births). Note: ONS only counts businesses registered for VAT or PAYE, which means the tiniest side projects (most of the user's peer group) are not even in this number, and their failure rate is almost certainly worse. Source: [ONS Business Demography 2024](https://www.ons.gov.uk/businessindustryandtrade/business/activitysizeandlocation/bulletins/businessdemography/2024), [gov.uk release](https://www.gov.uk/government/statistics/business-demography-2024).
- **Indie software (VERIFIED within its sample):** across 5,079 Stripe-verified projects on TrustMRR, median monthly revenue is **$169**. Top 25% make more than about $800/month, top 10% more than $10,000/month, top 1% more than $98,500/month. "Most products don't make any revenue at all." Source: [Indie Hackers analysis of TrustMRR](https://www.indiehackers.com/post/i-analyzed-5-079-stripe-verified-startups-f0f6bd053f). Caveat: this is only people proud enough to connect Stripe and list publicly, so the real median for all attempts is lower.
- **Rough rule from the evidence:** in every category with data, the typical outcome is somewhere between zero and pocket money, and the £1m outcome sits at or beyond the top 1%.

## By business type

### 1. Software and apps (SaaS)
- **Typical earnings:** median $169/month on TrustMRR (VERIFIED, self-selected sample, see above). Top 10% pass $10k MRR (MRR = monthly recurring revenue). Sales-tool products median $711/month (VERIFIED, same dataset).
- **Share reaching $1k MRR:** a synthesis of 423 public founder posts says about 70% of micro-SaaS products never cleared $1,000 MRR; a tracking of 487 Product Hunt SaaS launches over six months found 97.4% stayed under $1,000 MRR (both CLAIMED, method not checked). Source: [collab365 synthesis](https://spaces.collab365.com/posts/indie-saas-post-mortems-point-to-no-buyers-not-bad-code-utt3f3m2).
- **Share reaching $1m a year:** ChartMogul says about 50% of *monetising* SaaS companies that survive 10 years reach $1M ARR (annual recurring revenue). Top-quartile bootstrapped firms reach $1M ARR in about two years; the median bootstrapper takes over three years (VERIFIED as ChartMogul's own customer data, but heavily survivor-biased: you have to already be paying for a billing analytics tool and still be alive). Source: [ChartMogul SaaS Growth Report](https://chartmogul.com/reports/saas-growth-vc-bootstrapped/).
- **Failure:** the main failure mode in post-mortems is "nobody pays", not bad code (CLAIMED, collab365 synthesis).

### 2. AI tools
- **Typical earnings:** AI projects are 24.5% of the TrustMRR sample and have a median of **$156/month**, lower than the overall median (VERIFIED within sample). Source: [Indie Hackers TrustMRR analysis](https://www.indiehackers.com/post/i-analyzed-5-079-stripe-verified-startups-f0f6bd053f).
- **Failure:** blogs say about 3,800 AI startups shut between 2023 and early 2025 and another 1,800 in early 2026, and quote "McKinsey" putting survival for wrapper companies at about 3% over two years (CLAIMED, original sources not found; treat the McKinsey line as unverified and possibly invented by the blog). Source: [betonai.net](https://betonai.net/ai-tools-that-were-hyped-in-2025-but-dead-by-2026-the-saas-casualties/), [alexcloudstar.com](https://www.alexcloudstar.com/blog/ai-wrappers-dead-what-to-build-instead-2026/).
- **Specific risk:** the model provider ships your feature for free. Model prices also fall fast, which kills a "we resell AI" margin story (CLAIMED, same blogs).

### 3. Newsletters, media, creators
- **Substack:** nearly 100,000 publications earn money out of over 2 million active publications as of April 2026, so roughly 5% earn anything. Other aggregator figures say only about 10% have any paid subscribers. More than 50 creators earn over $1m a year (platform figures repeated by aggregators, so CLAIMED; the "50+ at $1m" line has been stated by Substack itself in the past, from memory, unverified). Sources: [Backlinko](https://backlinko.com/substack-users), [Search Engine Land](https://searchengineland.com/guide/substack-users), [bestwriting.com](https://bestwriting.com/substack-statistics).
- **beehiiv / Gumroad:** not searched (budget). Not found.
- **Platform risk for ad-funded media:** see Google failures below. Stack Overflow, a big Q&A site rather than a solo creator, saw questions plus answers in April 2025 down more than 64% year on year as people moved to AI assistants (VERIFIED via public data reported by DevClass). Source: [DevClass, 2025-05-13](https://devclass.com/2025/05/13/stack-overflow-seeks-rebrand-as-traffic-continues-to-plummet-which-is-bad-news-for-developers/).

### 4. Online shops and physical brands (Etsy, Shopify, DTC)
DTC = direct to consumer, a brand that sells straight to buyers online.
- **Etsy:** median annual revenue per seller quoted at $291; up to 65% of sellers earn under $100 a year; about half of shops have 10 or fewer total sales (CLAIMED, aggregator blogs; figures conflict with each other, one says median £100 to £250/month). Etsy's own older survey (2013, older) is the only first-party source found. Sources: [webtribunal](https://webtribunal.net/blog/etsy-stats/), [listifyai, 2026-01-22](https://www.listifyai.net/blog/how-much-do-etsy-sellers-make-2026), [Etsy 2013 report](https://extfiles.etsy.com/Press/reports/Etsy_RedefiningEntrepreneurshipReport_2013.pdf).
- **Shopify:** Shopify publishes no failure rate. The widely repeated "80 to 90% fail in year one or two" and "5 to 10% become sustainable" are industry estimates by app vendors who sell to struggling stores (CLAIMED). One newsletter reported Shopify store closures outpacing new installs, 1.5 closures per install in Q2 2025, and small DTC brand revenue down 25% year on year in June 2025 (CLAIMED). Sources: [gropulse](https://gropulse.com/shopify-success-rate/), [Ecommerce Coffee Break issue 150](https://ecommerce-coffee-break.beehiiv.com/p/ecb-news-150).
- **Customer acquisition cost:** a March 2025 DTC Index report said average Meta CAC (what it costs in ads to win one buyer) up 16.58% year on year, Facebook return on ad spend down 13.78% (CLAIMED, industry report). Source: [Modern Retail, 2025-06-02](https://www.modernretail.co/marketing/why-candle-brand-siblings-dropped-its-meta-spend-by-56/).
- **Relevance to the user's clothing label:** a small apparel brand sits in the worst-measured, most crowded category here. Treat £1m as a top-1% outcome.

### 5. Done-for-you services and agencies
- **Typical earnings / survival:** no platform-wide data found. The best available proxy is ONS overall: 38.4% five-year survival (VERIFIED). Not found: any dataset on productised agencies specifically.
- **Pattern in failures found:** agencies get commoditised; a common "lesson" from post-mortems is to move to a product within a few years (CLAIMED).

### 6. Real-world businesses run remotely with subcontractors
- **Typical earnings / survival:** no specific data found. ONS overall survival 38.4% at five years applies (VERIFIED). Not found: data on remotely run cleaning, trades or similar firms.

### 7. Courses, communities, paid information
- **Platform change (VERIFIED as a platform policy change, figure CLAIMED via secondary source):** Udemy cut instructor share of subscription revenue from 25% to 20% in January 2024. Source: [EzyCourse blog](https://www.ezycourse.com/blog/why-udemy-creators-are-frustrated).
- **Market claims:** "course revenue down 40% since 2023, completion under 5%" and "coaches selling like 2021 losing 30 to 60%" come from a vendor selling an alternative model (CLAIMED, and the source has a commercial reason to say it). Source: [communipass](https://communipass.com/blog/creator-monetization-trends-2026/).
- **Course platform health:** Thinkific laid off 100 staff in March 2022 and 75 more later (CLAIMED via Class Central report). Source: [Class Central](https://classcentral.com/report/?p=91262).
- **Base rate for the typical course creator:** not found.

### 8. Marketplaces and directories
- **Typical earnings:** marketplaces have the highest category median on TrustMRR at **$1,170/month**; e-commerce $599 (VERIFIED within sample, small sub-samples, not stated). Source: [Indie Hackers TrustMRR analysis](https://www.indiehackers.com/post/i-analyzed-5-079-stripe-verified-startups-f0f6bd053f).
- **Failure mode:** directories and content sites that live on Google traffic were hit hard by the September 2023 helpful content update, the March 2024 core update and AI Overviews (see failures 6 to 9).

## Documented failures that followed the winners' playbooks

**1. "$837 MRR to $0 in 3 months" (unnamed founder, Indie Hackers)**
- Playbook: solo build-in-public SaaS, project management tool.
- What happened: celebrated $837 MRR, then fell to $0 within three months.
- Numbers: $837 MRR peak (CLAIMED).
- Link: [Indie Hackers](https://www.indiehackers.com/post/837-mrr-0-in-3-months-why-my-successful-saas-died-and-the-4-brutal-lessons-thats-save-your-startup-99ec07e2b9). Date: not found.

**2. RecoverFlow (Indie Hackers)**
- Playbook: launch fast publicly, validate before building.
- What happened: 5 days after public launch, 0 signups; shut down before writing backend code.
- Link: [Indie Hackers](https://www.indiehackers.com/post/5-days-0-signups-im-shutting-down-my-saas-before-writing-a-single-line-of-backend-code-8dca5b1e12). Date: not found.

**3. Voiczy.com (Indie Hackers founder)**
- Playbook: solo SaaS.
- What happened: shut down after €118.67 lifetime revenue (CLAIMED, seen in search summary; exact post URL not confirmed).
- Link: summary via [collab365 synthesis](https://spaces.collab365.com/posts/indie-saas-post-mortems-point-to-no-buyers-not-bad-code-utt3f3m2). Date: not found.

**4. PDF chat wrappers (several, unnamed)**
- Playbook: thin AI wrapper charging monthly for "chat with your PDF".
- What happened: OpenAI added PDF upload to ChatGPT in late 2023, removing the main reason to pay.
- Numbers: not found.
- Link: [Fanatical Futurist, Nov 2023](https://www.fanaticalfuturist.com/2023/11/openais-updates-show-big-tech-can-destroy-your-statrtup-at-any-time/); [Yahoo Tech](https://tech.yahoo.com/science/articles/minor-chatgpt-warning-founders-big-123540379.html).

**5. Unnamed AI writing assistant**
- Playbook: AI tool launched to early buzz.
- What happened: 2,000 users in month one; lost 1,300 by month three when ChatGPT shipped the same feature natively (CLAIMED, anonymous anecdote on a blog).
- Link: [alexcloudstar.com](https://www.alexcloudstar.com/blog/ai-wrappers-dead-what-to-build-instead-2026/). Date: 2026 (exact not found).

**6. HouseFresh (Gisele Navarro and husband, small team)**
- Playbook: independent niche review site earning Amazon affiliate commissions, no ads.
- What happened: Google traffic fell from about 4,000 visitors a day (Sept 2023) to about 200 by early 2024, which they pin on Google's updates. They were advised to shut the site and start on a new domain.
- Numbers: about 95% traffic loss (CLAIMED, reported by AFP).
- Link: [Malay Mail / AFP, 2024-07-02](https://www.malaymail.com/news/tech-gadgets/2024/07/02/google-is-broken-how-an-algorithm-tweak-cost-livelihoods/142493).

**7. Retro Dodo**
- Playbook: enthusiast content site living on organic search.
- What happened: lost roughly 85% of organic traffic and revenue after Google updates (CLAIMED).
- Link: [TechWyse](https://www.techwyse.com/blog/general-category/googles-helpful-content-system-didnt-punish-bad-content-it-punished-honest-niches). Date: not found.

**8. All About Berlin (Nicolas Bouliane, solo)**
- Playbook: solo guide/directory-style site on a narrow topic (moving to Berlin), built since 2017.
- What happened: lost about 70% of traffic, which he attributes to Google AI Overviews; says he will need another way to pay rent.
- Link: [nicolasbouliane.com, "Death by AI"](https://nicolasbouliane.com/blog/death-by-ai). Date: not found (2025 per context).

**9. Charleston Crafted (Morgan McBride)**
- Playbook: ad-funded DIY content site.
- What happened: about 70% traffic loss in one month; 65% of ad revenue gone in a year, "tens of thousands of dollars" (CLAIMED, reported in press).
- Link: [eWeek](https://www.eweek.com/news/google-ai-overviews-smb-impact/). Date: not found.

**10. Siblings (candle brand, Brooklyn)**
- Playbook: DTC brand grown on Facebook and Instagram ads.
- What happened: not dead, but squeezed; cost to win a customer rose from $25 (2022) to $60 (2025), so they cut Meta spend 56% and are moving off paid ads.
- Link: [Modern Retail, 2025-06-02](https://www.modernretail.co/marketing/why-candle-brand-siblings-dropped-its-meta-spend-by-56/).

**11. In The Style (UK online fashion, larger than 5 people)**
- Playbook: influencer-led online fashion brand.
- What happened: entered administration and was sold to Alps Sourcing in March 2025, saving 87 UK jobs.
- Link: [Retail Gazette / startups.co.uk](https://startups.co.uk/news/uk-brands-administration/). Note: not a small team, included because it is the influencer DTC playbook at scale.

**12. Ankur Warikoo's edtech business (India, creator-led)**
- Playbook: creator with large audience sells courses. SELLS A COURSE.
- What happened: shut down the edtech business after Rs 100 crore in sales (about £9m at rough rates, conversion mine).
- Link: [Trak.in](https://trak.in/stories/after-generating-rs-100-crore-sales-ankur-warikoo-shuts-down-edtech-business/). Date: not found.

**13. Unnamed info-product creator**
- Playbook: online courses/books.
- What happened: 87% drop in net income in 2022 versus 2021 (post-pandemic slump) (CLAIMED, own blog).
- Link: [Goodreads author blog](https://www.goodreads.com/author_blog_posts/24017002-surviving-the-post-pandemic-slump-how-we-recovered-from-an-87-drop-in).

**14. Neon Shake (Polish digital agency)**
- Playbook: done-for-you digital services.
- What happened: collapsed in 2023 after 14 years, put down to commoditisation (CLAIMED, failure database). Founded 2009, older.
- Link: [ideaproof.io](https://ideaproof.io/failure/neon-shake).

**15. Chegg (not small; context only)**
- Playbook: paid answers and study help, the same "paid information" model as many course and Q&A businesses.
- What happened: subscribers down 31% to 3.2 million in a quarter, revenue down 30% to $121m; cut 22% of staff as students moved to ChatGPT (VERIFIED, company filings and press).
- Link: [TechRadar](https://www.techradar.com/pro/chegg-announces-move-to-reduce-workforce-by-22-percent-as-students-turn-to-ai); [Chegg 10-K FY2025](https://www.sec.gov/Archives/edgar/data/1364954/000136495426000021/chgg-20251231.htm).

Note on balance: a fair test needs failures that are named, small, and with numbers. Only cases 1, 2, 6, 8 and 9 meet most of that. Most failures are never written up, which is itself the point of the next section.

## Survivorship bias and the "income report" industry

- **Survivorship bias** means you only see the people still standing. Winners post screenshots; losers delete the tweet and get a job. Every "how I hit $1m" story is drawn from a pool where the losers are invisible.
- **The data sources are biased too.** TrustMRR only includes people who choose to list. ChartMogul only sees firms already paying for billing analytics. Etsy and Shopify do not publish failure rates, and the "90% fail" numbers come from app vendors selling fixes. Even the "honest" numbers flatter the field.
- **Income reports as a business model.** A large part of the indie and creator world earns its money by teaching other people to do indie and creator work: courses, cohorts, communities, templates, "build in public" coaching. When someone's main product is a course on how they got rich, their income report is a sales page, not evidence. Treat it as CLAIMED, check whether the revenue comes from the thing they say worked or from teaching it, and ask what share of their students reached even $1k MRR. That number is almost never published.
- **Several sources in this file sell something.** The course-crash statistics come from a vendor of an alternative to courses. The Shopify failure statistics come from Shopify app makers. The AI-wrapper death statistics come from blogs that sell "what to build instead". Read each one as a pitch.
- **What the honest numbers say:** median Stripe-verified indie product makes about $169 a month; about 1 in 20 Substack publications earns anything; around 6 in 10 registered UK businesses are gone in five years. The £1m outcomes in Phase 1 are the top of a very tall pyramid.

## What this means for the user (OPINION)
- Expect the base case of any new product to be zero to a few hundred pounds a month. Plan the day job around that, not around the Phase 1 winners.
- The biggest killers found were not bad products but **one channel owned by someone else**: Google traffic, Meta ads, or an AI model that ships your feature. A plan that depends on one of these is fragile.
- Categories with higher medians in verified data (marketplaces, sales tools) are worth weighting, but the samples are small.
