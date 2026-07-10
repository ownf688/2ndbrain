---
date: 2026-07-09
time: "09:30"
timezone: UTC
type: interview
interview_type: talent-screen
attendees:
  - "[[Ryan Bolton-Smith]]"
  - "Andrei Petrovich"
candidate: Andrei Petrovich
role: "Senior Backend Engineer"
duration: ~31 min
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/462894408"
tags: [meeting, interview]
---

# 2026-07-09 - Andrei Petrovich - Senior Backend Engineer Screen

> [!summary] TL;DR
> Andrei is a 7-year Go specialist currently at Delivery Hero (Germany), working on a high-integration cart service in a distributed microservices environment. Motivated by impact and technical growth, not management. Technical responses were directionally correct but lacked precision on fintech-specific patterns (idempotency, distributed locking). Comfortable with B2B contracting. Asking £140/hr gross. 3-month notice.

## Decisions

**Hire signal: lean yes - with caveat**

Andrei has the right foundation: 7 years exclusive Go, distributed systems, microservices, testing discipline (unit, integration, contract via Pact, E2E), and genuine curiosity about fintech. His motivation is authentic - he wants smaller company impact and more technical breadth. These are solid signals.

The caveat: when pushed on idempotency and distributed locking for double-spend prevention, he didn't land on the answer cleanly. He understood the problem space but needed Ryan to name the solutions. This is a flag for a backend role at a payments company, though not a blocker at talent screen stage. The pair programming and architecture stages will validate whether this is a knowledge gap or just interview nerves.

## Key discussion points

### Background & Experience
- 7 years exclusively Go. Based in Germany (near Swiss border), permanent German residency, no relocation needed.
- Current role: Delivery Hero, Transaction Tribe - Cart Service. Owns a high-integration service with ~20 upstream dependencies (catalog, payment, discounts, etc.). Team handles recalculation of prices, fees, discounts, and order placement.
- Previous: Fintech startup (cashback system) that failed to reach PMF - shows exposure to early-stage environments.
- Delivery Hero is shifting QA approach away from manual testers. Andrei's team uses unit, integration, contract (Pact framework), and E2E tests.
- AI usage: Heavy. Team has an internal bot that creates PRs from Jira tickets. Andrei uses AI daily, says his team "no longer writes code by hand" in most cases. Cautious about AI-generated RFCs - uses AI for summarisation and comprehension, writes his own prose.

