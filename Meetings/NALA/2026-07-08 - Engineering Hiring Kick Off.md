---
date: 2026-07-08
type: hiring-kickoff
attendees:
  - "[[Oli Woolf]]"
  - "[[Christos Petropoulos]]"
  - "[[Edoardo Foco]]"
project: "[[Hiring]]"
duration: 35m
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/462982381"
tags: [meeting, hiring, engineering]
---

# 2026-07-08 - Engineering Hiring Kick Off

> [!summary] TL;DR
> Oli ran his first hiring kick-off with Christos (Squad B) and Edoardo (Squad T-Rex) to define the ideal candidate profile for senior backend engineers. Non-negotiables agreed: Golang, scalable systems experience, ownership mindset, product awareness, strong English communication, and message broker (Kafka) experience. Both squads are all-male, both EMs are open to remote-across-Europe hiring (+/-2hrs London), and both care only about talent quality regardless of gender or nationality. Oli will write up the ICP and share by end of week, with a platform kick-off tomorrow.

## Decisions

- **Decision:** Non-negotiables for senior backend engineers defined as 6 criteria: Golang, scalable systems, ownership, product awareness, strong English, message broker experience
  - *Rationale:* EMs want to filter at screening stage so pair programming interviews only see genuinely senior candidates
  - *Source:* "Golang, has worked on scalable systems, ownership and product awareness"

- **Decision:** Hiring only at senior level for backend, no mid or junior
  - *Rationale:* Team needs people who can ship big features autonomously with minimal ramp-up
  - *Source:* "They have to be senior. Like, there's no other level apart from senior"

- **Decision:** Geography open to all of Europe (+/-2hrs London) pending confirmation from Owen
  - *Rationale:* Talent pool in London-only is too small; both EMs don't care about location as long as talent is strong
  - *Source:* "anywhere in Europe, as long as the person is very talented"

## Action items

- [ ] [[Oli Woolf]] - Write up ICP document from this session and share with Christos + Edoardo (due: 2026-07-11)
- [ ] [[Oli Woolf]] - Run platform hiring kick-off tomorrow morning with same format
- [ ] [[Oli Woolf]] - Sync with [[Me]] on EU remote hiring policy confirmation

## Open questions

- What is NALA's official position on EU remote hiring? Christos said to check with Owen. Need to confirm the +/-2hrs London rule and whether Deel/contractor setups are available.
- In-person cadence for remote engineers: no fixed schedule, roughly every 6 months for whole-team, ad hoc when EMs visit London. November Go conference in Italy may be a team event.
- Would a female PM be available to join interview panels for female engineering candidates? Edoardo suggested it's possible but both EMs pushed back on gender being a factor at all.

## Key discussion points

### Squad structure and ways of working

Both squads run identically: daily standups, 2-week sprints, fortnightly retros, planning at sprint start, grooming mid-sprint. 20% of sprint time allocated to tech debt (Christos does 20% per sprint, Edoardo batches it). Development lifecycle: Product PRD > Engineering RFC > Jira stories > Sprint > Release. T-Rex has 6 people (3 senior backend, 1 mobile, 1 PM + Edoardo). Squad B has 7 (2 senior backend, 2 senior mobile, 1 shared designer, 1 shared QA lead + Christos).

> [!quote]- Source
> "Daily standups, we do have them. 2-week sprints, fortnightly retrospectives on the sprint, planning at the beginning of the sprint and groomings in between."

### Tech stack

Backend is exclusively Go. Database is Postgres. Event bus is Kafka (critical, non-negotiable experience area). AWS infrastructure (ECS, RDS). Monitoring: Prometheus + Grafana for metrics, Datadog for logs, Incident.io for incidents. Amplitude for product analytics. Engineers expected to handle small Terraform changes but are not infra-focused. IaC is secondary.

> [!quote]- Source
> "We use Go on the backend everywhere. There's nothing else apart from Go. We use Postgres as a database. We use Kafka as an event bus."

### Product awareness vs product engineer

Critical distinction: they want engineers who are product-aware, not product engineers. The difference is they need technically excellent engineers who think about edge cases, challenge PRDs, and understand user impact, not people who blur the line between product and engineering.

> [!quote]- Source
> "We don't need a product engineer, we need really good engineers that are product aware... We need really good technical engineers that care for what products they're building."

### Ownership and English proficiency

Ownership means seeing features through post-ship: monitoring, business impact assessment, documentation for others. English proficiency is a non-negotiable because engineers present at demos, write architectural docs, and interact directly with product. Past hires who were great engineers but poor English communicators had to be let go.

> [!quote]- Source
> "the usage of the language needs to be very good... we had to consider people going away because we couldn't understand them"

### Diversity and inclusion posture

