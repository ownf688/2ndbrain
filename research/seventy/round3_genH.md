# Round 3, Generator H: dated, forced platform migrations (Oct 2026 to Oct 2027)

Written 2026-10-04. Research only, no scores. 12 searches used: **SEARCH LIMIT HIT**. Search-result summaries only; source pages were not opened, so every date below is "as reported in search results" and should be checked on the source page before scoring.

## Headline finding (OPINION)
The biggest HR-stack deadlines of 2026 have **already passed**: Greenhouse Harvest v1/v2 shut off 31 Aug 2026; Shopify Scripts stopped 30 Jun 2026; IRIS Earnie IQ and KashFlow Payroll stopped processing 6 Apr 2026; BrightPay went cloud-only from 2026/27. What remains inside the 12-month window is smaller or softer: Slack classic apps (16 Nov 2026, date conflicting), Microsoft SMTP basic auth off by default (end Dec 2026, admins can switch it back on), UKG Workforce Central on-prem end of life (31 Mar 2027, enterprise), the 6 Apr 2027 payroll year-end switch window, and Xero broad scopes (Sept 2027). **Across all 12 searches I found no priced freelancer listing for any of these migrations.** That is the main gap for "proof people pay".

## Sources used
- Greenhouse: [dev.to FlareCanary](https://dev.to/flarecanary/greenhouse-harvest-v1v2-retires-august-31-three-silent-failure-modes-during-your-v3-cursor-6cl), [Zapier help](https://help.zapier.com/hc/en-us/articles/47585848967437-Action-required-Update-your-Greenhouse-Zaps-before-the-Harvest-API-deprecation), [Workato](https://docs.workato.com/connectors/greenhouse/migration), [Boomi](https://help.boomi.com/docs/Atomsphere/Data_Integration/Sources/Applications/Greenhouse/migration-greenhouse-v3), [Kombo](https://kombo-api.notion.site/Greenhouse-v1-v3-migration-33e6526d848a80de96bdddc8362604fa), [100Hires](https://100hires.com/greenhouse-api.html)
- Shopify: [shopify.dev changelog](https://shopify.dev/changelog/shopify-scripts-will-be-deprecated-on-june-30-2026)
- HMRC: [Freelance Informer](https://www.freelanceinformer.com/news/mtd-contractor-software-devs-must-update-client-tools-before-16-october/), [GOV.UK MTD developer newsletter ed. 6](https://www.gov.uk/government/publications/edition-6-making-tax-digital-for-income-tax-software-developer-newsletter/edition-6-making-tax-digital-for-income-tax-software-developer-newsletter)
- Xero: [Apideck](https://apideck.com/blog/xero-scopes), [Xero FAQ](https://developer.xero.com/faq/granular-scopes), [Xero devblog](https://devblog.xero.com/upcoming-changes-to-xero-accounting-api-scopes-705c5a9621a0)
- Microsoft: [captaindns](https://www.captaindns.com/en/blog/microsoft-exchange-basic-auth-smtp-end), [MC786329 tracker](https://mc.merill.net/message/MC786329/v/2025-06-12T17-33-31-167Z), [Innovia (BC/NAV)](https://www.innovia.com/blog/microsoft-to-retire-basic-auth-smtp-for-exchange-online-what-bc-nav-users-need-to-know)
- Slack: [classic apps deprecation changelog](https://docs.slack.dev/changelog/2024-09-legacy-custom-bots-classic-apps-deprecation/), [Slack retirements](https://slack.com/intl/en-gb/help/articles/4426294050451-Slack-feature-and-subscription-retirements)
- Payroll sunsets: [IRIS Earnie IQ EOL (Staffology)](https://help.staffology.co.uk/payroll/projectfiles/files/eol-and-dataexport/Earnie_IQ_End_of_Life_Doc_-_Sep_2025.pdf), [KashFlow EOL](https://help.staffology.co.uk/payroll/projectfiles/files/eol-and-dataexport/KashFlow_End_of_Life_Doc_-_Jan_2026.pdf), [BrightPay Connect FAQs](https://payrollsupport.uk.brightsg.com/hc/en-gb/articles/36947924801809-FAQs-Moving-from-BrightPay-Connect), [AccountingWEB BrightPay alternatives](https://www.accountingweb.co.uk/any-answers/recommended-brightpay-alternatives), [UKG WFC (RSM)](https://technologyblog.rsmus.com/uncategorized/ukg-workforce-central-support-is-ending-do-you-have-a-plan)
- HiBob: [Make community thread](https://community.make.com/t/hibob-api-deprecation-read-all-company-employees-and-read-company-employee-by-id/57732)

---

## H1. Greenhouse "missed the deadline" rescue: fix internal reports, Sheets, BI pulls and scripts broken by the 31 Aug 2026 Harvest v1/v2 shut-off
- **Who pays:** Talent ops / People analytics leads at Greenhouse customers whose home-built pulls (Sheets, Looker/BI, scripts, Zaps) now return 401.
- **Proof of pay:** Not found (no priced listing). One search summary said "companies are looking for experienced developers to upgrade custom Greenhouse Harvest API integrations from V2 to V3"; source page and budget not identified. Vendors (Workato, Boomi, Zapier, Okta, Kombo) each published self-serve guides, which shows volume of affected integrations, not paid demand.
- **Rivals and gap:** Integration platforms migrated their own connectors (free to their customers). Gap: custom in-house code, which no vendor touches. Unified-API firms (Kombo, Knit, Truto, Apideck) sell to SaaS vendors, not end customers.
- **Dated trigger:** 31 Aug 2026, no dual-stack period; v1 calls return 401 (dev.to, Boomi). **Already passed**: demand now is laggards only, and it shrinks each week. Free vendor fix: yes for connectors, no for custom code.
- **Comparable revenue:** Not found.
- **First sale in 2 weeks/£500:** Plausible as a fixed-price service if a buyer is found; reaching Greenhouse customers' ops people in 2 weeks is the hard part (UK Greenhouse customer count not found).
- **User assets:** build skill (OAuth, APIs, Supabase), ATS domain knowledge, HR-leaders newsletter for reach. 3 assets.
- **Conflicts:** NALA runs Workable, not Greenhouse, so no direct competition with the employer; outside-work clause unchecked. Nudge: if Nudge integrates with ATSs, this is adjacent and could be a lead source rather than a conflict (UNCLEAR).
- **Against:** trigger is behind us; a broken pipeline is usually fixed by the company's own engineer in a day; no prices anywhere.

## H2. Slack classic-app and legacy-bot rebuilds for People teams (onboarding bots, birthday/anniversary bots, pulse bots)
- **Who pays:** People/ops leads at firms whose home-grown HR Slack bots were built as classic apps.
- **Proof of pay:** Not found.
- **Rivals and gap:** Off-the-shelf HR Slack apps (Donut, Birthday Bot, etc.; prices not checked this round) replace most simple bots, often with free tiers. Gap: bespoke bots wired to the firm's HRIS.
- **Dated trigger:** Slack changelog result says "Classic apps will no longer function beginning November 16, 2026"; another snippet says the date moved to 25 May 2026. **Conflicting; must be checked on the source page.** Legacy custom bots ended 31 Mar 2025; legacy Workflow Builder steps from apps ended 26 Sep 2024. No automated migration for classic apps found.
- **Comparable revenue:** Not found.
- **First sale:** Service-speed if a buyer exists; unknown how many People teams still run classic apps.
- **User assets:** Slack + HR + build skill + newsletter. Strong fit, evenings.
- **Conflicts:** Nudge is a Slack-based hiring product (per B24); a Slack-bot service for People teams overlaps its buyers (NUDGE flag, could also be a channel). Day job: low.
- **Against:** most such bots were cheap toys; buyers will switch to a £0-5/user app rather than pay for a rebuild. If the date was May 2026, this is already passed too.

## H3. Microsoft 365 SMTP basic-auth fix for HR and payroll systems that email payslips, offer letters and alerts (end Dec 2026)
- **Who pays:** Small firms (and their HR/payroll admins) whose desktop payroll, scanners, ATS notifications, website forms or line-of-business apps send via Exchange Online with a username and password.
- **Proof of pay:** Not found for this offer. Innovia's post targets Business Central/NAV users, showing partners use it as a lead topic; no price seen.
- **Rivals and gap:** Every MSP and IT support firm; SMTP relay services (SendGrid, Mailgun, SMTP2GO) offer the self-serve fix. Gap: none obvious.
- **Dated trigger:** End of December 2026: SMTP AUTH basic auth disabled by default for existing tenants, **but admins can re-enable it**; final removal date to be announced in H2 2027 (captaindns, MC786329). The date has slipped at least twice (Sept 2025, then March-April 2026). Soft trigger.
- **Comparable revenue:** Not found.
- **First sale:** Possible via local Belfast SMEs, but it is IT support, not People work.
- **User assets:** build skill only. 1 asset.
- **Conflicts:** none with NALA or Nudge.
- **Against:** a toggle buys another year; MSPs already own the relationship; crowded. Likely fails checks 3 and 4.

## H4. Xero granular-scopes re-authorisation for small firms with custom Xero integrations (Sept 2027)
- **Who pays:** SMEs and accountants who paid a freelancer for a one-off Xero integration (custom dashboards, invoice syncs, payroll journal pushes) built before 2 Mar 2026.
- **Proof of pay:** Not found.
- **Rivals and gap:** Xero app-store partners migrate their own apps (no customer cost). Integration platforms (Zapier, Make, Apideck) handle theirs. Gap: orphaned custom code whose original developer has gone. Size of that gap: not found.
- **Dated trigger:** Existing apps can use the broad `accounting.transactions` and `accounting.reports.read` scopes until **September 2027** (exact day not found); every connected user must re-authorise; "no silent migration path" (Apideck, Xero FAQ). Inside the window, and no free fix for custom code.
- **Comparable revenue:** Not found.
- **First sale in 2 weeks:** Unlikely; the deadline is 11 months out, and urgency usually starts in the last 2-3 months.
- **User assets:** build skill; payroll knowledge for payroll-journal integrations. 1-2 assets.
- **Conflicts:** NALA is a payments firm; accounting integrations for SMEs are not its market, but check the outside-work clause. Nudge: none.
- **Against:** the actual change is small (swap scope strings, prompt re-consent); accountants' in-house tech teams or Fiverr developers will do it cheaply. Buyers are hard to find because the code is orphaned.

## H5. "Payroll switch at year end": move micro-employers off sunset payroll products before 6 April 2027
- **Who pays:** Micro-employers and small bureaux still on, or hastily patched off, IRIS Earnie IQ, IRIS KashFlow Payroll, IRIS Payroll Basics, or BrightPay desktop.
- **Proof of pay:** Not found for migration as a standalone fee. Payroll bureaux charge per payslip (prices not found this round).
- **Rivals and gap:** IRIS provides end-of-life documents and data export to its own Staffology product (free, vendor-led). BrightPay moves customers to BrightPay Cloud. AccountingWEB thread shows bureaux shopping for alternatives (Moneysoft, Superpay mentioned). Gap: unclear; vendors do the migration.
- **Dated trigger:** The sunsets already took effect at 6 April 2026 (Earnie IQ, KashFlow Payroll; BrightPay Connect for bureau desktop licences ended for employees after 5 April 2026). **Next forced point is the 2027/28 tax year start, 6 April 2027**, only for those running on unsupported software (not verified that any are). BrightPay desktop gets "no updates, support or legislative compliance" from 2026/27.
- **Comparable revenue:** Not found.
- **First sale:** Weak; employers who missed April 2026 have likely moved already or will do it at year end.
- **User assets:** UK payroll/HR knowledge, build skill (data mapping). 2 assets.
- **Conflicts:** low with NALA; none with Nudge.
- **Against:** vendors give free import paths; bureaux and accountants already hold these clients; payroll errors carry real liability for an evenings-only operator.

## H6. UKG Workforce Central on-prem end of life (31 Mar 2027): data extract and archive for UK/IE mid-size employers
- **Who pays:** Retail, hospitality and healthcare employers still on WFC on-premise.
- **Proof of pay:** Enterprise migration projects exist (RSM's post is a partner lead piece); price not found.
- **Rivals and gap:** UKG partners and large SIs (RSM and others). No gap for a solo operator.
- **Dated trigger:** "Workforce Central On-Premise End of Life: 3/31/27" (RSM). Inside window. UKG drives customers to Pro, not a free migration for custom work (not confirmed).
- **Comparable revenue:** Not found.
- **First sale:** Not in 2 weeks; enterprise procurement.
- **User assets:** HR systems knowledge, build skill.
- **Conflicts:** weekday presence and vendor access likely needed; fails fit.
- **Against:** enterprise, slow, partner-gated. Listed for completeness; expect kill.

## H7. HMRC MTD Income Tax legacy-endpoint retirement (16 Oct 2026): patch custom bridging tools for contractors and small software makers
- **Who pays:** Small software vendors and contractors running home-made MTD bridging tools.
- **Proof of pay:** Not found.
- **Rivals and gap:** Commercial MTD software updates itself. HMRC's standard 6-month deprecation notice means most vendors are done.
- **Dated trigger:** Older Self Assessment API endpoints, including Individuals Capital Gains Income API v2 and Individuals Reliefs API v2, retired 16 Oct 2026 (Freelance Informer, GOV.UK newsletter). 12 days away.
- **Comparable revenue:** Not found.
- **First sale:** Too little time to find buyers.
- **User assets:** build skill only; tax is outside the user's expertise.
- **Conflicts:** low.
- **Against:** tiny, tax-domain, deadline nearly here. Expect kill.

## H8. HiBob API deprecation fixes for Make/Zapier scenarios (date not found)
- **Who pays:** HiBob customers' People ops teams whose Make or Zapier automations use deprecated "read all company employees" modules.
- **Proof of pay:** Not found.
- **Rivals and gap:** 8+ HiBob partners already sell services (from R6 kill). Make is expected to update its own modules.
- **Dated trigger:** Deprecation of those endpoints reported in a Make community thread; **date not found**.
- **User assets:** HiBob knowledge, build skill, newsletter.
- **Conflicts:** R6 was killed for crowding, weekday access and conflict; this repeats R6 unless a hard date and an unserved segment are found.
- **Against:** repeats R6 kill reason; no date.

## H9. "Deprecation radar" for People-tech stacks: a monthly paid alert plus fixed-price fixes when an HR/recruiting/payroll API or feature hits a sunset date
- **One line:** A subscription that watches a firm's named People stack (Greenhouse, Workable, HiBob, BambooHR, Slack, M365, Xero, payroll) for dated breaking changes and quotes a fix before the date.
- **Who pays:** People/talent ops leads at 50-500-person firms with home-built integrations.
- **Proof of pay:** Not found for HR-specific. FlareCanary (author of the Greenhouse dev.to post) appears to sell API-change monitoring; price and revenue not found.
- **Rivals and gap:** Generic API-change monitors (FlareCanary; others not checked); vendor changelogs and emails are free. Gap: HR-specific, plain-English, with a fix attached. Evidence of buyers in the gap: not found.
- **Dated trigger:** None of its own; it rides the dates above, the strongest of which have passed.
- **Comparable revenue:** Not found.
- **First sale in 2 weeks:** Possible as a pre-sale to newsletter readers, unproven.
- **User assets:** newsletter, HR-systems knowledge, build skill. 3 assets.
- **Conflicts:** NUDGE light (if Nudge integrates with ATSs/Slack, overlap of buyers); day job low.
- **Against:** vendors email customers about deprecations for free; a radar without a forced date is "steady demand" at best; the free-version problem (check 4) is likely.

---

## Summary table (dates and status)
| ID | Trigger | Date | In window? | Free vendor fix? | Priced sellers found |
|---|---|---|---|---|---|
| H1 | Greenhouse Harvest v1/v2 off | 31 Aug 2026 | No, passed | Connectors yes; custom code no | 0 |
| H2 | Slack classic apps stop | 16 Nov 2026 (conflicting: 25 May 2026) | Maybe | No | 0 |
| H3 | M365 SMTP basic auth off by default | End Dec 2026 (re-enable allowed) | Yes, soft | Self-serve relays | 0 |
| H4 | Xero broad scopes end | Sept 2027 | Yes | For partner apps, not custom | 0 |
| H5 | Payroll sunsets, next year-end | 6 Apr 2027 (sunsets were 6 Apr 2026) | Yes, weak | Yes (vendor import) | 0 |
| H6 | UKG WFC on-prem EOL | 31 Mar 2027 | Yes | Partner-led | 0 |
| H7 | HMRC MTD legacy endpoints | 16 Oct 2026 | Yes, 12 days | Commercial software self-updates | 0 |
| H8 | HiBob endpoint deprecation | Not found | Unknown | Make likely | 0 |
| H9 | Radar subscription | Rides the above | n/a | Vendor emails free | 0 |

## Generator's view of the gaps (OPINION, not a score)
- This angle delivers dated triggers but **not** priced proof of pay, which the R8 lesson says is needed at the same time. In 12 searches no Upwork/Contra/agency price for any of these migrations surfaced.
- The HR-specific deadlines with the best fit (Greenhouse, Shopify-style hard shut-offs) are behind us. The best remaining fit is H2 (Slack classic apps), but its date conflicts and the buyer's alternative is a cheap off-the-shelf bot. H4 (Xero, Sept 2027) is the cleanest hard date still ahead, but it uses only the build skill and its buyers (orphaned custom code) are hard to find.
- Next searches if a later round pursues this: Upwork "Harvest v3" and "Slack classic app migration" job posts with budgets; Slack changelog to settle the classic-app date; Xero exact September 2027 day; count of UK Greenhouse customers.