### Role Fit
- Scalable systems: Yes, described managing high-fan-out service with complex integrations. Directional competence.
- Idempotency / double-spend prevention: Understands the principle (database-level guard in distributed systems, can't rely on client) but did not independently name idempotency keys or distributed locking (Redis/ETCD). Ryan had to prompt these.
- Unique user reporting at scale: Proposed a background worker to periodically aggregate data and serve the dashboard. Sensible, pragmatic approach.
- Testing: Solid. Multi-layer test strategy including contract testing with Pact, which is above average.
- Go: 7 years exclusive - likely strong, to be validated in pair programming.

### Motivation
- Wants smaller company, bigger impact. Frustrated by Delivery Hero's bureaucracy and slow pace.
- Explicitly not interested in management. Wants to stay hands-on and grow technically.
- Fintech/payments is genuinely interesting to him - he researched NALA before the call and understood the B2C/B2B model accurately.
- Understands the stablecoin angle and bilateral flows. Engaged with the business story.

### Logistics
- Location: Germany (near Swiss border). Permanent residency. No relocation needed.
- Contract: B2B only at NALA (no entity). Andrei queried indefinite B2B contracts - Ryan addressed it, Andrei was cautious but not opposed.
- Rate: €140/hr gross.
- Notice: 3 months.
- Availability for next stage: Reasonable - no blockers mentioned.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Moderate | Understood the product well. Cart service is inherently customer-facing but he didn't frame his work that way. |
| Play to Win | Strong | "I'm an engineer. I'm trying to find something more interesting to me to grow" - self-directed, proactive career mover. |
| Speed Wins | Moderate | "I had Delivery Hero, is huge company, everything is slow" - actively seeking faster pace. Uses AI heavily to accelerate. |
| Understand Why | Strong | "I use RFC to summarize, to understand, to teach me, to explain the problem, to connect the things together" |

## Propagation

### [[Ryan Bolton-Smith]]
- [2026-07-09, [[2026-07-09 - Andrei Petrovich - Senior Backend Engineer]]] Screened Andrei Petrovich for Senior Backend Engineer - "7 years exclusively Go, distributed systems at Delivery Hero. Directionally right on idempotency but needed prompting. Lean yes to pair programming."

### [[Hiring]]
- [2026-07-09, [[2026-07-09 - Andrei Petrovich - Senior Backend Engineer]]] Andrei Petrovich screened for Senior Backend Engineer: lean yes - strong Go background, solid testing discipline, missed idempotency detail unprompted. Rate €140/hr gross, 3-month notice, Germany-based B2B.

## Raw transcript

> [!note]- Expand transcript
> ## Call with Andrei Petrovich - Senior Backend Engineer - Transcript
> 
> ### 00:00:01
> 
> **Ryan Bolton-Smith:** Hello. Hey, Andrei, how are you?
> 
> 
> ### 00:00:02
> 
> **Andrei Petrovich:** Fine, thank you.
> 
> 
> ### 00:00:05
> 
> **Ryan Bolton-Smith:** Really well, thanks. Really well. So usually I sit up in my office, but unfortunately it's far too warm for me up there, so I'm just down here in the dining room today. Apologies for being late, I was just stuck in another call. Is now still a good time for us?
> 
> 
> ### 00:00:22
> 
> **Andrei Petrovich:** Sorry, could you repeat please?
> 
> 
> ### 00:00:23
> 
> **Ryan Bolton-Smith:** Is now still good for time?
> 
> 
> ### 00:00:24
> 
> **Andrei Petrovich:** Yeah, yeah, yeah, absolutely. Don't worry. Yeah.
> 
> 
> ### 00:00:28
> 
> **Ryan Bolton-Smith:** Awesome. Well, thank you very much. Um, I suppose, you know, look, the aim of every kind of first call, from my perspective at least, is, you know, I want to try obviously, you know, find out about your skills, your experience, and obviously for me to share more about, you know, NALA and the role and kind of where we've been and where we'd like to go. And, you know, if we're kind of both happy with what one another say, then, um, we can go on to the next stages and kind of take it from there. Sound cool?
> 
> 
> ### 00:00:51
> 
> **Andrei Petrovich:** Yep.
> 
> 
> ### 00:00:54
> 
> **Ryan Bolton-Smith:** Awesome. I mean, look, before we get into any kind of formalities, I mean, I'd love to just hear about you and, you know, what you've been up to over the years.
> 
> 
> ### 00:01:00
> 
> **Andrei Petrovich:** Yeah, let me introduce myself briefly. So my name is Andrei. I lived last, I would say, last almost 5 years in Germany. I'm a Golang backend developer for the last 7 years exclusively. I work in Go, with Golang, distributed systems, microservices, etc. Currently working in Delivery Hero. We are a big international delivery food companies and I'm a part of transaction tribe. Strictly speaking, it's a cart service. You know, every e-commerce service has a cart functionality. You add something to the cart, call a pizza, any other goods, remove something. We recalculate all the prices, all the fees, all discounts and return the result to the client. once the client is done, we place the order. That's, that's it. Uh, yeah, we work together with several engineers. We maintain and develop several services. Um, what else? I, yeah, uh, employer in Germany was a small startup. We tried to build this kind of cashback system. It was kind of fintech startup, very exciting, great opportunity to meet. Unfortunately, we didn't make, didn't meet, I think, product market fit. This company doesn't exist anymore. And that's it. Yeah.
> 
> 
> ### 00:02:31
> 
> **Ryan Bolton-Smith:** Awesome. Sounds great. And what would you say actually brings us here today? You know, obviously not implying that you're actively looking, but obviously you replied to a message, you set up a call with a recruiter working at another company, like Has something changed for you over the last couple of months to make you start looking, or just a case of saw my message and thought, hey, why not?
> 
> 
> ### 00:02:51
> 
> **Andrei Petrovich:** Well, I have a general idea that there are 2 goals I, I am aiming, I would say. First, I would love to work in a bit smaller company to avoid a lot of bureaucracy or a lot of overhead with communications and make a bigger impact. I had the Delivery Hero, is huge company, uh, everything is slow. And you know, the same engineers in the same position, even with the identical skills in the small company, usually have more opportunity to grow and more challenge, uh, more challenges, interesting challenges to solve, uh, and the impact on the business and the money is bigger than in, in a large company. Maybe it's a contradiction, but for me, I feel it. The second reason, I am trying to find something more interesting in terms of technologies. We are a bit focused on the single area, and I'm an engineer. I'm trying to find something more interesting to me to grow as a technical guy because I'm not a manager. I still develop. And that's it.
> 
> 
> ### 00:04:05
> 
> **Ryan Bolton-Smith:** And you enjoy being hands-on, I guess? And you enjoy being hands-on, so to speak?
> 
> 
> ### 00:04:11
> 
> **Andrei Petrovich:** Yes, you know, now because of AI, we changed dramatically our approach, but still I like to do something by hand and not only read and write documents. And now currently I have to read a lot, a lot of documents. Review, read, less write. But yeah, awesome.
> 
> 
> ### 00:04:36
> 
> **Ryan Bolton-Smith:** And what do you say, like, um, when it comes to like how your team is set up and how you actually work together, like how does it work there over at Delivery Hero for you?
> 
> 
> ### 00:04:45
> 
> **Andrei Petrovich:** You mean how we organize it in the teams? And it's, um, several frontend engineers, iOS, Android, um, several backend engineers. How much? I would say for frontend engineers, and the same about backend engineers, we are transforming our QA team. We had them, now we don't have. I don't know the future and what will be decided regarding the QA, but normally we had manual testers and automated testers. We have by nature, like, because we are aggregated sales, we collect data from multiple services. For example, we have about 20 integrations with other services like catalog, payment, etc., etc. And we need to communicate with them a lot. Our work is not isolated. Every change very often affects the cart because it's a part of our business, a part of a common functionality, I would say. If you want to add any new discount, even if it belongs to Simtech, I don't know, billing, you will go to us and we have to communicate how to propagate these values, how to calculate these values with our calculator, etc.
> 
> 
> ### 00:06:08
> 
> **Ryan Bolton-Smith:** Cool.
> 
> 
> ### 00:06:08
> 
> **Andrei Petrovich:** Awesome. That sounds great.
> 
> 
> ### 00:06:11
> 
> **Ryan Bolton-Smith:** And with regards to, by the way, like my, you know, the message that I sent over to you kind of like, you know, about NALA and, you know, the kind of the position, was there any questions of like You know, what is NALA, what is Rafiki, and like how they make money basically? Or like, is there any kind of like outstanding questions that I could help you out with?
> 
> 
> ### 00:06:26
> 
> **Andrei Petrovich:** Yeah, I tried to investigate a bit and let's check my understanding. Are they— are we on the same page? So mostly you are transferring the money. I— if I got it right, from Europe to Africa. Africa is, how to say, maybe focus of the company.
> 
> 
> ### 00:06:43
> 
> **Ryan Bolton-Smith:** Africa, Asia.
> 
> 
> ### 00:06:44
> 
> **Andrei Petrovich:** Yeah. Yeah, Africa, Asia. And you are trying to do it more reliable, cheaper, safer, faster. So you are trying to get income from fees and you also have some B2B product like API payment system. If I got it right, these are 2 things, 2 main sources of your income. Maybe I'm wrong, you please correct me.
> 
> 
> ### 00:07:10
> 
> **Ryan Bolton-Smith:** No, no, no, I mean, you hit it right on the head, so to speak. So yeah, NALA basically is our B2C model where, you know, downloads an app and move money from the US or Europe to Africa or Asia. And then basically about 3 years ago, we were getting fed up of having to deal with like the middlemen, you know, who connect us with the local payout providers in Africa and Asia. So then decided, well, we'll build our own, you know, direct integrations, our own kind of payment rails. And it's been a huge success for us because a lot of people don't bother to do it just because it's, well, you need a lot of connections. Like you need a lot of, you know, you need to be able to speak to the regulators, the banks, and All of these different people to get licensing approval across all the different. And obviously, Africa's about fifty. Is it fifty-three countries if I'm not mistaken? Sorry, total. I have to Google it now because I fifty-four. Damn. Sorry, I thought it was fifty-three. Sorry, fifty-four countries. So that's fifty-four regulators, fifty-four different banks. You know, there's a lot, a lot of different people that we have to speak to, and and that's why a lot of people don't do it. So we, yeah, we did that across the markets that we operate in, of which is approximately 14 to 15. It does change genuinely because some banks will call us up one day and say, hey, by the way, you know, we're shutting off you or, you know, and other competitors as well for whatever reason. But nowadays we facilitate B2B, like we've got MoneyGram that use us, obviously one of the biggest remittance providers in the world, TransferGo. Mama Money, DLocal, Mama Money, Cardano, like some gigantic companies already. And you might ask, well, how on earth do— why do they use you, right? They can't be bothered to build it. And so we've built— we've basically built something where our competitors to our NALA product, which obviously is the B2C one, we've got our competitors on the B2B side using us for their, obviously, their transfer, which obviously I think if anyone builds something where your editor is using you still, that's a fantastic product that you've built. This then allows us to then digress, or not digress, it then allows us to think about other things that we can then build upon that, right? I.e., local collections is quite an interesting product for us. So instead of having to always move money internationally where it goes through essentially like, you know, 15 different banks, 20 different clearinghouses, there's a load of net flows obviously you need to understand. If we can just digest the money in Nigeria and disperse it in Nigeria, of course, it's extremely cheap for us to do that. And therefore, equally, where there's dollar shortages across the continent, which is a very common thing as to why these businesses are so successful, this has allowed us to actually build a collection of products. So if I'm Uber, as an example, in Ghana, and I'm collecting money in local currency, I want to— normally I'd want to be able to move that money into USD or euro as fast as possible just because of currency fluctuations and volatility.
> 
> 
> ### 00:10:04
> 
> **Andrei Petrovich:** Okay.
> 
> 
> ### 00:10:05
> 
> **Ryan Bolton-Smith:** There isn't really a platform way of doing that unless you go through a broker who then speaks to another broker who then speaks to a disbursement order and so forth, so forth. Whereas actually you can just log into Rafiki now, say, hey, this is the amount of money that I'd like to deposit, I want it converted to whatever currency, and we simply facilitate it for you. So then there's loads of other things that we've built, but I won't go into depth into every single one for you, but global accounts are something that we've built already. So this means that you can download our app now and get paid in USD anywhere.
> 
> 
> ### 00:10:35
> 
> **Andrei Petrovich:** Mm-hmm.
> 
> 
> ### 00:10:35
> 
> **Ryan Bolton-Smith:** And we're also doing on the B2B side, we're doing stablecoins already now. So we're moving money into USDT and to allow both our B2B customers and us, you know, opportunity to actually make some money on arbitrage. And but also, obviously, allow quicker and faster payments because I don't think anyone could dispute that stablecoins isn't extremely quick. And then also we want to be able to introduce that on the B2C side of our business as well, because if we can imagine If we could imagine a really cool situation where there's a political event upcoming and, you know, that might devalue currencies in certain markets and you can just move your money to stablecoin, how great would that be? And that's what we want to be able to offer our customers. And so now if we go forward to right today, like what our plans are, we want to launch physical cards for our customers. We've already got global accounts.
> 
> 
> ### 00:11:20
> 
> **Andrei Petrovich:** Mm-hmm.
> 
> 
> ### 00:11:21
> 
> **Ryan Bolton-Smith:** And we've more recently been doing bilateral flows as well. So everyone, all of our competitors focus on sending money to Africa and to Asia. We're actually— we hear from our customers quite frequently. Like, we meet with them, you know, as many as we can every month or every 2 months nowadays. And they say, hey, like, I want to be able to send money from Kenya to the UK and to Europe to my friends, my family, and etc. So we've actually— we've allowed that. So Tanzania, Uganda, Kenya are live right now, and people can send money back and forth. And it actually increases our profit margin by a very surprising over 80%. And just allowing bilateral flows because again, no one else is doing it. It means that we get really good rates because if you now think about how this all this stitches together, we're doing local collections, we're getting really good rates because people have got wanting to get rid of local into USD. We're facilitating both of those. You can send money back and from, which allows us to get more favorable rates, which allows us to get with more brokers, more farmers, more exporters, more importers, and also it just grows and grows and grows. So that's our business at the moment.
> 
> 
> ### 00:12:25
> 
> **Andrei Petrovich:** Yeah, sounds great. So it looks like a neobanker for me. Yeah, like cryptocurrency opportunities. Yeah, I read about that you are trying to use the USDT as an infrastructure layer under the hood. But okay, now user will be able to directly buy USDT. Okay.
> 
> 
> ### 00:12:47
> 
> **Ryan Bolton-Smith:** Yeah, lots of cool stuff going on. Um, like I say, and you know, and you know, we're looking to hire into— like, we've got 4 squads here, by the way. We've got one called Squad T-Rex. Forgive me, they're not my names. We've got Squad T-Rex, Collections and Treasury, Squad B, and then we've also got the Payout and Compliance Squad. Um, so all these squads obviously all work on different things. On the Rafiki side, B2B, that's Payout and Compliance and Treasury and Collections.
> 
> 
> ### 00:13:11
> 
> **Andrei Petrovich:** Okay.
> 
> 
> ### 00:13:12
> 
> **Ryan Bolton-Smith:** And then Squad B and Squad T-Rex are on the NALA side, and basically they work on just everything to do with NALA. So they haven't got like a set focus, they just work on everything. And we work in the usual way, as you might guess. You know, we like our Scrum, we like our sprints. We are now moving more towards like a more matured setup in the sense of actually setting quarterly goals and like, you know, trying to stagger our goals to actually achieve those.
> 
> 
> ### 00:13:38
> 
> **Andrei Petrovich:** Mm-hmm.
> 
> 
> ### 00:13:38
> 
> **Ryan Bolton-Smith:** Before, it was just let's work on stuff and make it happen, which is fine. But, you know, as we grow, we need to be obviously a little bit more coordinated in how we think about things. And yeah, I mean, that's kind of it. I mean, hopefully you've seen the job ad, I hope.
> 
> 
> ### 00:13:53
> 
> **Andrei Petrovich:** Yes, it looks great. But I have a quick question.
> 
> 
> ### 00:13:59
> 
> **Ryan Bolton-Smith:** Yep.
> 
> 
> ### 00:13:59
> 
> **Andrei Petrovich:** What is— can you say that this company is heavily, I don't know, VC funded, or you have significant Cash flow and you earn enough to be independent? How does it work?
> 
> 
> ### 00:14:13
> 
> **Ryan Bolton-Smith:** Yeah, sure. I mean, like, to give you the numbers, so in 2024, in around June, they raised $40 million USD from VCs. Uh, that was Series A. Uh, they then did a debt funding round, and that was in December 2025. So, um, and that was for $50 million as well. And then as of right this second, We're getting ready to do our Series B, which I believe that we'll announce in the next couple of months. A big problem with these cross-border payment companies is that all their money gets locked up in float accounts, right, with our brokers. So when we raise that Series B at $40 million, approximately $30 million, approximately $30 million of that is just being given to brokers to lock out to get really good favorable rates.
> 
> 
> ### 00:14:57
> 
> **Andrei Petrovich:** Mm-hmm.
> 
> 
> ### 00:14:58
> 
> **Ryan Bolton-Smith:** So we actually haven't, actually really haven't spent that much money in the sense of like on staffing or offices or, you know, lavish benefits or anything like that because we don't have the money for that, right? We have to act quite lean. And then we did the debt facility at $50 million. Again, that allows us to get even better rates for our customers and therefore hopefully, you know, fattens up our profit margins. And but just to be abundantly clear, in March 2024, to prove that we could do it, we achieved profitability.
> 
> 
> ### 00:15:26
> 
> **Andrei Petrovich:** Hmm.
> 
> 
> ### 00:15:28
> 
> **Ryan Bolton-Smith:** So we did that before we raised our Series A and was like, cool, we know that we can do that. Let's go back to spending money on expansion. And so like I say, and we did the debt facility at $50 million in December 2025 simply because we can afford the interest payments on loans. We don't want to give up— we didn't want to at that moment in time, we didn't want to give up more dilution. And we'd rather come to the investors where we are right now today in a much more powerful position and therefore and be more aggressive in our negotiation with them as well. Because like I say, December was a great, a great quarter for us, but there was like a couple of bumps in the road that maybe wasn't as favorable for us. And we thought, well, we know that we can ride this out. And in February this year, and actually this quarter just gone, has been our best quarter since the business has launched ever. And February, for one reason or another, was our most profitable month ever. So we're very happy.
> 
> 
> ### 00:16:19
> 
> **Andrei Petrovich:** Thank you, thank you for the explanation.
> 
> 
> ### 00:16:23
> 
> **Ryan Bolton-Smith:** No problem.
> 
> 
> ### 00:16:24
> 
> **Andrei Petrovich:** Appreciate it.
> 
> 
> ### 00:16:24
> 
> **Ryan Bolton-Smith:** That's what I'm here for. So now that we've gone through all of that, what I'd like to do then is, in order for us to proceed on, I need to be able to ask you some technical questions that the team asked me to ask everyone to make sure that no one's wasting each other's time. And, and then assuming that they're all well, I can then progress on to the next stage where I'll give you some guidance as to what to expect. Okay.
> 
> 
> ### 00:16:45
> 
> **Andrei Petrovich:** Yeah, so we are doing right now this technical questionnaire?
> 
> 
> ### 00:16:50
> 
> **Ryan Bolton-Smith:** Yeah, yeah, like I said, they're just scenario-based, none of them are super in-depth. Obviously, I'm just a recruiter.
> 
> 
> ### 00:16:55
> 
> **Andrei Petrovich:** Yeah, yeah, okay, let's do whatever you want.
> 
> 
> ### 00:16:58
> 
> **Ryan Bolton-Smith:** Cool, all righty. Well, first and foremost, if a user's on a slow connection and they're clicking repeatedly on their send money button, like 3 times in a second, how do you make sure that that money is actually only sent once?
> 
> 
> ### 00:17:17
> 
> **Andrei Petrovich:** We are talking about the application, let's say mobile application. Yeah, you can, first you have, if you're talking about money, you have—
> 
> 
> ### 00:17:28
> 
> **Ryan Bolton-Smith:** Well, it could be anything. Let's say I'm on Delivery Hero and I click order now 5 times on kebabs.
> 
> 
> ### 00:17:34
> 
> **Andrei Petrovich:** It's a different thing because if you want to transact the money, it should be, how to say, transactional. And on the backend level, you have a guard. You can cannot put it twice. But apart from that, you can implement something on client side. Let's say put it in a queue. And because client knows that the user tries to attempt several times, use the same action. So you have— you can also, let's say, make a protection on the client level as well. But everything that is related to money is impossible, I would say, to make twice because of the strictest transaction level usually belongs to the money sphere. You can add something to the bucket, it's just calculation. It's not a big deal if you visit duplication, but double spending is impossible.
> 
> 
> ### 00:18:32
> 
> **Ryan Bolton-Smith:** But do you know exactly what the approach is taken though to prevent the double spending? I think I know that you said that you can implement something on the client side, but what I want to know is what is that something?
> 
> 
> ### 00:18:45
> 
> **Andrei Petrovich:** You mean, wait, on client or backend? On the client side, you just can't avoid— you can avoid to try to send multiple requests, but in any case, on the backend side, you cannot trust that the client will avoid it because I can be a proud user, I can create my own client, you know, program that will send repetitive queries and requests. So it's the final guard will be implemented on a database level and backend. And you cannot do it in memory because you have distributed system.
> 
> 
> ### 00:19:24
> 
> **Ryan Bolton-Smith:** So like I've got 2 approaches that I got given, which is idempotency.
> 
> 
> ### 00:19:29
> 
> **Andrei Petrovich:** Yeah.
> 
> 
> ### 00:19:31
> 
> **Ryan Bolton-Smith:** Or looking at maybe Redis or ETCD with distributed locking.
> 
> 
> ### 00:19:37
> 
> **Andrei Petrovich:** Distributed.
> 
> 
> ### 00:19:39
> 
> **Ryan Bolton-Smith:** Regarding, you're talking about distributed transactions or distributed locking for, for like to prevent double spending.
> 
> 
> ### 00:19:49
> 
> **Andrei Petrovich:** Okay. So to me, it sounds complicated. I see it just maybe I didn't work with money directly.
> 
> 
> ### 00:19:58
> 
> **Ryan Bolton-Smith:** No, no, of course.
> 
> 
> ### 00:19:59
> 
> **Andrei Petrovich:** Yeah.
> 
> 
> ### 00:19:59
> 
> **Ryan Bolton-Smith:** Yeah.
> 
> 
> ### 00:20:00
> 
> **Andrei Petrovich:** But I imagine it's as a layer on how to implement it on transaction layer in database.
> 
> 
> ### 00:20:08
> 
> **Ryan Bolton-Smith:** Got it. And next up is a scenario of like how you'd work with a product team. So now at NALA Rafiki, you know, as I'm sure you could guess, you know, we deal with millions of transactions. And if the product team were to say to you, hey, you know, Andrei, I'd like you to build us a report that can check how many unique users have transacted in the last 7 days. How would you design such an implementation?
> 
> 
> ### 00:20:37
> 
> **Andrei Petrovich:** Once again, you have a lot of— how many transactions do you have per week, per day?
> 
> 
> ### 00:20:43
> 
> **Ryan Bolton-Smith:** Millions a day.
> 
> 
> ### 00:20:44
> 
> **Andrei Petrovich:** Millions. And you need to build a statistic tool, yeah?
> 
> 
> ### 00:20:51
> 
> **Ryan Bolton-Smith:** All we want to know is that all they— all the product team in this scenario want to know is How many unique users have transacted in the last 7 days?
> 
> 
> ### 00:20:59
> 
> **Andrei Petrovich:** Why you cannot just try to build some worker that will— you probably don't need it, how to say, very accurate in real time. And the worker will try to aggregate data for some period of time and store it so dashboard could consume it. So it's repetitive work in background with no Real-time, 100% accuracy, but enough for statistics.
> 
> 
> ### 00:21:28
> 
> **Ryan Bolton-Smith:** Okay, that's cool. That's fun. What about in the wonderful world of AI? Do you use AI at Delivery Hero?
> 
> 
> ### 00:21:36
> 
> **Andrei Petrovich:** Yeah, yeah, it's everywhere. Everyone's using AI. Yeah, just not just use AI, we incorporate it in our— How do you like to work with it? I cannot even say the opinion because everything is transforming super fast. What was relevant 2 months ago is not relevant. I will say we have several providers. We could use different models from different vendors. We have our in-house built tool to create a feature from scratch. You just create a Jira ticket. and assign it to our bot. It will create a pull request, maybe in several repositories, you just will review it, etc. Of course, I think it's too many cases. And I personally, of course, use AI every day. And, you know, it was the interview with Baris Çökmek from Anthropic. He said that they don't write any code by hand anymore. Uh, it was several months ago, and that time, back in that time, it was like, uh, looked like an exaggeration, maybe because he built this tool. But now, surprisingly, I found myself and my team, I think we do not write also our code anymore by hand. Maybe in very occasional cases, uh, But yeah, cool. No one knows the consequences, and I don't know, yeah, what will happen in, in several months.
> 
> 
> ### 00:23:19
> 
> **Ryan Bolton-Smith:** Do you use it a lot in like, um, like I speak to some people and they say to me, well, Ryan, like sometimes I use for the coding, like the basic stuff, I kind of treat it like a junior, but I use it a lot for like, you know, fleshing out, you know, requesting for like RFCs, ARDs, and stuff like that. Do you use it a lot in like the design phase?
> 
> 
> ### 00:23:38
> 
> **Andrei Petrovich:** For design phase, usually I cannot— I don't know if the people are trying to generate RFC, but many of them are trying and it does not look good because if you see the AI slot, it's very predictable wording and there are a lot of text, much, how to say, bigger than a human would generate. Personally, I do not write RFCs. I use RFC to summarize, to understand, to teach me, to explain the problem, to connect the things together. Writing, I can just reformulate words if I don't like, but usually you write it by yourself and only format Maybe this, yeah. Reading, for reading, AI is a super cool tool because if you have a lot of documents incoming flow, the only way to manage it, to utilize the AI. Yeah. Cool.
> 
> 
> ### 00:24:47
> 
> **Ryan Bolton-Smith:** What about when we think about how you like to approach testing? Like, is there a specific approach that you'd like to have, like, with testing in Go?
> 
> 
> ### 00:24:56
> 
> **Andrei Petrovich:** Testing, it's not a topic of— yeah, you're asking in general.
> 
> 
> ### 00:25:02
> 
> **Ryan Bolton-Smith:** Separate question now.
> 
> 
> ### 00:25:03
> 
> **Andrei Petrovich:** Yeah, nothing is, how to say, super specific here. Look, you have a big company, distributed system, you have tests on many levels, unit tests, then you have integration tests that are running on your local machine and in CI/CD pipeline and use it to mock all the services and Maybe real instances of database like DynamoDB, etc. Then you have contract testing. If one of our dependencies changes the API contract, we will see it. We use Pact framework for that. You have end-to-end integration test. QI, automated tester writes a scenario on stage environment and checks it with real, not mocked dependencies. Of course, you test it manually on staging, sometimes on production, unfortunately.
> 
> 
> ### 00:26:06
> 
> **Ryan Bolton-Smith:** Thank you, Andrei. And then finally, I've now just got some recruitment questions. What's your notice period of delivery here? I would guess it's 3 months.
> 
> 
> ### 00:26:17
> 
> **Andrei Petrovich:** Exactly, 3 months as usual.
> 
> 
> ### 00:26:19
> 
> **Ryan Bolton-Smith:** Yeah, sure. And then with regards to the right to work, geographically you're based in Switzerland, is that right?
> 
> 
> ### 00:26:27
> 
> **Andrei Petrovich:** Not exactly, in Germany, but very close to Switzerland.
> 
> 
> ### 00:26:30
> 
> **Ryan Bolton-Smith:** Oh, I see. Okay. So what's your— what passport have you got? What's your right to work in said country?
> 
> 
> ### 00:26:38
> 
> **Andrei Petrovich:** You are asking about my resident permit, a visa, etc. I don't need any relocation support. I have permanent residence in Germany. I don't have passport.
> 
> 
> ### 00:26:51
> 
> **Ryan Bolton-Smith:** Got you. Okay, cool. Perfect. Thank you. And In regards to salary, now before I ask you what you're looking for, I just want to make something quite clear from our side. And when we hire people outside of the UK where ultimately we don't have an entity, we put people on B2B. And these are indefinite contracts. We've got loads— we've got people in Germany, Greece, Italy, Portugal, you name it, we've got someone there. It just means that you have to pay your own tax basically, right? So you just send us a gross invoice.
> 
> 
> ### 00:27:20
> 
> **Andrei Petrovich:** Mm-hmm.
> 
> 
> ### 00:27:20
> 
> **Ryan Bolton-Smith:** We'll send you payment. We'll word the contract so you still get full benefits, you know, holidays, sick pay, etc., of course. Um, but it just means that you have to, well, either hire an accountant or ask Claude to build you an accountant. It's up to you. I'm joking. Um, so does that agreement work with you?
> 
> 
> ### 00:27:40
> 
> **Andrei Petrovich:** So it's a usual B2B? Yes, no, uh, employer of record.
> 
> 
> ### 00:27:45
> 
> **Ryan Bolton-Smith:** Correct.
> 
> 
> ### 00:27:46
> 
> **Andrei Petrovich:** Um, I don't know how does it work in terms of infinite contract because usually all B2B contracts they have restricted timeline.
> 
> 
> ### 00:27:58
> 
> **Ryan Bolton-Smith:** We define our contract as indefinite.
> 
> 
> ### 00:28:02
> 
> **Andrei Petrovich:** I'm not sure.
> 
> 
> ### 00:28:04
> 
> **Ryan Bolton-Smith:** We could confine to whatever local tax laws you have and we could word the contract in such a way that you'd be happy with it.
> 
> 
> ### 00:28:14
> 
> **Andrei Petrovich:** Okay, you mentioned you have these holidays. Okay, in terms of B2B, it is €140 gross.
> 
> 
> ### 00:28:26
> 
> **Ryan Bolton-Smith:** Okay, like I said, look, we can go through the specifics and I can even get you to speak to my colleagues that I've got across, you know, Amsterdam, Germany, and Portugal as well. They can help provide advice for you if you need it. And obviously we'd always advise people to get their own independent tax advice anyway, for obvious reasons, of course. Wonderful. Andrei, have you got any questions for me that I can help you with?
> 
> 
> ### 00:28:51
> 
> **Andrei Petrovich:** I did not understand clearly to which team you are trying to hire, or you want to, how to say, fill in all 4 teams you mentioned.
> 
> 
> ### 00:29:02
> 
> **Ryan Bolton-Smith:** Yeah, we've got options on all 4, to be honest with you. They're high priority as of like today, like assuming that this other person I'm interviewing doesn't get a role. We're looking to hire specifically, ideally in the collections and treasury team. But if that role gets filled by the end of this week, which hopefully it will do, then we've got more of our opportunities on the NALA side as well. So like I say, both sides as of this moment.
> 
> 
> ### 00:29:24
> 
> **Andrei Petrovich:** Cool. Quick question, how does your hiring process look like?
> 
> 
> ### 00:29:29
> 
> **Ryan Bolton-Smith:** So the process is 3 3 stages in total. So there's a technical stage next, which is a pair program exercise that we do with everyone. Don't worry, it's not a— it's not a like a crappy thing that we've made up. Like, it's a real thing of how we set limits for our users. Um, it's not like a— what are those things called? Uh, I can't remember what they're called now.
> 
> 
> ### 00:29:53
> 
> **Andrei Petrovich:** I don't know.
> 
> 
> ### 00:29:53
> 
> **Ryan Bolton-Smith:** LeetCode. It's not like LeetCode.
> 
> 
> ### 00:29:55
> 
> **Andrei Petrovich:** It's not—
> 
> 
> ### 00:29:55
> 
> **Ryan Bolton-Smith:** okay, yeah, we're going to send you a zip folder that contains everything you need to know. And it's to do with how we set limits for our users across all the many countries that we operate in. So I'll ask you to solve that. Like I said, just share your screen with us. We don't like— just use your own setup. We're not going to ask you to use a crappy interviewer IDE. Just do what you want to do. Use AI, like whatever. Like, we don't really care too much. We just want to see, can you actually solve the problem? And it's meant— it's designed to be a simple problem. There are 5 limits to solve. And so that's stage 1. Stage 2 is then a very general kind of architecture to see like if you actually can flesh out architectural problems, and then the team are going to give you blockades to see if you can overcome them. And number 3, you then have a chat with Marcus, our head of engineering, for like 20-30 minutes. And yeah, that's it. That's the process. Cool.
> 
> 
> ### 00:30:44
> 
> **Andrei Petrovich:** Thank you.
> 
> 
> ### 00:30:45
> 
> **Ryan Bolton-Smith:** It's designed to be quite, you know, quite slick. We normally can get it finished in under 10 days.
> 
> 
> ### 00:30:51
> 
> **Andrei Petrovich:** Okay, got it. Thank you.
> 
> 
> ### 00:30:53
> 
> **Ryan Bolton-Smith:** Cool. All right, well, look, have a great day. I'll see you soon.
> 
> 
> ### 00:30:55
> 
> **Andrei Petrovich:** See you. Bye. Bye.