Both squads are currently all-male. Both EMs are emphatically gender-blind in hiring. Christos's position is that if a candidate over-indexes on gender as a factor, that itself is an amber flag in their culture which is intentionally "politics-free, religion-free, gender-free."

> [!quote]- Source
> "We do not care. As long as they're good engineers, nothing else matters."

## Candidate Knowledge notes

*Atomic insights worth promoting to `/Knowledge/`. Flag here; promote during weekly review.*

- [ ] **"Product-aware engineers outperform product engineers in scaling fintech teams"** -- Christos's distinction between needing technical depth with product awareness vs hiring for product engineering as a discipline. Surfaced in engineering ICP discussion.
- [ ] **"English communication proficiency is a non-negotiable for remote engineering teams even when native fluency is not required"** -- NALA lost engineers who were technically strong but couldn't communicate clearly. Not accent, but structural language use.

## Values alignment

| Value | Signal | Evidence |
|-------|--------|----------|
| Customers First | Positive (Oli) | Structured ICP process to improve candidate experience by reducing wasted pair programming interviews |
| Play to Win | Positive (Christos) | "We technically don't need code monkeys. We have AI for that." -- raising the bar |
| Speed Wins | Positive (Oli) | Running kick-offs within first week, platform session already booked for tomorrow |
| Understand Why | Positive (Christos) | Articulated the why behind every non-negotiable with concrete examples |

## Propagation

*Proposed updates to other notes. Apply after review.*

### [[Oli Woolf]]

- [2026-07-08, [[2026-07-08 - Engineering Hiring Kick Off]]] Ran first engineering ICP kick-off with Christos and Edoardo. Structured approach: recorded session, built non-negotiables matrix, asked about diversity, geography, and team dynamics. Writing up ICP by EOW.

### [[Christos Petropoulos]]

- [2026-07-08, [[2026-07-08 - Engineering Hiring Kick Off]]] Squad B: 2 senior backend, 2 senior mobile, 1 shared designer, 1 shared QA lead. Non-negotiables: Golang, scalable systems, ownership, product awareness, strong English, Kafka. "We technically don't need code monkeys. We have AI for that."
- [2026-07-08, [[2026-07-08 - Engineering Hiring Kick Off]]] EYS Values: Pushed for English proficiency as hard filter based on past hiring mistakes -- *Understand Why*

### [[Edoardo Foco]]

- [2026-07-08, [[2026-07-08 - Engineering Hiring Kick Off]]] Squad T-Rex: 3 senior backend, 1 mobile, 1 PM. Top 4 non-negotiables: Golang, scalable systems, ownership, product awareness. "The job doesn't end when you ship the feature."
- [2026-07-08, [[2026-07-08 - Engineering Hiring Kick Off]]] EYS Values: "I like to hire everywhere. I don't care where the candidate comes from as long as he can deliver and ship." -- *Play to Win*

## Raw transcript

