---
date: 2026-07-09
time: "10:45"
timezone: UTC
type: interview
interview_type: problem-solving
attendees:
  - "[[Ryan Bolton-Smith]]"
  - "Kasper Bentsen"
candidate: Kasper Bentsen
role: "Senior Backend Engineer"
duration: ~48 min
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/463030380"
tags: [meeting, interview]
---

# 2026-07-09 - Kasper Bentsen - Senior Backend Engineer Problem-Solving

> [!summary] TL;DR
> Danish senior backend engineer, currently at 90POE (procurement domain), leaving due to post-acquisition culture shift toward KPI-driven waterfall. Strong systems-thinking, good idempotency and event-architecture answers, healthy AI skepticism with clear ownership principles. Salary ask is 138K EUR/year on B2B. Progressed to pair programming exercise on customer limits.

## Decisions

Hire signal: **lean yes**

Ryan progressed Kasper to the next stage (pair programming). Kasper answered all three technical scenarios well and unprompted, demonstrated good architectural instincts. The idempotency answer needed a nudge to the right term but the concept was correct. The event-sourcing / Kafka answer for the unique-users reporting problem was clean and independent. AI answer showed genuine maturity - not anti-AI, but disciplined about ownership. Main uncertainty: salary (138K EUR) is at the upper end; some flexibility confirmed but contingent on how much he likes the role. Notice period is 1 or 3 months - needs confirmation.

## Key Discussion Points

### Background & Experience

- Currently at 90POE (maritime procurement), cross-functional backend team of ~8. Prior role at Beat (ridesharing), which fed into 90POE when Beat shut its engineering division.
- Leaving because 90POE was acquired ~1 year ago. New leadership introduced KPI-driven 3-month roadmaps with customer-facing hard deadlines layered on top of Scrum, creating a waterfall-Scrum hybrid. Kasper described it as entering a "Ballmer era" - execution over innovation.
- Wants: interesting problems, technical challenge, big impact, clean systems. Fintech has always appealed. Previous manager started Lunar (couldn't join due to contract clause).
- Tech stack at 90POE: Go, Postgres, SQLite, Kafka.
- Danish national, based in Denmark, B2B contract arrangement (same as current role).

### Technical Scenarios

**Scenario 1 - Duplicate send prevention (slow connection, user clicks 3x):**
Kasper immediately raised optimistic locking and nonces, worked through the tradeoffs based on transaction weight and rollback cost. Did not land on "idempotency" by name unprompted but confirmed it immediately when Ryan named it. Also mentioned frontend prevention and distributed locking. Clean answer.

**Scenario 2 - Unique users transacted in last 7 days:**
Strongest answer of the three. Immediately flagged: never put reporting load on the production database. Proposed Kafka event stream, multiple consumers per event type, separate reporting system per domain. Correctly identified the key engineering principle: decouple product engineering from data platform via shared event contracts. No cross-team interference.

**Scenario 3 - AI usage in engineering workflow:**
Deliberately distrustful of AI - knows how it works architecturally. Joins new codebases without AI to build understanding first, then offloads boring/well-understood tasks. Core principle: "If you're digging a hole, AI makes you dig faster" - AI does not fix wrong direction. Writes core logic himself, uses AI to fill gaps. Hard line: never submit AI code you haven't reviewed - it's your code regardless of who wrote it.

### Motivation & Fit

- Cares about product mission. Described NALA initially looking like a "scam site" but verified via Trustpilot before taking the call - useful candid feedback passed to Ryan for the brand team.
- Excited by bilateral flows and stablecoin as real engineering problems.
- Asked sharp questions: burn rate and funding runway (Ryan disclosed Series B in late stages, best quarter/most profitable month ever, LATAM and global accounts as next expansion). Also asked about headcount (149) and whether engineering is fully remote (yes, but all Europe-based).
- Minimal meeting culture (3h/week for engineers) noted as a positive.

### Logistics

- Notice period: 1 or 3 months - needs confirmation before offer.
- Salary ask: 138K EUR/year (11,500 EUR/month). Some flexibility, contingent on role appeal.
- B2B contract confirmed as appropriate (same as current arrangement).
- Next step: pair programming exercise on customer limits problem, 1 hour, zip file sent 30 min before call.

## Values Alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Moderate | Mentioned product mission mattering ("if I don't care about the product, I don't really want to be there") but discussion was mostly technical |
| Play to Win | Strong | Proactive due diligence before the call (Trustpilot check), sharp questions on funding and runway, clear view on what good engineering looks like |
| Speed Wins | Strong | "Nothing is as permanent in tech as a temporary solution" - pragmatic but principled; used AI on heavy deadlines when needed but sets clear conditions |
| Understand Why | Strong | "I will not be using AI at all for a period just so that I get a feel for the system" - root-cause before shortcuts; event decoupling answer shows deep systems understanding |

## Problem Solving Scorecard

| Dimension | Rating (1-5) | Evidence |
|-----------|-------------|----------|
| Problem Breakdown | 4 | Consistently identified the core constraint before proposing a solution (e.g. "it depends on whether your transactions are heavy and hard to roll back"); asked clarifying questions on tech stack |
| Independence | 4 | Reached correct solutions on scenarios 1 and 2 without leading; scenario 1 needed the idempotency term surfaced but the concept was correct |
| Solution Quality | 4 | Kafka + decoupled consumers answer was textbook and clean; AI answer showed judgment over enthusiasm; no overengineering |

## Propagation

### [[Ryan Bolton-Smith]]
- [2026-07-09, [[2026-07-09 - Kasper Bentsen - Senior Backend Engineer Problem-Solving]]] Progressed to pair programming - sent workable link and self-schedule link for engineer session - "It's been great, I'll see you in a while"

### [[Hiring]]
- [2026-07-09, [[2026-07-09 - Kasper Bentsen - Senior Backend Engineer Problem-Solving]]] Salary at 138K EUR/year B2B, flexibility confirmed. Notice period unconfirmed (1 or 3 months - Ryan to verify). Series B announcement expected in next few weeks - don't delay process.

## Raw transcript

> [!note]- Expand transcript
> ## Interview with Kasper Bentsen - Senior Backend Engineer - Transcript
> 
> ### 00:00:01
> 
> **Ryan Bolton-Smith:** Hey, Kasper.
> 
> 
> ### 00:00:03
> 
> **Kasper Bentsen:** Hello.
> 
> 
> ### 00:00:04
> 
> **Ryan Bolton-Smith:** Hey, sorry for keeping you waiting. My laptop's being extremely slow even though I'm not overheating. Give me a second, please.
> 
> 
> ### 00:00:13
> 
> **Kasper Bentsen:** Yeah, no worries.
> 
> 
> ### 00:01:07
> 
> **Ryan Bolton-Smith:** Sorry about this, Kasper. It appears that my laptop has overheated.
> 
> 
> ### 00:01:12
> 
> **Kasper Bentsen:** No worries. The heat is not just bad for, for humans.
> 
> 
> ### 00:01:16
> 
> **Ryan Bolton-Smith:** Certainly not.
> 
> 
> ### 00:01:17
> 
> **Kasper Bentsen:** My—
> 
> 
> ### 00:01:19
> 
> **Ryan Bolton-Smith:** I've got 2 PC cases that I kind of halved. Well, I won't show my room, maybe a bit improper as an interviewer, but I've got 3 or 4 PC cases all opened up where I'm reconfiguring. I'm changing the blades on some of my CPU fans to help increase velocity. And Yeah, I need to be able to keep my, all my stuff pretty cool because I run a lot of, uh, yeah, uh, pretty GPU-intensive games, I would say, like Satisfactory, um, and, uh, yeah, almost impossible to keep those cool in the heat.
> 
> 
> ### 00:01:58
> 
> **Kasper Bentsen:** Um, it really is.
> 
> 
> ### 00:02:00
> 
> **Ryan Bolton-Smith:** Well, um, well, I really appreciate you kind of taking the time. And look, the aim of the very first call from my perspective here is to ultimately get an understanding of your skills and your experience, see how it aligns to the role, you know, here at NALA. And ultimately, if we're both happy with what one another say, we can then go on to the next stages. Seem like a plan?
> 
> 
> ### 00:02:21
> 
> **Kasper Bentsen:** Yep, sounds good.
> 
> 
> ### 00:02:22
> 
> **Ryan Bolton-Smith:** Cool, awesome. Why do you know what I was just thinking? I see so many beat engineers that go from beat over to 90POE. Why is that? Uh, you're George Giorgio, right? At 90POE, you've had George Giorgio, George Christo, Uh, I can't remember who else, but yeah, Nikos Raptis, like we have a lot.
> 
> 
> ### 00:02:44
> 
> **Kasper Bentsen:** Um, I, I think it was just coincidence of when Beat kind of shut down their engineering division and it all went over to Freenow, and 90POE was aggressively hiring at the time.
> 
> 
> ### 00:02:56
> 
> **Ryan Bolton-Smith:** Fair, fair.
> 
> 
> ### 00:02:58
> 
> **Kasper Bentsen:** And it's a lot of Greek, like 90POE was Greek and the shipping market is very Greek as well, so I think it's just a good fit.
> 
> 
> ### 00:03:06
> 
> **Ryan Bolton-Smith:** Yeah, my brother works as a shipbroker and, uh, he always brings me back some oil back home from Greece, which is always nice. Sorry if you can hear a baby screaming in the background. I've got a newborn in the house.
> 
> 
> ### 00:03:21
> 
> **Kasper Bentsen:** No worries. Congratulations.
> 
> 
> ### 00:03:23
> 
> **Ryan Bolton-Smith:** Yeah, thank you, thank you. Um, so I suppose, Kasper, like, based on the message that I sent you, um, obviously Must have been positive, hence why we're speaking today. But was there any like immediate queries that you had of either, whether it be about the role or the company? Because I like to try and address these things upfront because if I say something that you don't like, then, you know, we can call it a day.
> 
> 
> ### 00:03:45
> 
> **Kasper Bentsen:** Yeah, yeah, of course. No, like my immediate reaction was like, is this a scam? Like NALA looks very like a scam site to me. So I had to do a little bit of digging.
> 
> 
> ### 00:03:56
> 
> **Ryan Bolton-Smith:** Oh, okay. Yeah. What? Why do you think that? Sorry, I'm really. I'll pass on the feedback to the team.
> 
> 
> ### 00:04:02
> 
> **Kasper Bentsen:** No, just very like African money, very generic fintech page looks very you know very scammy.
> 
> 
> ### 00:04:13
> 
> **Ryan Bolton-Smith:** Yeah.
> 
> 
> ### 00:04:14
> 
> **Kasper Bentsen:** I don't think it is.
> 
> 
> ### 00:04:15
> 
> **Ryan Bolton-Smith:** Isn't it? Yeah.
> 
> 
> ### 00:04:17
> 
> **Kasper Bentsen:** Yeah. Yeah. I'm very used to checking Trustpilot, and the first thing I see is good reviews there with a lot of reviews. So. That's the first bit of evidence that obviously this is not, not a fake or a scam. So that's why I agreed on the meeting at all.
> 
> 
> ### 00:04:31
> 
> **Ryan Bolton-Smith:** Good. Yeah, look, yeah, we are. So we've got many, many licenses. Like I said, there's many news articles about us as well, and loads of Forbes ones as well. I mean, to be fair, actually Forbes doesn't actually help, I think, with scam companies just because of their recent 30 Under 30s that they've done over the last few years. But Benji's not in that crop. But yeah, like I say, we're VC backed by Accel and NYC, just so you've got the numbers up front. So they did a Series A raise back in June, July 2024. I joined September 2024. So of that $40 million Series A, a lot of it just kind of gets locked up in float, to be quite honest with you. Like, obviously, you know how it works. It's, you know, hey, You want a rate of X, you give us 20 mil, we'll give you this. You give us 25 mil, we'll give you this. Right, okay, well, you know, we'll give you more. And, you know, we don't really spend that much on expanding really. Um, and then they did the debt raise just, uh, December just gone, like 2025. Um, and they did that as 50 million. Um, and they did that as like a debt raise. So obviously, A, not giving up liquidity, uh, and B, it also— like, anyone that does a debt raise is normally quite It might sound like a bad thing, but it's normally quite a positive indicator because it means that, A, they're definitely generating enough revenue that this company is willing to lend them such an exorbitant amount of money and that we can afford the premiums, which is kind of what we do. It's very normal for cross-border payment companies to do that. Look at TapTap, Remitly, Wise, et cetera. Like they've all done at least 6 or 7 debt raises. This is our first one ever. And this means that we can actually spend some money on expanding. Because if you look at Nala and Rafiki, was it clear that how Nala makes money and how Rafiki makes money? Like, I know for some it's obvious, some it isn't. So I thought I'd just double-check.
> 
> 
> ### 00:06:15
> 
> **Kasper Bentsen:** I didn't look that much into the business models. I'm guessing that it's a percentage of whatever transaction for Nala, and Rafiki is B2B, so it's contract-based, I would assume.
> 
> 
> ### 00:06:27
> 
> **Ryan Bolton-Smith:** Yeah, I mean, it's very straightforward. Instead, so we charge a small fee. So if you send a very small amount of money, we'll charge you a fee because it literally costs us money to send it over. You know, we're not a charity.
> 
> 
> ### 00:06:37
> 
> **Kasper Bentsen:** Yeah.
> 
> 
> ### 00:06:38
> 
> **Ryan Bolton-Smith:** But then those, if you're sending like, you know, $100 or something as an example, like $100 USD, then, you know, you're not gonna get charged for that. We'll make our money in the FX margin itself. The FX margin, although for those in euro and pound might not seem like a lot, but with some of the African currencies and Asian currencies, they're very, very volatile. Like I've seen currencies move 10% in a day. If that happened to the euro or the pound, there would be a catastrophe of sorts, right?
> 
> 
> ### 00:07:04
> 
> **Kasper Bentsen:** Yeah.
> 
> 
> ### 00:07:06
> 
> **Ryan Bolton-Smith:** So yeah, that's kind of how we make it. And basically Rafiki is quite interesting how that came about really. So the way that you think of our company structure is like we've got NALA Group up here and then we've got NALA, which is product A, and then we've got Rafiki, product B. We had to call it a different name because ultimately our competitors use it. So the competitors of NALA use Rafiki's B2B pipelines.
> 
> 
> ### 00:07:29
> 
> **Kasper Bentsen:** Interesting.
> 
> 
> ### 00:07:29
> 
> **Ryan Bolton-Smith:** So like MoneyGram, uh, Cardano Money, DLocal, TransferGo, these gigantic remittance companies use our services. And this all come about in a really hilarious way, in my opinion at least, was basically about 3 years ago the team was sitting there and they were getting really annoyed with these middlemen in both Africa and Asia of how we want to move money. So normally it's about a 5-step process, and that's a very simplified version. It's like, hey, I want to send money, cool. go to NALA, go to Wise or whoever. We then go to a broker, then go to a local payout company, and then hey presto, you get your money. All the problems are here and here, right? You know, payout brokers, middlemen doing the integrations. And as an engineer, I'm sure you can appreciate it more than most. We're dealing with people whose APIs are absolutely crap and not well documented. We're trying to do this, but actually it's doing this instead. Like, okay, why? And they're putting themselves in maintenance mode for 6 hours, that turns into 20 hours. We're like, cool, we can't send money to Ghana today. And obviously, the lower you go down on the pecking order, the higher the fee gets, of course. Hence why we picked those as number one. And we're like, all right, we're fed up with all of this. Can we actually build our own? Obviously, this takes a lot of work, of course, right? You need relations with the regulators, the banks. We need licensing, which we do have across all of our licensing now in Africa, which are known as letters of no objection. Or we've got like approved partnerships with like Ghana is a good example. If you want to work with Ghana, you can't directly work with the Bank of Ghana, but you go for a company called BigPay. who's their, let's say, their preferred partner, right? So, and that's how that works then. So we're like, cool, we're gonna build our own thing, built it. And then one of our competitors gave us a call one day, like, hey, how are you getting money into X country? And we said, oh, we built our own thing. And they're like, cool, could we use you? We're like, yeah. I think any company that builds something where the competitors of your B2C product they're using is a good thing, right? This then allows us to think about lots of other different things, right? You know, think about— so B2B, cool. How else can we like monetize that? We can look at maybe local collections. So then as a business like Uber, example, they operate in Ghana and they always want to move their money out from local currency into USD, right? As an example, because of volatility reasons. So instead of having to go through a broker who charges a fee to then get it into another bank who charges a fee and then transfer it for another fee, You could log into Rafiki's dashboard like right now, like, hey, I want to convert from X currency to Y currency. And we're like, cool. And because we're dealing with it domestically, like we're already moving money to that country already, it doesn't cost us more to send more, right? And that's one thing we need to do more about. And obviously that's very favorable. Also B2B-wise, we're thinking more about like our own private ledger that we've been building, which is why actually I'm talking to you right now. Like that's one of the big projects that we're working on. And obviously we need to expand across more countries, basically. Like, that's the aim of the game. Like, we don't just want to be known as like an African payments company or like an Asian payments company. Like, that isn't— like, that was the goal at one point, whereas now moving more towards like global accounts. So the idea of NALA now is you can actually download NALA on our— if you go for our waiting list, and you can download NALA and just get paid in USD anywhere. Which is working out quite well for us so far, and people are quite happy.
> 
> 
> ### 00:10:50
> 
> **Kasper Bentsen:** That's pretty cool. Like, my— a good friend of mine married a Vietnamese girl, and he makes quite a bit of money, so he put some savings into a Vietnamese bank with an 8.6% interest rate, but he's like, I can never get that back out of Vietnam.
> 
> 
> ### 00:11:06
> 
> **Ryan Bolton-Smith:** Yeah, yeah.
> 
> 
> ### 00:11:07
> 
> **Kasper Bentsen:** But he would be able to with NALA.
> 
> 
> ### 00:11:09
> 
> **Ryan Bolton-Smith:** Yeah.
> 
> 
> ### 00:11:10
> 
> **Kasper Bentsen:** That's cool.
> 
> 
> ### 00:11:11
> 
> **Ryan Bolton-Smith:** Yeah, I mean, yeah, technically speaking, I mean, like I said, I don't know the ins and outs of Vietnamese banking laws, so I won't say yes to Vietnam. But yeah, the idea is—
> 
> 
> ### 00:11:19
> 
> **Kasper Bentsen:** Yeah, okay, no, that's cool.
> 
> 
> ### 00:11:22
> 
> **Ryan Bolton-Smith:** Um, and obviously, you know, B2B, we're already doing stablecoin actual payments already. Like, we're already actually doing it. Like, we're not just saying that, we've actually executed payments already with stablecoin. And most of the time, there's actually some interesting arbitrage opportunities with it. So, you know, just make money for the sake of just moving it. But also we found some interesting opportunities where currency, like, you know, we know, you know, our country managers who are like in-country, like, hey, this thing's about to happen, you need to like, you know, dump currency. And we just move into USD too. So yeah, it's working quite favorable for us at the moment. And also on the B2C side, an interesting one is that we're not just caring about people sending money from the US and Europe to Africa and Asia.
> 
> 
> ### 00:12:02
> 
> **Kasper Bentsen:** Yeah.
> 
> 
> ### 00:12:03
> 
> **Ryan Bolton-Smith:** A lot. And that's what all of our competitors focus on that. And that's all they care about. And, you know, wires do $100 billion a year, $100 billion in just money transfers. We do $1.2 billion. We're a very small fish in the grand schemes. But we also listen to our customers quite frequently in the sense that we're actually enabling and have enabled already bilateral flows now. So it doesn't— like if you're in London sending to Kenya, it doesn't actually— if you go to Kenya, you can now send over to Europe and US from Kenya. And also same for Uganda and also same for Tanzania. So these are 3 that we've done recently. And it actually increases our gross profit margin by 88%, which is absolutely crazy.
> 
> 
> ### 00:12:42
> 
> **Kasper Bentsen:** Wild.
> 
> 
> ### 00:12:44
> 
> **Ryan Bolton-Smith:** Yeah, well, because again, because of like how this all connects, you imagine we're collecting local— we collect that currency locally on the B2B side, which means we get very favorable rates. And because there's always a dollar shortage that we can obviously use on. And then also because basically Rafiki's model is legal regulatory integration, Nala comes along as its own product, sits on top. And the way that you can, in a way that you can view it, it's like Rafiki is Nala's preferred customer. You know, it's how we do it. And that leads to why we have to call it a different name, as I mentioned earlier.
> 
> 
> ### 00:13:17
> 
> **Kasper Bentsen:** Yeah, yeah.
> 
> 
> ### 00:13:18
> 
> **Ryan Bolton-Smith:** So hopefully that all makes sense. So you now know everything you need to know about Nala and Rafiki.
> 
> 
> ### 00:13:23
> 
> **Kasper Bentsen:** Yeah, no, I think it does. Like, so the B2B model is kind of pooling cash somewhere, and because you're sending a lot of it across borders, you can just pile more on top and pay the transaction fee for a lot of stuff at once. And that's why you can—
> 
> 
> ### 00:13:40
> 
> **Ryan Bolton-Smith:** It depends on currency by currency, to be really honest. But overall, yes, in a way. Like, you know, we did— our volumes are Between 100 to 120 million a month approximately. So people are depositing money into Nala, which we're then using. We've also obviously got our own personal reserves as well, or business reserves of course, that we use to get favorable deals as well. And obviously we're then just reconciling every day. So like, you're off— like, we've, we've got our own treasury department and even our own trading department as well. And so every day, like, you know, I go to the London office fairly frequently, so I hear the trades every day. Oh, hey, like I need NGN. I need to convert to USD, or I need this because of these reasons, or whatever it might be. And obviously, the whole idea is that this is all driven by our pricing engine of basically estimation to a degree of like right. We know roughly on the 18th of February last year we did X, so it means we probably need Y. You know, this time round, based on these growth events that we've experienced, and obviously obvious things like the 25th of every month or 24th of every month. onwards, we know that we need a higher reserve cap because of course that's when everyone's getting paid. So yeah, in a way, yes. So most importantly, let's talk about you, Kasper. Yeah, so you're at 90 POE. So first of all, like, how come we're chatting today? Like, has something changed for you recently to make you start looking, or is it just a case of I sent a message and you thought, why not?
> 
> 
> ### 00:15:04
> 
> **Kasper Bentsen:** Well, both. Um, 90POE was acquired not fairly long, like maybe a year, a little bit under a year ago.
> 
> 
> ### 00:15:13
> 
> **Ryan Bolton-Smith:** I did read about that, yeah.
> 
> 
> ### 00:15:15
> 
> **Kasper Bentsen:** And that always comes with new leadership, right? And new leadership is, uh, well, new leadership in tech companies, there's a, there's a very big tendency that talent leaves when leadership changes, and you feel it. My team has not been directly affected that much, but You could just feel that the organization is not the same anymore, and the processes are changing, and it's being more driven by KPIs. And, you know, you know, there's a, there's a really good way of thinking about it. It's like Microsoft when Bill Gates was there. It was all about innovation and love for the project. And then Steve Ballmer took over, and it was just execution phase from there, just making money no matter what. And that was the only thing. That's kind of the phase that we're entering in now, I feel like, in 90POE. And that's not a fun phase anymore.
> 
> 
> ### 00:16:03
> 
> **Ryan Bolton-Smith:** Yeah, yeah. It's like when the game publishers, right, they get bought by the big studios and then next thing you know, it's like disappeared. Yeah, yeah, for sure.
> 
> 
> ### 00:16:10
> 
> **Kasper Bentsen:** Exactly.
> 
> 
> ### 00:16:11
> 
> **Ryan Bolton-Smith:** Fair enough. So if we focus on, I suppose, in what you're looking for now that you've had time to reflect about this, like what is it that is on the list?
> 
> 
> ### 00:16:23
> 
> **Kasper Bentsen:** So I'm looking for something interesting. First of all, I like interesting problems. I don't just Like, if I don't care about the product, I don't really want to be there, uh, because why waste my time on something boring?
> 
> 
> ### 00:16:40
> 
> **Ryan Bolton-Smith:** Sure.
> 
> 
> ### 00:16:41
> 
> **Kasper Bentsen:** But I also look for technical challenges, but also for places where I can have big impact. Like, if you want someone who just picks up the tickets off the board and just does the whole thing, like hire an engineer, give them AI, do the thing, like I have my experience behind me. I know what to do. Like, you hire me because you want something who knows how to build systems, and I like to build systems and good systems. That's very important, good systems, because oh my God, those systems where you're just told just make this work, we'll fix it later. Like, nothing is as permanent in tech as a temporary solution. I get that those are required sometimes. But if it's the norm, that's very not a good sign. And I think fintech for me has always been interesting. My previous employer, who I really was really fond of, he started Lunar, which unfortunately I had a clause in my contract that I could join. So I never got to go there, but it was very interesting following his journey and Some of my friends work there, and that's cool.
> 
> 
> ### 00:17:58
> 
> **Ryan Bolton-Smith:** Awesome. So when we think about, let's say, like, because also I know 90PO has got a huge engineering team, like, what team do you actually work in?
> 
> 
> ### 00:18:06
> 
> **Kasper Bentsen:** I'm in procurement.
> 
> 
> ### 00:18:07
> 
> **Ryan Bolton-Smith:** Procurement. Okay. How big is procurement?
> 
> 
> ### 00:18:14
> 
> **Kasper Bentsen:** Yeah, procurement is like—
> 
> 
> ### 00:18:16
> 
> **Ryan Bolton-Smith:** I'm sorry, not the entirety of procurement of everything, obviously, I think that'd be very large. But like, in terms of like, when you're in your standups every day, is that like, is it 5 people, 6 people? Is it backend and frontend? Like, that's what I'm just trying to get an understanding of.
> 
> 
> ### 00:18:29
> 
> **Kasper Bentsen:** Yeah, yeah, no, we're a cross-functional team. So it's backend and frontend. It's a PO, it's a team lead. And we're like, we just hired 2 more backenders. So now we're 7, 8 in the team, and we're really supposed to be like 5 teams that size. Procurement is massive.
> 
> 
> ### 00:18:55
> 
> **Ryan Bolton-Smith:** Cool, awesome. All right, and how do you all work together? Like, I do— I guess, is it sprints with scrums every day? I, I—
> 
> 
> ### 00:19:03
> 
> **Kasper Bentsen:** yeah, so this is one of the, one of the things that with the new process that leadership brought about, they now want 3-month roadmaps. We have Scrum, but we have to fit into 3-month roadmaps, and those roadmaps become deadline maps. So we have to follow them to the letter and just deliver, but pretend we're doing Scrum at the same time. So we're somewhere in between waterfall and Scrum, which is not ideal.
> 
> 
> ### 00:19:32
> 
> **Ryan Bolton-Smith:** Yeah, fair. Okay. In that case, like I mean, I'll give you an idea. We kind of do that, but like we've only just started doing it just because basically it was a bit of like a fire show for us is how I would describe it, which is like, cool, we're just gonna work on stuff. And then, uh, which is fine, but obviously priorities just always change. So at the start of the quarter, we come up with like, instead of having like fixed deadlines, we're like, cool, right, this is what we're aiming for from a, like, how we, how we'd like to structure it. Is right. Okay, and sorry, someone's at the door.
> 
> 
> ### 00:20:11
> 
> **Kasper Bentsen:** And nice.
> 
> 
> ### 00:20:11
> 
> **Ryan Bolton-Smith:** I would like to structure it like, okay, so what we're thinking about is we want to get this many customers and grow revenue by this much, and we think if we do A, B, C, and D, that will help us achieve those goals. And, and obviously that's down to leadership to make those decisions, and obviously that is in a Combined effort with the head of engineering, every engineering manager here, every product manager, pricing, and et cetera. So it isn't just heads of like one person who isn't actually attached to the business and going, cool, do these things. It's like, but they're very well thought out. But also, just to be abundantly clear, I've seen it many a times where it's like, oh, actually this thing just happened and we now need to just dump that roadmap and actually focus on this thing instead, because if we don't, the business is going to lose $20 million in revenue or something.
> 
> 
> ### 00:20:57
> 
> **Kasper Bentsen:** Yeah. Yeah, of course. And that's roadmaps, right? Roadmaps are designed to be changing. They're supposed to be just, we're doing this and then we're doing this and then we're doing this. And if it takes 2 weeks more to deliver one thing, that's okay. You just— the roadmap is not supposed to have like to-the-day dates.
> 
> 
> ### 00:21:15
> 
> **Ryan Bolton-Smith:** Oh yeah, for sure not. No, for sure.
> 
> 
> ### 00:21:16
> 
> **Kasper Bentsen:** Unfortunately we do, and our customers see them and we have to deliver on that date.
> 
> 
> ### 00:21:21
> 
> **Ryan Bolton-Smith:** Fair. Okay, not cool anymore. Noted.
> 
> 
> ### 00:21:26
> 
> **Kasper Bentsen:** I'm not sure. It's it's a new thing. I'm hoping it's just a trying thing, and they realize that it that doesn't work, and they're going to change it again. That's my hope.
> 
> 
> ### 00:21:35
> 
> **Ryan Bolton-Smith:** Fair, fair. Um, that makes sense. So in terms of tech stack, I mean, I've chatted with a few people at Niner PoE over the years. I imagine you're in the same tech stack as everyone.
> 
> 
> ### 00:21:48
> 
> **Kasper Bentsen:** Like yeah, go yeah yeah go Postgres. SQLite, Kafka, all the buzzwords for today. Well, except Rust.
> 
> 
> ### 00:22:00
> 
> **Ryan Bolton-Smith:** All right, awesome. And then let's think about a few different things then. So in that case, what I'd like to do is I always like to run through like a few kind of common technical scenario questions, if you wish. But basically these are given to me by the engineers, and again, none of these are meant to get you off your toes. These are just normal things that we think about. So we just want to see how you approach the problem.
> 
> 
> ### 00:22:23
> 
> **Kasper Bentsen:** Sure.
> 
> 
> ### 00:22:24
> 
> **Ryan Bolton-Smith:** So first and foremost, if we're thinking about users on a slow connection— so when I say slow, I don't mean that, oh no, my 5G has gone to 4G. I mean very slow, you know, talking by the byte. So how would you prevent— if one of our customers clicked send money 3 times in a second, how would you make sure that that money is actually only going to be sent once?
> 
> 
> ### 00:22:53
> 
> **Kasper Bentsen:** Yeah, there's a lot of options. The easiest way is just a simple optimistic offline lock. It depends. So the actual lock that you're going to use is going to be dependent on whether your transactions are really heavy and really hard to roll back. If they're like very light and you just go in, try to acquire the lock, you didn't get it, go back. That's pretty fine for optimistic offline locking. You just go in there, you have a key that you got when you fetched the data, you try to send it, the server will say, hey, something, you're already processing something, like you give it a nonce. And if that nonce is not allowed anymore, you break it. Now, it's not very common in just send scenarios. It's more common when you fill a form and you see if someone changed stuff while you were doing things. So for sending, you would traditionally, like, obviously you You do the frontend thing, you don't allow it to multiple send, but it can go wrong. You can do the thing for sending. Yeah, I think non-syncing is a really good approach. I think having a lock on saying, okay, your user cannot— you're already processing like a send in the database. It all depends on the database that you're using too. But again, it depends, right? There's, there's so many ways to do this depending on what stack we're actually talking about.
> 
> 
> ### 00:24:35
> 
> **Ryan Bolton-Smith:** Oh, for sure. Yeah. I mean, like you've got idempotency, you've got distributed locking is another way. Again, some are, some are quite complicated. Some aren't, right? Yeah. Yeah.
> 
> 
> ### 00:24:44
> 
> **Kasper Bentsen:** So idempotency, that was, that was the word that I was trying to get to, but that's the nonce thing that I was trying to explain. You have a nonce, you make sure that you don't reprocess.
> 
> 
> ### 00:24:55
> 
> **Ryan Bolton-Smith:** I got you. I got you. Yeah, perfectly fine. Like I say, there are many, many ways to approach it. And like I say, you've listed the main ones, which is always good.
> 
> 
> ### 00:25:03
> 
> **Kasper Bentsen:** Yeah.
> 
> 
> ### 00:25:04
> 
> **Ryan Bolton-Smith:** So the next one then, if you now go a step more, no, it's not more complicated, just different kind of problem. So at NALA and Rafiki, as you might guess, as you know, right, we deal with millions of transactions every day or month or week. It all depends on the day and the time. If the product team were to come up to you and be like, hey Kasper, we want you to create a report for us that can check how many unique users have transacted in the last 7 days, keyword being unique users. How would you design such an implementation?
> 
> 
> ### 00:25:36
> 
> **Kasper Bentsen:** Oh my God, that's such a depends question as well.
> 
> 
> ### 00:25:39
> 
> **Ryan Bolton-Smith:** Well, we use— I can give you the full bounty full of our tech stack and stuff. We love Postgres, that's our thing. We love Hex. Well, we love loads of different tools. We'll use the right tool for the right job.
> 
> 
> ### 00:25:52
> 
> **Kasper Bentsen:** Yeah, yeah, okay. So assuming that there's some kind of system that tracks sign-ins, like maybe that's the question, to design a system that tracks sign-ins and actual user interactions and stuff.
> 
> 
> ### 00:26:10
> 
> **Ryan Bolton-Smith:** Yeah, you can assume that we track the obvious things, you know, event IDs, user transactions, user ID, login, because obviously, you know, as you might imagine, we've got a pretty complicated KYC you know, thing you have to go through in order to log in. We're very, very aware and acutely aware of account takeovers, actually quite common in certain regions for us as well, unfortunately. So you can assume we've got the obvious things.
> 
> 
> ### 00:26:32
> 
> **Kasper Bentsen:** All right, great. So we have the events, we're tracking the events. The worst thing you can absolutely do is put that pressure onto the production database, the load-bearing database. You want to have this in a secondary system that does not affect the performance of the running system. So you can have again a few different ways you can do this. The way that I kind of like is that all of these things become events. You put them on Kafka, you have a consumer somewhere, and based on the report that you want, based on the type of reports that you want to generate, you can have multiple consumers putting into different reporting systems. And there can be one purpose-built for user management tracking, user login tracking, all these things. But you can also have a lot of different types of events based on the same events, which gives you the— you want to decouple the actual production, the product engineering teams from the data platform teams. And by events, you have a shared contract that you don't have to mess with each other's work ever. You don't have to put event code into the production code, and you don't have to put production code into the report code.
> 
> 
> ### 00:27:46
> 
> **Ryan Bolton-Smith:** Excellent. And everyone's happy.
> 
> 
> ### 00:27:48
> 
> **Kasper Bentsen:** Everyone's happy.
> 
> 
> ### 00:27:49
> 
> **Ryan Bolton-Smith:** Excellent. Yeah, good approach. Thank you. Appreciate it. In the wonderful world of— so that scenario is now finished. Moving on to the next one.
> 
> 
> ### 00:27:58
> 
> **Kasper Bentsen:** Sure.
> 
> 
> ### 00:27:58
> 
> **Ryan Bolton-Smith:** If we think about the wonderful world of AI, because of course no interview these days would be complete But what we're actually interested in understanding from you is how you actually like to work with it. Like, if we go from, hey, Kasper, build this thing, and we go all the way through to it's launching and it's working, it's in prod, etc., and you've not broken prod, which is great, you know, it all works. Like, where'd you like to use it? Like I said, and obviously this answer could be— there's no right or wrong here, it's just we're just trying to understand your approach.
> 
> 
> ### 00:28:30
> 
> **Kasper Bentsen:** Yeah, yeah. Yeah, yeah, I'm very distrustful of AI. I know how it's built, I know how it works. So it's, it's not, it's not the end-all be-all. And I like to take boring tasks that I fully understand and give that to AI and just say, do this thing for me.
> 
> 
> ### 00:28:47
> 
> **Ryan Bolton-Smith:** Sure.
> 
> 
> ### 00:28:49
> 
> **Kasper Bentsen:** If let's say I'm joining your company and I'm new there, I will not be using AI unless to explain me things that I specifically ask for. I will not be using AI at all for a period just so that I get a feel for the system. I get to understand the system. I understand what is the boring parts. But so boring parts, easy. But the more I understand, the more I can offload to AI. Yeah, but I'm also, I'm very, very wary of AI because there's this notion of, I don't think AI solves you digging holes. If you're digging a hole, AI makes you dig the hole faster.
> 
> 
> ### 00:29:27
> 
> **Ryan Bolton-Smith:** So I think it's important also to have your Sorry, I said it, and it loves to agree with you on the way down as well.
> 
> 
> ### 00:29:35
> 
> **Kasper Bentsen:** Yes, exactly. It doesn't ask questions. So what I like to do is have my hands-on, understand if the abstraction we're using is that good. Like, why do I want to use AI for this? If something sucks from an engineering point of view, maybe we should just fix the problem earlier in the pipeline, and I can write smaller code, better code, and I don't have to use AI as much. But I also think it's very— so we're under heavy deadlines right now, 90 POE, so we use AI a bit more now than I'd like to. But yeah, and again, if it's a complicated problem, I like to write the core of the problem myself and then maybe ask AI to fill out the blanks if I want to. The only thing that I cannot accept Is if someone writes AI code and do not even review their own code before they send it to code review, like you have to understand what you're doing. It's your responsibility, your code, no matter if AI wrote it, it's your code. So you have to own it.
> 
> 
> ### 00:30:36
> 
> **Ryan Bolton-Smith:** Cool. Yeah. Happy, happy with what you said in the sense of like, we work with, like we work at AI with, we trust, but we verify, right? Like with anything in life that most people do. One of the things that we like to— we like to give it menial tasks that deal with stuff that simply, like, once we, once we understand, obviously, the context and the core of the problem, we're like, cool, this is what I'm expecting. Can you do these basic things? Almost like if you were to give it, like, to an intern of sorts, so to speak. And we do use it a lot for design. However, just be very clear, when I say design, I'm not saying it's giving us our design choices. We have very, very well documented Notion pages as our preferred knowledge center, um, of how we think about architecture and how we think about design, and even extensive documentation on how do you write PRDs, RFCs, ARGs, and so forth. That is very extensive, and almost some people actually say it's overly documented, but hey, it's a good problem to have. Um, but we give you an idea of the ideal kind of person that we're after is if you get given a very difficult problem to solve we would like it if someone said to us, I'd like to use a pen and paper to sketch our architecture, or a whiteboard, you know, whatever your preferences. Um, but like, that's how our engineering managers work here. So they're all really hands-on, all really, you know, up to date with all the architecture that's going on. They've got a lot of cursed knowledge of just because they've been here a while. Um, and yeah, documented enough. Same with you, I would guess, as well. Um, and also all of our engineering team here as well, you know, they're all really senior. They're all very competent in what they do. Again, they like to use it to basically generate the design docs of their thought process of like, right, this is going to be our approach based on this context. This is how we're going to do things. Obviously, by all means, by the way, we've used AI for lots of fun stuff as well. For fraud detection, we've got loads of stuff that we build in Hex and a few other custom fraud detection models that we've built over the years that we're now using AI to just improve. improve that for us. And we've also— we're also wanting to create it to basically like, you know what I mentioned earlier of all those bad APIs that we deal with and then obviously wasting engineering time because our team are then reaching out to the team like, hey, we've tried this and it's done this, why? We're actually trying to make an agent that can basically execute basic calls and it's like, if you get this response, send a message to said person and be like, hey, why? Again, just to save time for people. Um, yeah, lots of interesting stuff, but at the end of the day, it's like pen and paper, so to speak, is like how we'd like to think about things. Because the problem that we've got isn't a scaling problem. Like I say, spinning up new things is easy, right, to a degree. But like, the problem we've got is the velocity of our scale that happens in very, very quick bursts.
> 
> 
> ### 00:33:25
> 
> **Kasper Bentsen:** Um, yeah.
> 
> 
> ### 00:33:26
> 
> **Ryan Bolton-Smith:** if we turn on a— like right now we've got a waiting list of over 100,000 people on our app just because there's been— there was a very small compliance issue with like the per— we use something called Modulr who like allows us to piggyback off their licensing, right? Very standard practice for any EMI, electronic money incentive company basically. And like, so for the US, it's all— we're onboarding customers every single day, but then like UK and Europe, there's like this problem with this annoying new compliance law that came out that we wasn't told about by our licensing. And we're like, oh, so we had to pause customer sign-up just temporarily. And like I said, we've got tens and tens of thousands of these customers now all signed up ready out the gate. So as soon as we open that, that's probably going to cause some problems for us. And we also do get a lot of problems with referral fraud as well, unfortunately. I'm sure, like, yeah, yeah, over the years.
> 
> 
> ### 00:34:20
> 
> **Kasper Bentsen:** It was horrible with this.
> 
> 
> ### 00:34:22
> 
> **Ryan Bolton-Smith:** Yeah, it's pretty, uh, yes, it's pretty grim. But yeah, hey, you know, we do our best.
> 
> 
> ### 00:34:26
> 
> **Kasper Bentsen:** Um, yeah, cool.
> 
> 
> ### 00:34:28
> 
> **Ryan Bolton-Smith:** All right, well, look, thanks for answering all my questions there. Um, well, no, it's just basics then. In terms of notice period, what do you want? Is it 3 months or 2 months?
> 
> 
> ### 00:34:40
> 
> **Kasper Bentsen:** Ah, uh, it's either 1 or 3 months.
> 
> 
> ### 00:34:42
> 
> **Ryan Bolton-Smith:** 1 or 3. Okay, cool. Double-check that because I'll make the team either really happy or really sad. With regards to the right to work, you're based in Denmark. So do I guess you are local to Denmark yourself? Yes. In terms of your passport or permit that you have?
> 
> 
> ### 00:35:00
> 
> **Kasper Bentsen:** Yep.
> 
> 
> ### 00:35:01
> 
> **Ryan Bolton-Smith:** Yeah. Cool. Cool. Sorry, let me just write this down. So I just need to write that you're Danish, right? Is that right?
> 
> 
> ### 00:35:13
> 
> **Kasper Bentsen:** Yes. Yes. Danish.
> 
> 
> ### 00:35:14
> 
> **Ryan Bolton-Smith:** Okay.
> 
> 
> ### 00:35:15
> 
> **Kasper Bentsen:** Cool.
> 
> 
> ### 00:35:17
> 
> **Ryan Bolton-Smith:** So salary expectations is the next one. However, I'd like to prompt you with a few different things before you give me an answer. Anyone that's outside our UK entity, we put on B2B contracts. And this is a very, very standard arrangement. I'd be more than happy to get you on a call with Christos in Greece and Alessandro in Italy, or many, many people that we've got all over the place. And it normally works out more tax efficient for those people. Just in the UK, we're not allowed to do it because of Certain laws.
> 
> 
> ### 00:35:47
> 
> **Kasper Bentsen:** Yeah, same with Denmark.
> 
> 
> ### 00:35:49
> 
> **Ryan Bolton-Smith:** Okay, good. So that's the agreement that we'd have for you. We design the contract to be indefinite. And just be abundantly clear that just because you are a B2B contractor, you will still get holiday pay at 35 days per year. You're still legally entitled to all forms of sick pay and all associated benefits like paternity leave and so forth, and our L&D budget, which is $1,000 per year as well. However, of course, to be abundantly clear, this means that we do not give you money for pension contributions. This also means that you would be personally responsible for your yearly or quarterly taxes, however your country likes that. And so obviously there is a slight cost to you in terms of accountant, unless you're very confident in tax law. Um, but, um, so with that being taken into account, um, is there a banding of which that Is where we're looking.
> 
> 
> ### 00:36:40
> 
> **Kasper Bentsen:** So that's, that's almost exactly the same contract as I have now. Okay, let me just— do you want them in euros?
> 
> 
> ### 00:36:49
> 
> **Ryan Bolton-Smith:** Yeah, euros is fine for me. Yeah, I mean, we are an international money company, we can pay in any currency. Yeah, we'll pay—
> 
> 
> ### 00:36:55
> 
> **Kasper Bentsen:** I'll just— we, we still use Danish crowns in Denmark, so I always have to convert the numbers to something else.
> 
> 
> ### 00:37:03
> 
> **Ryan Bolton-Smith:** You can get paid in Kroner, if you want. What would you prefer?
> 
> 
> ### 00:37:10
> 
> **Kasper Bentsen:** It doesn't matter right now. It's just we're tied to the euro, so it doesn't matter. It's always the same exchange rate almost. It's just to communicate the expectation. It will be easier if we agree on the same currency. Right. So I'm thinking somewhere about Uh, €11,500 per month and above.
> 
> 
> ### 00:37:43
> 
> **Ryan Bolton-Smith:** So just to be clear on my side again, so that's €138,000 per year based on 11.5 times 12. Yeah. Okay, cool. And like I say, I have to ask because, you know, I am a recruiter, it's kind of my job. Is there flexibility there? I mean, obviously if we can give you more Obviously we'll do our best, of course, but like at the same time, if they were to come in a bit lower than that, like how much flexibility is there within that number?
> 
> 
> ### 00:38:12
> 
> **Kasper Bentsen:** The flexibility of the number depends on how cool I find the job itself and the job description and everything. Okay. I would say there's some margin in there.
> 
> 
> ### 00:38:23
> 
> **Ryan Bolton-Smith:** Okay. Yeah, as long as, again, it's always, it's just these questions I like to ask because basically What happens sometimes is someone says, right, I want this figure. And I go, okay, that's near, you know, near, not top end, but like near-ish the top end. And all it means is that the expectations on you are therefore higher. And it's like, if you're cool with that, great. Yeah, no problemo. But then, because I think sometimes, again, maybe it's just my personal view on things, but sometimes when I come to companies and they're like, hey, we want to give you offer A or offer B, and I'm like, all right, I'll take the lower base and like the higher equity.
> 
> 
> ### 00:38:54
> 
> **Kasper Bentsen:** Yeah.
> 
> 
> ### 00:38:54
> 
> **Ryan Bolton-Smith:** For now and I'll see how I feel about it. And then if I'm like, oh, actually cool, this actually works. I know I can always get more money, but you can't always get more equity, right? Which is kind of my logic anyway. Awesome. All right. Yeah, that makes sense. Cool. Let me write that down.
> 
> 
> ### 00:39:12
> 
> **Kasper Bentsen:** Sweet.
> 
> 
> ### 00:39:13
> 
> **Ryan Bolton-Smith:** So any questions for me at this point, Kasper, I can help you with other than next stages, which I'll explain in a moment for you?
> 
> 
> ### 00:39:22
> 
> **Kasper Bentsen:** Um, well, you already mentioned the funding. Uh, do you know what, what is the current burn rate and roadmap? Like, when is the next funding round expected, and how much of it is— like, which percentage of the current burn rate is self-funded?
> 
> 
> ### 00:39:42
> 
> **Ryan Bolton-Smith:** Uh, I mean, some of the stuff I'm allowed to talk about publicly, some of it I'm not. It's not something that companies like to talk about, right?
> 
> 
> ### 00:39:50
> 
> **Kasper Bentsen:** Yeah, yeah, just whatever you can say, you probably do.
> 
> 
> ### 00:39:53
> 
> **Ryan Bolton-Smith:** So in terms of the next funding raise, we're probably going to announce it in the next few weeks. We are in late stages with a number of investors, existing investors as well, like existing and new ones as well. And we'll probably announce our Series B more formally in the next few weeks. We could have done this last year when we did our debt raise, But because our volumes wasn't where we wanted them, we're like, we're kind of negotiating from a place of weakness. And now even if you go on our CEO's kind of LinkedIn page, he talks about publicly of how we've had our best quarter, um, ever, or even like the best fit, the most profitable month ever. Like Benjamin Fernandez, or Benji Fernandez, is his LinkedIn. He's quite public about a lot of progress that we make as a company as well. Um, however, burn rate and so forth in those calculations, you Yeah, we never talk about those publicly.
> 
> 
> ### 00:40:42
> 
> **Kasper Bentsen:** No worries.
> 
> 
> ### 00:40:44
> 
> **Ryan Bolton-Smith:** However, when you—
> 
> 
> ### 00:40:45
> 
> **Kasper Bentsen:** Oh, you kind of answered the soon new funding round. That's good enough.
> 
> 
> ### 00:40:50
> 
> **Ryan Bolton-Smith:** Yeah. Yeah, like we need to because they want to go into the global accounts, as I mentioned earlier, stablecoin stuff, but also what they want to go into LATAM as well. They want to get into Mexico as well, like really as fast as they can. I think it's number 1 or number 2 in the world in terms of remittances. Um, Philippines is number 6 in the world. Don't know if you know that, but it shocked me. I didn't think it would be number 6. But, um, yeah, it goes like China, China, India, Mexico is like top 3. Um, and obviously it's like, it's not as easy just going, cool, we'll announce that we can get in there. Like, it's an extremely competitive landscape, so you need obviously a lot of money to be able to get the good deals. I would also be on physical cards. Just as a little thing at the end as well.
> 
> 
> ### 00:41:39
> 
> **Kasper Bentsen:** All right. And how many employees are there currently at NALA?
> 
> 
> ### 00:41:42
> 
> **Ryan Bolton-Smith:** Total, I think 155 now. Could be—
> 
> 
> ### 00:41:46
> 
> **Kasper Bentsen:** 155.
> 
> 
> ### 00:41:47
> 
> **Ryan Bolton-Smith:** Yeah, could be wrong. Like when I joined, like I said, when I joined September 2024, there was only about 85, 90. There you go. Sorry, I just got the update for you guys. It is, sorry, 149 people. There you go. Exactly.
> 
> 
> ### 00:42:00
> 
> **Kasper Bentsen:** Okay, well, that's a respectable number, but not too small, not too big.
> 
> 
> ### 00:42:04
> 
> **Ryan Bolton-Smith:** Yeah, yeah, like I say, look, we've got, you know, we've got like a lot of that, like only of that, only about 15 of that is backend engineers. And you might think, well, that seems like quite a small proportion. However, you need to take into account that we've got a lot of customer support staff. So we've got a huge office out in Kenya, you know, in Nairobi. We've got lovely— yeah, everyone loves the office out there. And then we also flew everyone in the company 2 years ago to Zanzibar, which is just to the east of that. And that was a super fun trip apparently. You'll see that on our careers page where everyone dressed in the all-white party. Yeah, so we've got a big collection of people there. We've then got loads of people scattered around kind of Europe in general. There's another headquarters in London where I live several miles from in Canary Wharf. And then we've then got a really small WeWork in New York because that's where our CFO is in Brooklyn. And then Benji, like basically like the execs, like Nico and Benji, like they've co-founded— well, Benji founder and Nico co-founder. And they basically just, they're just on like a constant rotation around the world really, like San Fran, New York, London. Nico stops us in Switzerland because he's Swiss. And then Benji's then going back to Tanzania and Kenya as well. So They just kind of constantly travel throughout the world, all to our different presences as well. So like, however, you'd be happy to know that every now and then, like every maybe, maybe once or maybe even twice a year, we'll fly everyone in over from Europe over to the London office just so you can all hang out for a week. Obviously all expenses on us, naturally. And yeah, that's it.
> 
> 
> ### 00:43:44
> 
> **Kasper Bentsen:** Okay, so does that mean that everyone, all of the engineering team is remote?
> 
> 
> ### 00:43:49
> 
> **Ryan Bolton-Smith:** Um, some of them, most of them are, yeah. But we've got, um, all of them are just in Europe though. There's no offshore in here, just to be abundantly clear. Um, but it's all in Greece, Italy, Portugal, Denmark. Um, we've got actually, we actually do have a guy in Denmark, but he's not an engineer though, he's an operations manager. Um, oh cool. Um, or was he, was he moved now? He might have moved over, I can't remember. Um, it's hard to keep track, but yeah, we've got people in Yeah, Portugal, France, Germany, you kind of name it from an engineering perspective. And then in the UK, in where I work, I work alongside Marcus. He's our head of engineering. Um, he's actually just— he's in the process of moving from— I think he's, he's either Austrian living in Germany or German living in Austria, one or the other. Um, I can't remember what it is, but he's about to move over formally, right, with his family, uh, to London for us. Um, and yeah, so I work with him and I work with like 2 or 3 of the other engineers who actually work on site in our office as well.
> 
> 
> ### 00:44:48
> 
> **Kasper Bentsen:** Okay. All right. And my final question, because I don't think you sent me any material on the actual job itself, any description or anything. Yeah, sure. You might have missed it if you did.
> 
> 
> ### 00:45:00
> 
> **Ryan Bolton-Smith:** Yeah, do you know what it is? Is that I don't like including links in my reach-outs because I think some people go, oh my God, it's probably like a spam link or something. So, but I'll send it to you here. This is the apply.workable link.
> 
> 
> ### 00:45:13
> 
> **Kasper Bentsen:** Um, all right.
> 
> 
> ### 00:45:15
> 
> **Ryan Bolton-Smith:** And that should just take you direct to a job that allows you to apply. Obviously you don't need to apply, of course. Um, yeah, that should give you hopefully a good overview. And we, we write in there hopefully good pieces of info of like, we write like the basics, like you should have this and what this, but we also put in there, we're trying to almost convince people not to apply, right? Like we're like, hey, the role isn't this. you're not just gonna be spoon-fed all day, like, what exactly you need to do. Like, this is a role where you really do need to think about, like, how you design and how you like to approach things. And like I say, the team here, I can say with full confidence, I've been doing recruitment for 15 years and I've worked with thousands of engineers these days. Many of the companies I've worked at, they're really competent, and here has been no different either. Like, when you see it, when all the engineers are in the office together, like, on, like, the offsites that we do every now and then, it's genuinely Nice to see people actually talking about, oh, actually, I didn't realize you're working on this. Have you thought about doing this before? And like actually having good discussion, um, versus just people just siloed and, you know, working on stuff, which of course happens from time to time, of course, from project to project. And, and also, you'll be happy to know there's no meeting Armageddons here of like you have to attend 12 hours a week of meetings. There is— they dedicate time. If I pull up, let's say, Bailey's diary, like one of the engineers, So this week.
> 
> 
> ### 00:46:36
> 
> **Kasper Bentsen:** Cool, that's great.
> 
> 
> ### 00:46:37
> 
> **Ryan Bolton-Smith:** Yeah, he's got like 3 hours of meetings and that's it.
> 
> 
> ### 00:46:40
> 
> **Kasper Bentsen:** Oh, nice, nice.
> 
> 
> ### 00:46:42
> 
> **Ryan Bolton-Smith:** Yeah. And cool, I appreciate we're a bit over time now. I'm pretty sure you probably want to go eat some food if you haven't already. Um, but if you're interested in proceeding, um, which hopefully it seems like you are, and the next stage is a pair programming exercise. However, just to be abundantly clear, it's not a LeetCode exercise. This is a real problem that we're deal with. It's to do with how we set limits for our customers. There's 5 limits to solve. I will give you everything you need to know, the zip file that contains everything you need to know 30 minutes before the call to get your environment set up. You are welcome to use AI for basics if you really want to. However, please have the on-screen prompts on your screen. If you just copy and paste everything over, as you mentioned, we'll just be like, hey, why have you done that?
> 
> 
> ### 00:47:20
> 
> **Kasper Bentsen:** Yeah, yeah, yeah.
> 
> 
> ### 00:47:22
> 
> **Ryan Bolton-Smith:** And yeah, that's it really. Like I said, I'll give you all the prompts that you need. I'll send you a self-scheduled link to chat with the engineers, and it'll be 1 hour in total.
> 
> 
> ### 00:47:30
> 
> **Kasper Bentsen:** All right, sounds good. Cool.
> 
> 
> ### 00:47:32
> 
> **Ryan Bolton-Smith:** All right, Kasper, it's been great. I'll see you in a while.
> 
> 
> ### 00:47:34
> 
> **Kasper Bentsen:** Yep, bye-bye.
> 
> 
> ### 00:47:35
> 
> **Ryan Bolton-Smith:** Cheers, bye.