> [!note]- Expand transcript
> **Oli Woolf:** Hey, Chris, how are you?
>
> **Christos Petropoulos:** Good, man. How are you?
>
> **Oli Woolf:** Good, good, thank you. How's your, uh, week been so far? I know we spoke back end of last week. Get up to anything fun at the weekend?
>
> **Christos Petropoulos:** Uh, went to a basketball game, uh, FIBA qualifiers for the World Championship, or started there, but the game was pretty bad.
>
> **Oli Woolf:** Oh, really?
>
> **Christos Petropoulos:** Yeah, yeah.
>
> **Oli Woolf:** Yeah, who was it? Greece playing someone else?
>
> **Christos Petropoulos:** Greece with Portugal, uh, but we, we didn't have even half of the players there for some reason, you know, because the national teams, you have to call them and they have to accept to get to a game, right? For some reason they didn't call them, so the biggest players, they were not there.
>
> **Oli Woolf:** So like Giannis or whatever wasn't there?
>
> **Christos Petropoulos:** Yeah, he wasn't there.
>
> **Oli Woolf:** Weird.
>
> **Christos Petropoulos:** I think they underestimated Portugal, and we lost, of course.
>
> **Edoardo Foco:** Yeah, yeah.
>
> **Oli Woolf:** I'm just looking at it now.
>
> **Edoardo Foco:** Oh, interesting.
>
> **Oli Woolf:** Fine. Let's wait for Edoardo to join, but I'll tell him the same thing. I guess we've had an introduction now. Ah, perfect. Thank you. Hey, Edoardo. How you doing?
>
> **Edoardo Foco:** Good, thanks. Good.
>
> **Oli Woolf:** Yeah, good, good. Thank you. Um, I'm conscious of time and obviously we lost 5 minutes for the, uh, the demo day running over a little bit, so, um, keen to kind of jump straight into it. For me, the purpose of this session is to just have a conversation with you both that I can record and extract information from at the end about, in your mind, what does specifically a good backend engineer at NALA look like, right? And I have, um, a line of questioning that I'll talk to you both about to understand not just technically what that looks like, but, um, you know, culturally and how they'd be positioned and what their career maybe looks like, um, so that we can generate kind of-- I call it an ICP, right? An ideal candidate profile. that I can then go away and start building up, um, funnels for you, right? I know you've mentioned that you have 1 to 4 headcount available at the moment, but I'm hoping we're on the same page here where even if you had zero headcount available but I found you someone exceptional, we would find a place for them, right? So my aim from-- or the outcome I'm hoping for from this conversation is to understand what that exceptional candidate looks like and then always be on the lookout for that person. Be sending emails every week, be doing new searches every week, be doing new screenings every week, so we're always keeping a tab on the market. All right, I do have, um, some slash most of this information from, uh, Ryan and from, uh, information on Notion, but for, um, my own sanity, and please do forgive me, there may be some things that I ask you that appear obvious I just want to make sure that I'm hearing it from you guys rather than hearing it through a third party, and so that we're all on the same page.
>
> **Christos Petropoulos:** Okay.
>
> **Oli Woolf:** Any questions about any of that? Great. Perfect.
>
> **Edoardo Foco:** I appreciate it.
>
> **Oli Woolf:** So let's, let's kind of get into it then. Both of you run, run your squads, right? And the first thing I'm keen to understand from an engineering point of view Um, is who the important stakeholders for any new engineers are going to be. Okay, so, um, obviously both of you, and, and for the, for the, uh, note-taker's sake, I'll, I'll refer to you by full name and, and title so that we can capture it. But, um, so Edoardo Foco, you are an engineering manager, correct?
>
> **Edoardo Foco:** Yes.
>
> **Oli Woolf:** Um, which squad is it that you look after?
>
> **Edoardo Foco:** Squad T-Rex.
>
> **Oli Woolf:** Squad T-Rex, great. And you're important to engineering because you, uh, on a, on a day-to-day basis, um, uh, like assign kind of tasks and projects to that squad? Or can you tell me a little bit about, um, you know, how you-- your relationship with that squad?
>
> **Edoardo Foco:** Yeah, that's a good question. Um, the truth is we wear many hats. We are, first of all, the bridge between product and engineering. What we do is we collaborate with product to refine their PRDs, which are the product requests, understand where the gaps are, and then finally move it to engineering where-- and sorry, so then the engineers start actually going deep into the assignment, into the product feature that the product wants to ship. And our role there is to make sure that we divide and conquer the feature into tasks, and then the tasks are fully, you know, documented and are ready to go into the development phase. On top of that, we make sure obviously that the products get shipped in a timely manner and that all the guardrails are in place, the monitoring, and so on and so forth.
>
> **Oli Woolf:** Great, perfect. Thanks for the overview, I appreciate it. So likewise, same question, Question for you, um, Christos. So Christos, uh, Petropoulos, um, engineering manager, uh, you're responsible for, uh, Squad B, is that correct?
>
> **Edoardo Foco:** Yes.
>
> **Oli Woolf:** Great.
>
> **Christos Petropoulos:** Yes.
>
> **Oli Woolf:** Um, you know, tell me a little bit about your role within Squad B then and what you're-- how you kind of run that squad and what you're responsible for.
>
> **Christos Petropoulos:** I think it's pretty similar to what Edoardo mentioned. Um, We are the bridge between product and engineering. We're usually the people that provide context because apart from expertise, we also have a lot of tenure. So there's lots of divided context across that we just happen to have. It has to do with the breakdown, as Edoardo said. It's also related to us being responsible for the quality of the delivery in terms of how engineering scales. how we build things in a way that they can last. We're also potentially the key deciding factors on trajectory changes in terms of, we don't have enough time, we need to build something, it cannot be perfect, how do we do it? We usually come in to make the last decision, I think. And we've also done hiring for our squads. I mean, most of the people that exist now, I think we have interviewed them. Yeah, product engineering, and I think there are other spillovers into other departments because of the context we have, but these are the main things, I think.
>
> **Oli Woolf:** Great, perfect. Thank you for the overview. In terms of other key stakeholders in this space, I think an obvious one would be Markus Seebacher, right, who, um, is the head of engineering and ultimately both of you two report into. Have I got that correct?
>
> **Edoardo Foco:** Yeah.
>
> **Christos Petropoulos:** Yes.
>
> **Oli Woolf:** So between you three, or other than you three, um, you know, from an interviewing perspective, uh, you know, just from a stakeholder perspective, is there anyone else within NALA, and maybe one of the product managers or something, that is going to be important for, as a stakeholder, for these engineers once they are in In situ, or is it ultimately you 3 are the key players here?
>
> **Edoardo Foco:** We're definitely the key players, I'd say. However, an engineer that comes into NALA is expected to actually deal-- I mean, have conversation with the product as well as the stakeholders for the feature that he's developing.
>
> **Christos Petropoulos:** Right.
>
> **Edoardo Foco:** Okay. And ultimately, as I mentioned last time, we're kind of like looking For a product-oriented engineer that is able to understand the product itself, not just ship code.
>
> **Oli Woolf:** Yep.
>
> **Edoardo Foco:** Okay.
>
> **Christos Petropoulos:** I think there's a small clarification to do on what you just said. We don't need a product engineer, we need really good engineers that are product aware, if that makes sense.
>
> **Oli Woolf:** Sure.
>
> **Christos Petropoulos:** Because I think lately, based on the industry, that might be slightly different.
>
> **Oli Woolf:** Uh-huh.
>
> **Christos Petropoulos:** We need really good technical engineers that care for what products they're building And they look behind just the code that they need to write. If you want to translate what Edoardo said, but yeah.
>
> **Oli Woolf:** Makes, makes sense. Makes perfect sense. So in terms of one of my lines of questioning here, which we can jump to, is, you know, who will they be working with and why? So directly that's going to be engineering and product. Again, for note-taker purposes, Edoardo, how big is Squad T-Rex from a headcount? perspective, and likewise, Christos, same for Squad B.
>
> **Edoardo Foco:** So we have 3 senior engineers backend, 1 mobile, and 1 product manager.
>
> **Oli Woolf:** Right, so 5 in T-Rex plus you, Edoardo, 6?
>
> **Edoardo Foco:** Yep.
>
> **Oli Woolf:** Yep, and Chris, for Squad B?
>
> **Christos Petropoulos:** I have 2 senior backend engineers, 2 senior mobile engineers, Uh, one designer which is shared kind of between us, and also a lead QA who is the only QA, and he's also shared. I just happen to manage them.
>
> **Oli Woolf:** Sure. So 6 for Squad B plus you then, Chris? Yes.
>
> **Edoardo Foco:** Great. Yes.
>
> **Oli Woolf:** Amazing. They'll work very closely with product, we've mentioned. Are there other teams within NALA that they might be exposed to indirectly, which is, is, is good to be aware of?
>
> **Christos Petropoulos:** I mean, to some extent, if we keep building wallets, finance might be one of the places because we're defining ledgers and, you know, how money moves. But theoretically compliance too, because of what we're building.
>
> **Edoardo Foco:** Sure.
>
> **Christos Petropoulos:** But indirectly, right, through product, it should be. Sure.
>
> **Oli Woolf:** Yeah, understood. Okay. And in terms of how you set up your teams and your ways of working, Maybe you follow similar structures and cadence, maybe you kind of run them slightly differently. If you could talk to me a little bit about that. Do you follow agile principles? Do you run daily stand-ups? Do you run fortnightly sprints? Tell me again, just high level, but help me understand the sort of cadence you both work at with your squads.
>
> **Christos Petropoulos:** I think I can speak for both. We have pretty much the same things. Very, very slightly different. So daily standups, we do have them. 2-week sprints, um, um, 4 nightly retrospectives on the sprint, uh, planning at the beginning of the sprint and groomings in between. On my side, it's usually once per week, but if there's more need, it's more than once a week depending on the, on the needs of product to refine things to work on. Aside from that, there's a-- this is where our difference is. We have agreed to spend 20% of the sprint time on improving our tech, which is tech debt and anything related to that. I prefer to do it 20% per sprint. Edoardo might not give the 20% per sprint, but have like a sprint that it's mostly that, for example, later on in the quarter. Edo, is there anything else?
>
> **Edoardo Foco:** No, I think that's it. I'm not sure if you're also interested in knowing the, like, the full development lifecycle. So yeah, so everything again starts from product when they define, well, the, the objectives, the initiatives that we have to take on this on a quarter basis. From that, from those initiatives, typically 2, 3, maybe 4 per quarter, then we go, then they go and create a document which is called TRD. Document is created, goes to engineering. Engineering creates an RFC, which is a technical requirements document. From the RFC, we then split it out and we create stories and tasks on Jira. Once everything is estimated, we, together with product, we slot it in the roadmap, and then the normal development flow kicks in with the sprints and Yeah, releases.
>
> **Oli Woolf:** Okay, perfect. Thanks for, for, for talking me through that. You talked a lot about, or you've spoken about tech debt and, um, uh, how you allocate 20% of your, or 20%, whether it's per sprint or of your quarter to solving tech debt. Talking about the technology stack as a whole, um, Obviously, I'm aware that the backend is primarily written in Go. Um, I say primarily, uh, just because I don't know, are there any other languages that your, uh, kind of backend code is written in, or is everything written in Go? I guess broader question, can you tell me a little bit about the technical environment? So, uh, infrastructure components that you use, um, You know, anything, right, that from a technology point of view that's going to go into a good engineer stack that's going to be suited to NALA?
>
> **Edoardo Foco:** Sorry, so technology stack, yeah, we use Go on the backend everywhere. There's nothing else apart from Go. We use Postgres as a database. We use Kafka as an event bus, let's call it that way. What else? We use AWS as infrastructure provider. Sure. And that's pretty much it, just because I'm not sure within AWS.
>
> **Oli Woolf:** Sorry, Chris, I was going to say within AWS, um, are there any particular components, um, like Aurora for example, um, EKS? Like, is there anything within AWS that you're particularly reliant on that would help Or, you know, when I am searching and kind of screening applicants, that question also applies not just for AWS but for, uh, you know, IaC, um, and, and, uh, programming languages as well. Can there be flexibility with, um, Go? So I guess, yeah, back over to you to kind of talk me through in a little bit of detail.
>
> **Edoardo Foco:** Yeah, so typically backend engineers are not really Involved in infrastructure in that way, but we use like standard things, so standard components, so ECS for example, or RDS for the database. We, we do expect engineers at some point to work with, to be able to work with Terraform to deploy smallish AWS infrastructure changes, but those are typically like very small.
>
> **Christos Petropoulos:** Okay.
>
> **Edoardo Foco:** Sure, depends on the experience, to be fair. Like, if we find a strong-- a strong engineer would typically have some infrastructure knowledge.
>
> **Oli Woolf:** Yep, yep, great. We're obviously going to talk-- not to derail this, we've got this same meeting tomorrow morning to do this thing for platform as well, so we can get into that a little bit more. But yeah, okay, that's good to know. Chris, on the tech stack, um, anything you'd like to, uh, double down on, add? Maybe have a different perspective on?
>
> **Christos Petropoulos:** No, I can, I can add a few things. Because you mentioned components in AWS, I mean, DBs are RDS, if that makes any sense. For metrics, we use Prometheus and Grafana.
>
> **Oli Woolf:** Yep.
>
> **Christos Petropoulos:** Logs we have on Datadog. Alerts are Grafana and Datadog, and incidents are mainly handled through Incident.io.
>
> **Oli Woolf:** Okay.
>
> **Christos Petropoulos:** We have, not related to the backend, but in general, we have a lot of Amplitude data for how our app is operating, and there's lots of funnels on it. What else? Any other cross-cutting concern? I think that's it. That's what I wanted to add.
>
> **Oli Woolf:** Okay, awesome. I have a couple of final questions that's then really going to help me kind of focus down on these. I'll move away from the technical briefly and talk about kind of the geographies of where these people are based. Edoardo, I know you're in Italy. Chris, I know you're in Greece. I'm still relatively new to NALA and I'm getting a little bit mixed messaging about do we have to have people in London? Can we have people over Europe? So let's just kind of between the 3 of us, tell me your perspective on it. You know, I'm going to pick a random country, right? Say I find an exceptional Golang engineer in Moldova, right? Are you against hiring in that location? Edoardo, would you prefer your squad be based in Italy? Christos, would you prefer your squad be based in Greece? Do you not care as long as you're getting exceptional talent? Um, can you give me your perspective and how you understand kind of NALA's position on, on where I can be looking for these people?
>
> **Edoardo Foco:** I think it's 2 different positions though. There's our positions and NALA's, right? Um, my personal position is that I like to hire everywhere. Like, I don't care where the candidate comes from as long as he can deliver and ship. You could be working on a beach, I don't care.
>
> **Christos Petropoulos:** There is a limitation to that though, Edo. Yeah, historically at NALA we were hiring plus minus 2 hours from London to keep at least a similar day within ourselves. Like if someone is in the US, it's gonna be tough, right? Um, and standups, we have them a bit late to accommodate for that. But apart from this, I'm fully with you on our side. I don't care anywhere in Europe, anywhere, as long as the person is very talented and very good at their job. The rest is just simple as it is right now. But Oli, I think you should also sync with Owen, I think, on this.
>
> **Edoardo Foco:** Yeah.
>
> **Christos Petropoulos:** Because we got an update recently that because the talent pool is getting smaller on the London-specific area, we're now open to across Europe, right? But that's not something we can decide. This is our view, I think.
>
> **Oli Woolf:** I understand. And then from, um, a team perspective, uh, how often do you, uh, or maybe you don't, but intend to get the team together? Do you kind of fly the team into London or location, um, you know, quarterly for, um, a hackathon or a conference or just some team bonding and just to maybe at the back end of a, of a really important project? Hey team, the last week we're all going to be in London and get this over the line together. What's your cadence on in-person collaboration? Maybe there isn't, and that's fine, but just so I'm aware of what I'm selling and talking to prospective candidates about.
>
> **Edoardo Foco:** I could take this if you want, Christos.
>
> **Christos Petropoulos:** Yeah, sure. And I can add if needed.
>
> **Edoardo Foco:** Yeah. So first off, me and Christos, we typically come to London like once a month, max once every 2 months. And when we do, we generally try to bring the engineers, engineering teams together. This means if you live around London, we pay for the trip and the hotel for a couple of days. We have various occurrences of this. For engineers that work remotely, again, it depends. We, of course, we try, but we don't have like a regular cadence for organizing these things. Now, in November, there is a Go event in Italy, and I think we're going to try to get the backend engineering team together for that event.
>
> **Oli Woolf:** Great, perfect.
>
> **Christos Petropoulos:** Yeah, and if I can add, there's no actual cadence, but historically, or statistically to be precise, I think we're doing once every 6 months or once a year, like whole team gatherings. Now if someone is close and we go to the office, of course they come down, you know, we spend a couple of days. Um, and there's also the case where the company does offsites. Historically there have been some. Now we're funding, it's different. Um, but I've been to 2 big offsites, one in Kenya and one, one in Zanzibar. That's a good selling point if it's, you know, oh, you might get there or something, right? I mean, it doesn't mean that it's going to happen again, but historically it did, and there are tons of pictures on it. Um, but that's it. Otherwise, it's just, you know, a per case once we go to London, etc.
>
> **Oli Woolf:** Yeah, makes sense. Okay, perfect. Um, I'm conscious of time, so the last thing I really want to nail down on-- I'm going to share my screen just, just for some context. Right? So this is, this is my matrix that I use and I've, I've built. It's pretty, pretty simple. I'm not going to change the world here. But what I want to know really is, you know, between you, kind of your non-negotiables, okay, and how we are going to deploy these for what exceptional engineering talent at NALA looks like.
>
> **Christos Petropoulos:** Okay.
>
> **Oli Woolf:** I'll give you an example, right? Obviously, I know one of the non-negotiables is they must have Golang. How are they going to use that skill on a day-to-day basis? You know, building the backends. OK? What expectation level do we have? This is where I'll hand over to you. But it might be like, for example, comfortable with concurrency, for example, right?
>
> **Edoardo Foco:** Yeah.
>
> **Oli Woolf:** Can you, between you, for the last few minutes, kind of talk me through, um, and the note-taker will capture this, but talk me through what the non-negotiables are? So if I only find you candidates with these 3 or 4 or 5 or 6 things, um, anything else is a bonus, uh, but we'll talk to them. Can you, um, kind of share your, your thoughts and opinions in, in this style on, on what that looks like to help me go out and start curating?
>
> **Edoardo Foco:** I mean, I would-- so goal, I mean, is it just technologies or--
>
> **Oli Woolf:** Can be soft skills as well. This is the, in your opinion, the non-negotiables, right? That list can be pretty long. But when I'm searching, I then know if a candidate does not-- has to have all of these, uh, either from a search perspective or after I screen them, because my screening will be based on this. The things that are non-negotiable for you, I'll go into a level of detail where I can hopefully filter out the, the good talkers from the actual capable engineers.
>
> **Christos Petropoulos:** Yeah.
>
> **Oli Woolf:** So it's, it's the non-negotiables, right? I'm sure you've been in a pair programming interview, after 5 minutes you're like, Damn it, this, this candidate's not strong enough, right? Yeah. My job here is to actually try and avoid as much of that as possible by going into the right areas at an appropriate level of depth in the screening calls.
>
> **Edoardo Foco:** Yeah. So for me, top 4 that come to my mind right now, but then you can change them obviously, is Golang, um, has worked on scalable systems, Systems with many users, put it this way. Ownership and product awareness.
>
> **Oli Woolf:** Okay, so let's, let's work backwards from that. Product awareness, how are they going to use that skill? Well, I'm assuming, correct me if I'm wrong, that is just the relationship with product and seeing the bigger picture and how the product will kind of land with end users?
>
> **Edoardo Foco:** Chris?
>
> **Christos Petropoulos:** On this one, on product awareness, an example is PMs are going to get us product requirement documents. Then we sit down as a team and we try to tackle them. And the less PRD breaks, the more stable the implementation will be and the better the feature will be. So someone having the ability to think edge cases, how a user will perceive this, is this design that's brought in Irrelevant or it doesn't make sense, you know, stuff like that.
>
> **Edoardo Foco:** Yep.
>
> **Christos Petropoulos:** This can make our building more effective by helping product.
>
> **Oli Woolf:** Sure. So this is the, the expectation level we have of, of engineers from a product awareness skill, let's say.
>
> **Christos Petropoulos:** Yes, because we technically don't need code monkeys. Yep. We have AI for that.
>
> **Oli Woolf:** Sure. Makes sense. Let's talk through the other 3 things you mentioned there, Edoardo. I'm conscious of time. If you have a few more minutes, it'd be really helpful for me. me and we'll wrap this up. So Golang, we've spoken about, it's what you build the backend with. It's, it's the day-to-day, right? But what, um, what's the expectation level? I accept that our expectation level for leads is entirely different to juniors, but as a whole, what are we looking for? What level do we need people to be at with Golang, um, for us to be able to consider them?
>
> **Edoardo Foco:** They have to be senior. Like, there's no other level apart from senior.
>
> **Oli Woolf:** OK, and how do you, like, what do you classify as a senior in your eyes? Is it, you know, I'm just throwing buzzwords out. Is it they're comfortable with concurrency? Is it they are or they have experience doing this certain thing? Tell me what a senior is in your eyes, what the expectation is.
>
> **Edoardo Foco:** That's, I mean, you're opening kind of worms here. Like, we could just write essays about this.
>
> **Oli Woolf:** Sure.
>
> **Edoardo Foco:** So from a high-level perspective, someone who can ship a big feature with little issues. Okay. And then if you go later down, it's somewhere-- I mean, yeah, someone who can work autonomously, who can implement the best practices. This means various things from, you know, SOLID principles to testing.
>
> **Christos Petropoulos:** That's not Go-specific, right?
>
> **Edoardo Foco:** That's not Go-specific, no.
>
> **Christos Petropoulos:** It's a different thing, senior on software and senior in Go.
>
> **Edoardo Foco:** Sure.
>
> **Oli Woolf:** Yep.
>
> **Christos Petropoulos:** Right? In Go, they need to know how to use the language, but the rest is architecture, coding best practices, and everything, right?
>
> **Oli Woolf:** Basic software engineering principles then?
>
> **Christos Petropoulos:** Well, basic, more advanced, like all of them, you know. It's, it's very helpful.
>
> **Oli Woolf:** Yeah, sure. Okay.
>
> **Edoardo Foco:** Like, the point of hiring only Go is because we don't want to invest time on someone that has to learn another language, but the language is just a tool.
>
> **Oli Woolf:** Sure, I understand.
>
> **Edoardo Foco:** Yep.
>
> **Oli Woolf:** Remind me what the other, the last 2 or the first 2 things you mentioned.
>
> **Edoardo Foco:** Has worked on scalable systems. So I think that's important because he wouldn't know how to, what problems we'll face. He would already know the problems that we're facing.
>
> **Oli Woolf:** Sure. Okay. So how's--
>
> **Christos Petropoulos:** An example of that could be, don't make a PR and give us a query that's going to make everything slower. You need to know and you need to think how what you're adding is going to affect the big system, how it scales, how it might not scale in the future. And, you know, systems with, I don't know, 5,000 concurrent users at any moment and hundreds of thousands every month, It's not the same as building something that's addressing like 1,000 users, right?
>
> **Oli Woolf:** Sure, totally understand. Okay, and then the final point-- forgive me, Eduardo-- you mentioned was--
>
> **Edoardo Foco:** Final point, what's that? Sorry, ownership.
>
> **Oli Woolf:** Ownership, probably. Yeah, ownership.
>
> **Edoardo Foco:** As I said, I mean, the job doesn't end when Once you ship the feature, we want people to actually go and assess whether the feature is having a real business impact, if it's working as expected, if there are issues down the line, if the monitoring is set up correctly, if, I don't know, other people are able to, you know, work on the feature if there are issues. Right.
>
> **Oli Woolf:** Okay.
>
> **Christos Petropoulos:** There's another aspect on that. Which is related to how much they understand what they're building. Again, ownership is also against being a code monkey, right? So when we decide as a squad to build something, our expectations is that you're not just going to say yes to whatever requirements come in, you're going to evaluate them because you have the skill to do so, because you're going to own this as a feature that you build and you're proud for it.
>
> **Oli Woolf:** Cool. Okay, gents, thank you so much for your time. This has been a super useful session for me. I'm gonna kind of type up everything we've discussed, and I'm--
>
> **Christos Petropoulos:** I have 2 more to add, if you--
>
> **Oli Woolf:** Please, yeah, yeah, as long as-- I'm fine for time, I just don't want to keep you. I know, if you want to drop, sure.
>
> **Christos Petropoulos:** I just want to add 2 more things.
>
> **Oli Woolf:** Um, I'll, um, just while you're here, I will type this up and share it with both of you so that we're then all aligned, you know, by the end of this week. So yeah, Edoardo, if you do need to drop You'll get a-- I'm cool, guys, I'm cool.
>
> **Edoardo Foco:** I have 5 minutes.
>
> **Oli Woolf:** Oh, good stuff. Yeah, Chris, sorry.
>
> **Christos Petropoulos:** One that has been problematic in the past, especially if we hire across Europe, is the usage of the English language. We've had issues in the past where we had people that were great engineers, but because our engineers will speak with product, they might present on a demo, they might create architectural documents, the usage of the language needs to be very good. I'm not saying native, I'm not native for example, but we need people who are able to elaborate on what they're saying with ease and being able to raise arguments in a very proper way. So if someone has a weird accent, I don't care about the accent, it's about the usage of the language structurally, if that makes sense, because we had to consider people going away because we couldn't understand them.
>
> **Oli Woolf:** Sure.
>
> **Christos Petropoulos:** In the long distant past. And number 2, on the techs, if you add to the mix experience with message brokers, we heavily rely on Kafka, for example. It's a big part of the backend and how events are being driven in the system. So it's not that it's a needed thing, but if someone has never worked with messaging brokers in the past, I mean, It's lacking architectural concepts that one might not have to craft something that is complete in many ways, especially on scaled systems and on distributed stuff. That's it. That's the 2 things.
>
> **Oli Woolf:** Makes sense. Okay, perfect. Again, really useful context for me on this. The final thing, from a diversity perspective, Um, uh, are both of your squads all male? Is there a male-female split? Um, would you be open to-- yeah, Chris, can I reply to that, please?
>
> **Christos Petropoulos:** We do not care. As long as they're good engineers, nothing else matters.
>
> **Oli Woolf:** Great answer. That's what I was hoping to hear. Good. Okay. Um, but for-- I'm also conscious that if I do find you an exceptional female, for example, and they are the first, first female, that there could be, um, hesitancy is the wrong word, but they hopefully they won't, but they might feel intimidated stepping into, um, an environment. So is your current-- Right, I agree. But is your-- are your current squads all male at the moment, or do you have any females in there? You know, for example, if we get an engineering-- yeah.
>
> **Christos Petropoulos:** Currently, no. Historically, we did.
>
> **Oli Woolf:** Okay. I'm, I'm also thinking from an interviewing perspective, if we have an exceptional female, would there be a female interviewer that we could kind of insert into the process to get some form of familiarity and build that bond? You know, again, talking ahead of ourselves here, but good for me to know so that I can position certain things and orchestrate a process to, to try and get the best outcome depending on You know, the candidate that we're dealing with. Obviously, if I find an amazing Greek engineer, Christos, I'm going to be hitting you up. You can relate, right? Likewise, Italians, Edoardo. And let's play to our strengths here. Let's give ourselves a competitive advantage with what we already have.
>
> **Edoardo Foco:** So nowhere in engineering as an engineer, but we could try to arrange with the product, with the PM. Yeah, I know what stuff, but sure. Okay, the last stage with the PM, right?
>
> **Oli Woolf:** Yeah, okay.
>
> **Christos Petropoulos:** If that makes it any different. But you know, the-- if we don't see gender in this and someone who's gonna come in does, to me that's a problem.
>
> **Oli Woolf:** Yep, red flag.
>
> **Christos Petropoulos:** Because we're politics-free, we're religion-free, and we have everything, I can assure you. Uh, we're also gender-free. We don't really care. someone cares too much and this is a problem, to me, maybe not a red flag, but it's an amber flag because it's a distilled environment intentionally so that we can all respect each other and work in a nice way.
>
> **Oli Woolf:** Great.
>
> **Christos Petropoulos:** Just, just a note. That's what I wanted to answer on this one because I'm very sensitive. I don't tolerate, and I don't tolerate weird behaviors. So everyone needs to be equal. Everyone is the same. It doesn't matter what you are, where you're from, where you live and everything. That's all.
>
> **Oli Woolf:** Love it. Really good to know. Okay, chaps, thank you so much. Um, we'll do this all again for platform in the morning. Uh, so yeah, it will follow a similar style, so maybe it will get you thinking about kind of, um, what we can talk about tomorrow morning. I will then write up both, both conversations. I'll share that with you both, and then we're all aligned on, on what, what good looks like for engineering and for platform at NALA. And that then sets me on my way to go and find and screen these people so that by the time they hit you and your teams at pair programming, we filtered hopefully the majority of the unsuitable applicants and we're, we're saving you more time interviewing and getting you quicker turnarounds on, on good engineers. So I appreciate your time again, gents. I'm available on Slack if you need anything. Otherwise, enjoy your afternoons and we'll chat again tomorrow.
>
> **Edoardo Foco:** Thank you.
>
> **Oli Woolf:** Thank you so much. Bye.
