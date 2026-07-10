---
date: 2026-07-09
time: "08:30"
timezone: UTC
type: internal-meeting
attendees:
  - "[[Oli Woolf]]"
  - "[[Edoardo Foco]]"
  - "[[Christos Petropoulos]]"
topics:
  - Platform hiring kick-off
  - Backend engineering hiring doc review
duration: ~35 min
status: raw
source: metaview
source_url: "https://my.metaview.app/notes/462982464"
tags: [meeting, hiring, engineering, platform]
---

# 2026-07-09 - Platform Hiring Kick Off

> [!summary] TL;DR
> [[Oli Woolf]] ran a dual-track hiring kick-off: first a sense-check on the backend engineering hiring doc (non-negotiables, interview process coverage), then a full intake for the new Senior Platform Engineer role. Key outputs: 6 backend non-negotiables confirmed, architecture added as a screening signal, platform non-negotiables locked to AWS + Terraform at senior level, interview process for platform is talent screen -> 90-min architecture/Terraform task -> bar raiser with Markus.

## Decisions

- **Backend doc**: Architecture must be added as an explicit screening question alongside scalable systems. [[Christos Petropoulos]] flagged candidates may pass pair programming but fail architecture if this isn't surfaced early.
- **Platform interview process**: No pair programming stage. Flow is: Oli talent screen -> 90-min technical task (system design + live Terraform) -> bar raiser with [[Markus Seebacher]]. Two interviewers per architecture session (Edoardo, Christos, Ale, or Seb).
- **Platform non-negotiables**: AWS (strong preference, not GCP) + Terraform at senior/expert level. Networking, security best practices, and ability to shape infrastructure strategy are the underlying bar.
- **Location**: Remote, Europe +/- 2 hrs London. No hard London requirement. To be confirmed with Owen and Markus.
- **Reporting line**: Platform hire reports to [[Edoardo Foco]] initially.
- **Direct reports**: None expected in the near term; possible team growth if NALA scales significantly.
- **Ways of working**: Daily standup with Edoardo for first 1-2 months, then lighter cadence.

## Key discussion points

### Backend engineering doc review
- [[Oli Woolf]] shared a written document from the prior day's session as the source of truth for backend hiring.
- [[Christos Petropoulos]] identified a gap: "scalable systems" alone doesn't capture system design/architecture. Candidates may pass pair programming but hit the architecture wall. Oli committed to adding an architecture-specific line of questioning to the talent screen.
- 6 non-negotiable backend skills (exact list in the doc): Go, scalable systems, message broker experience (Kafka), architecture, product awareness, communications/ownership. Pair programming tests Go + scalable systems; architecture stage tests Kafka, system design, product awareness, and comms.

### Platform role context
- First standalone platform hire at NALA/Rafiki. Previously Seb and Nico (CTO) owned infrastructure; after EM transition, Edoardo, Christos, and Ale hold it by default alongside their core jobs.
- No pure platform engineer currently in-house. Risk: inability to handle major incidents or implement infrastructure best practices.
- Edoardo's framing: "Senior platform engineer who's hungry to become lead/staff level."
- Key stakeholders: [[Edoardo Foco]], [[Christos Petropoulos]], [[Markus Seebacher]], Petros Kirillist (Head of Security, SOC 2), Parth (Data) for data infrastructure overlap. Alessandro Colaneri is an engineering stakeholder but less central to platform.

### Platform roadmap (from Edoardo's Slack post, #hiring-infra-engineer, June 11)
- **0-3 months**: Understand the estate, map infrastructure, security baseline, build process for capturing infra requirements from teams, improve observability, identify AI opportunities.
- **3-6 months**: Optimise and automate, address scaling bottlenecks, backlog items, lay ground for AI-driven incident management.
- **6-9 months**: Simba project - move shared services to a separate AWS account.
- **Ongoing**: Atlantis (incomplete) - enables engineering self-service on infrastructure changes. Christos flagged this as high value for team autonomy.

### Platform tech stack
AWS (primary cloud), Terraform, ECS, RDS, Kafka (managed), CodePipeline, CodeDeploy, CodeBuild, TwinGate, Neo4j, HashiCorp Vault, IAM, AppSync, CloudWatch, Secrets Manager. Candidate must know these, not learn them.

### Interview process alignment
- [[Oli Woolf]] proposed an optional 15-30 min technical pre-screen before the 90-min architecture task to reduce wasted time on weak candidates. Both EMs acknowledged the risk of letting unsuitable candidates through to the 90-min stage.
- Edoardo accepted some early-stage iteration: "We're going to fuck up a few times and that's fine."
- Christos noted the 2-stage process (talent screen + 90-min task) is a competitive advantage to sell to candidates - lean and fast.

## Actions
- [ ] [[Oli Woolf]] to build Platform hiring doc (equivalent to backend doc) by Monday
- [ ] [[Edoardo Foco]] and [[Christos Petropoulos]] to review backend engineering doc within 48-72 hours and add comments
- [ ] Confirm platform location requirement with [[Me]] and [[Markus Seebacher]]
- [ ] [[Oli Woolf]] to review Edoardo's June 11 Slack post in #hiring-infra-engineer (30/60/90 day plan)

## Propagation

### [[Oli Woolf]]
- [2026-07-09, [[2026-07-09 - Platform Hiring Kick Off]]] Ran platform hiring intake with Edoardo and Christos. Building platform hiring doc by Monday. Added architecture to backend talent screen questioning.

### [[Edoardo Foco]]
- [2026-07-09, [[2026-07-09 - Platform Hiring Kick Off]]] Platform hire reports to him. Shared 30/60/90 roadmap in Slack June 11. AWS + Terraform are hard non-negotiables at senior level.

### [[Christos Petropoulos]]
- [2026-07-09, [[2026-07-09 - Platform Hiring Kick Off]]] Flagged architecture gap in backend screening. Advocated for Atlantis completion as self-service enabler. Key interviewer for architecture stage.

### [[Hiring]]
- [2026-07-09, [[2026-07-09 - Platform Hiring Kick Off]]] Platform Engineer kick-off complete. Role is NALA's first standalone infra hire. Process: talent screen -> 90-min architecture/Terraform -> bar raiser (Markus). Non-negotiables: AWS + Terraform at senior level.

## Raw transcript

> [!note]- Expand transcript
> ## Platform Hiring Kick Off - Transcript
> 
> ### 00:00:01
> 
> **Edoardo Foco:** Hey, Oli. Hey, Edoardo.
> 
> 
> ### 00:00:03
> 
> **Oli Woolf:** How was your evening?
> 
> 
> ### 00:00:07
> 
> **Edoardo Foco:** Yeah, can't complain, can't complain. With 2 kids, it's never easy, man.
> 
> 
> ### 00:00:10
> 
> **Oli Woolf:** But I can only imagine. Hopefully I'll get there one day.
> 
> 
> ### 00:00:15
> 
> **Edoardo Foco:** Are you sure you want that?
> 
> 
> ### 00:00:17
> 
> **Oli Woolf:** Well, yeah, good. Yeah, right now, yeah, probably right now I think I do, but, uh, maybe Yeah, you spent— you, uh, you had your hands full then.
> 
> 
> ### 00:00:34
> 
> **Edoardo Foco:** Yeah, yeah, yeah. But I mean, it's, it's very nice anyway. Um, dude, the thing is, every evening it's a fight.
> 
> 
> ### 00:00:44
> 
> **Oli Woolf:** Yeah, but it's like, how old are your 2 kids?
> 
> 
> ### 00:00:46
> 
> **Edoardo Foco:** Um, 3 years, uh, 8 months, and 1 year and 3 months.
> 
> 
> ### 00:00:52
> 
> **Oli Woolf:** Wow, okay.
> 
> 
> ### 00:00:53
> 
> **Edoardo Foco:** So one is in the terrible too, so it's like, yeah, it's like everything is a fight, right? It's a compromise. You do that, you take a shower, you can watch a little bit of videos, right?
> 
> 
> ### 00:01:07
> 
> **Oli Woolf:** Yeah, I, uh, I don't envy you, I'm not gonna lie.
> 
> 
> ### 00:01:13
> 
> **Edoardo Foco:** Is Chris—
> 
> 
> ### 00:01:15
> 
> **Oli Woolf:** I'm sure he is turning up. We'll give him a couple of minutes. But did you, before we start, did you see I, I typed up Um, the document from yesterday, um, and shared it with you.
> 
> 
> ### 00:01:28
> 
> **Edoardo Foco:** I have not seen it. No problem, Christos.
> 
> 
> ### 00:01:31
> 
> **Oli Woolf:** It's, uh, it's all good. I'll share my screen quickly now. We can give him a couple of minutes.
> 
> 
> ### 00:01:35
> 
> **Edoardo Foco:** I'm sure he'll join.
> 
> 
> ### 00:01:37
> 
> **Oli Woolf:** So let's get rid of this. So essentially, this is everything we spoke about, right? Um, you can have a read of it all. And obviously, if you've got any comments to add, please add comments where appropriate. But the main thing here is that this information is accurate, that this information is accurate, you know, because this is going to be our source of truth. This is what we're going to constantly refer back to when it comes to kind of hiring. These are the bandings that I've been given. You know, maybe you disagree with that. Maybe people in your team don't align with that. Like, happy to have conversations here. Now, these these bits, this bit is not as important. I can kind of complete that async. But if there's any kind of career development, professional development opportunities that you think will help accelerate or progress. Applicants' careers by being part of NALA, or specifically part of engineering at NALA. This is just a good place to put them, and it helps me kind of curate that sell, that attraction piece, a little bit more. You know, another angle to it. This is arguably the most important section. These are what we discussed yesterday as the non-negotiable skills. Yeah. So basically, if I found you. an applicant with only these 6 things and nothing else, what we've essentially discussed yesterday. Hey, Chris.
> 
> 
> ### 00:03:17
> 
> **Christos Petropoulos:** Sorry I'm late.
> 
> 
> ### 00:03:18
> 
> **Oli Woolf:** No worries.
> 
> 
> ### 00:03:18
> 
> **Christos Petropoulos:** I ended up overrun.
> 
> 
> ### 00:03:20
> 
> **Oli Woolf:** All good, all good. I was just talking through— I'm not sure if you've seen, I shared this document with you, um, yesterday afternoon, which was kind of the write-up of what we discussed, uh, for engineering yesterday.
> 
> 
> ### 00:03:34
> 
> **Christos Petropoulos:** I haven't seen it, but I can check now.
> 
> 
> ### 00:03:36
> 
> **Oli Woolf:** No problem.
> 
> 
> ### 00:03:36
> 
> **Christos Petropoulos:** I saw the notification, but I haven't opened it.
> 
> 
> ### 00:03:38
> 
> **Oli Woolf:** Yeah, all good. Um, it's just about I guess between you just kind of sense checking what I've written down because it's going to be our source of truth, right? We're going to constantly kind of come back to this and iterate searches and maybe iterate, you know, questions in interviews, and it's all going to relate ultimately back to these 6 skills. These are the non-negotiables, as I'm aware of it, of what we need in a strong engineer. This is the level that we need candidates to be at, and this is how they're going to utilize those skills and the context around that. Now importantly, down here, let me zoom in on this a little bit. So in my talent screen, what we want to do, or across the whole of the interview like process, what we want to do is make sure that we are covering these 6 skills at an appropriate level of depth, um, an appropriate number of times, right? So, um, whilst I'm not super technical, I can at least screen to a high level for Go skills in my talent screen. I can obviously screen for comms, and I can ask them examples about where they've built scalable systems and where they've owned things, right? That will then give you a signal Or us a signal about whether or not at a really high level they're worth continuing a conversation with. Now, what I'd be interested to hear is, does the pair programming task and does the architecture task— is it designed to actually capture and assess some of these things?
> 
> 
> ### 00:05:21
> 
> **Edoardo Foco:** Yeah, so the pair programming, obviously the goal, uh, if he's good with Go And not necessarily message broker experience. Architecture stage is yes, Kafka basically.
> 
> 
> ### 00:05:37
> 
> **Oli Woolf:** Great.
> 
> 
> ### 00:05:39
> 
> **Edoardo Foco:** As well as architecture and scalable systems.
> 
> 
> ### 00:05:42
> 
> **Oli Woolf:** So this is message broker. Yep. And then scalable systems again. Great. So we're touching that twice. This is good.
> 
> 
> ### 00:05:51
> 
> **Christos Petropoulos:** Architecture is also touched. Oh yeah, go for it. Sorry.
> 
> 
> ### 00:05:55
> 
> **Edoardo Foco:** Yeah, yeah. Also touches product, uh, product awareness.
> 
> 
> ### 00:06:00
> 
> **Oli Woolf:** Amazing.
> 
> 
> ### 00:06:01
> 
> **Christos Petropoulos:** Great.
> 
> 
> ### 00:06:01
> 
> **Edoardo Foco:** Communications, obviously. Yep, it touches fundamentally all the points involved.
> 
> 
> ### 00:06:06
> 
> **Oli Woolf:** Awesome. Uh, I'll tidy this up after, but yeah, anyway, I'll tidy this up after, but it would be good, um, to kind of look through this and just be very clear on, okay, Are we actually— do we have a— and it sounds like we do, but it's always good to just sense-check it— do we have an interview process that actually captures and allows us to assess the key things we've just— we've said we need? Because we don't want to get to this stage, or even after this stage, where we're making a decision and we go, oh, we need an extra conversation because we don't feel like we've got ownership mentality. Like, we we've delved into that enough. Um, so yeah, this has been shared with you. Um, review it over the next kind of 48-72 hours. I'm really open to your comments on it, and this can be our kind of source of truth when it comes to backend engineering and hiring moving forwards.
> 
> 
> ### 00:07:05
> 
> **Edoardo Foco:** Cool.
> 
> 
> ### 00:07:06
> 
> **Oli Woolf:** All right, so obviously in a similar vein to yesterday, I kind of like to run through this again with you both, but with a platform spin on it, right?
> 
> 
> ### 00:07:16
> 
> **Edoardo Foco:** Yeah, I think Christos had the question.
> 
> 
> ### 00:07:18
> 
> **Oli Woolf:** Sure, Christos, sorry.
> 
> 
> ### 00:07:20
> 
> **Christos Petropoulos:** More of like a note. The document is actually pretty nice, to be honest, and it showcased one of the items we haven't added for screening that might be helpful for putting people away. So on the items for the screening, we don't have anything specific on architecture. You have scalable systems in a way, but designing systems might be slightly different. And why I'm mentioning this, based on the stuff you have on the screening, on the items, if someone is good at Go, they have worked with scalable systems, they have ownership, they're product aware, but they haven't designed heavily, they will probably go past the pair programming, but then they might fail in architecture. And I think architecture is probably our biggest fail rate because As you can see, it touches— it's the main interview, let's say. So maybe we can add something on screening on you just asking, hey, have you been architecting systems? Or what's the biggest feature you architected and how you did it? Whatever, just to, you know, right?
> 
> 
> ### 00:08:23
> 
> **Oli Woolf:** Uh, I'll just add a note, system scalable. Yeah, that's it, that's it, with architecture. Um, yeah, I'll make sure that that's that question, that line of questioning is focused more— well, there's a line of questioning on scaling, and there's also a line of questioning on architecture as well. Yeah, again, even a simple thing like that can make a huge difference now. It means I can, um, reject people rather than pushing them through. So look, this might take a week to iterate to get it.
> 
> 
> ### 00:08:53
> 
> **Christos Petropoulos:** Fair, fair.
> 
> 
> ### 00:08:54
> 
> **Oli Woolf:** It's not going to stop me from going to market and finding more people. It's just a good exercise we can work on async to build Confidence in ourselves. You know, you guys then have confidence in me that I'm looking for what you need and that we're screening them to a relevant level. So by the time you get involved at architecture stage, hopefully with a fair degree of confidence, you can go into an interview thinking, this is not going to be a waste of my time, and I'm quite excited to talk about someone, rather than, oh, I wonder what's going to happen today. So yeah, okay, really good call out. And please keep those, keep those comments coming over Slack as notes on the, on the doc, and we can iterate this and get it to a good spot. So yeah, I'm conscious of time and keen to, keen to chat about platform because I'll spin one of these up for platform as well. So, um, from the top then, kind of role title, are you looking for senior platform engineers? Are you looking for You know, juniors, mids, leads, what are you, I guess by title, what are you looking for?
> 
> 
> ### 00:10:04
> 
> **Christos Petropoulos:** Cool.
> 
> 
> ### 00:10:05
> 
> **Edoardo Foco:** So we're looking for senior. I'll just give you some context here.
> 
> 
> ### 00:10:10
> 
> **Oli Woolf:** Please.
> 
> 
> ### 00:10:12
> 
> **Edoardo Foco:** We absolutely need someone who can own platform infrastructure. Okay, this is the single person that will enable us to deploy servers and monitor servers and do, you know, All the infrastructure bits between Rafiki and Nala. So he needs to be senior. So the way I framed it is a senior platform engineer who's hungry to become like lead staff level, something like that.
> 
> 
> ### 00:10:43
> 
> **Oli Woolf:** Okay, makes sense. So would this be our first standalone platform hire? Do we currently have people working on platform, but they're part of engineering and it's kind of a An afterthought is the wrong, is the wrong word, but it's, it's, it's a secondary element of their job. And this is now someone that is solely focused on platform, or what's our existing kind of platform setup?
> 
> 
> ### 00:11:05
> 
> **Edoardo Foco:** I'll give you some, some background history here. Originally we had Seb and Nico. Nico was CTO, who were managing most of the infrastructure.
> 
> 
> ### 00:11:12
> 
> **Christos Petropoulos:** They left.
> 
> 
> ### 00:11:13
> 
> **Edoardo Foco:** We had an, we had an EM takeover. EM left for various reasons. And now fundamentally me, Christos, and Ale are mostly owning the infrastructure with some engineers making considerable changes like Arek, for example. Truth is none of us is a pure platform infrastructure engineer, so we don't have right now the capability in-house to actually cater for major incidents or major factors in that space. So again, we need someone that cannot just, you know, go there and fix a couple of servers. We need someone that actually implements the best practices and creates a solid stance of infrastructure.
> 
> 
> ### 00:12:01
> 
> **Oli Woolf:** Makes sense. Okay.
> 
> 
> ### 00:12:03
> 
> **Edoardo Foco:** Christos, I'm not sure if you have anything to add here.
> 
> 
> ### 00:12:05
> 
> **Christos Petropoulos:** No, I agree 100%.
> 
> 
> ### 00:12:07
> 
> **Edoardo Foco:** Great.
> 
> 
> ### 00:12:08
> 
> **Oli Woolf:** From a location perspective, are we still working as we were yesterday, you know, remote in Europe, plus minus 2 hours of London, or do we have a hard requirement for this platform person to be in London given they'll be the first standalone in that area? And what's your opinion on it, both of you?
> 
> 
> ### 00:12:29
> 
> **Edoardo Foco:** I don't care where he's based. Again, I don't think— I mean, even if he was in London, he would be working alone in the office because there's not much interaction with engineers. Marcus himself is not close to infrastructure, so Okay.
> 
> 
> ### 00:12:42
> 
> **Christos Petropoulos:** I would also double-check with Owen and Marcus just in case though, you know.
> 
> 
> ### 00:12:46
> 
> **Edoardo Foco:** Sure.
> 
> 
> ### 00:12:46
> 
> **Christos Petropoulos:** But I agree with Edu.
> 
> 
> ### 00:12:48
> 
> **Oli Woolf:** Yeah, okay, great. All right, so let's work through, um, the key stakeholders then. Do, um, does Eduardo—
> 
> 
> ### 00:12:57
> 
> **Edoardo Foco:** Sorry if I interrupt you. Um, in the hiring infrastructure channel, I actually created a whole like roadmap of his first like 3 months and like evolution plan.
> 
> 
> ### 00:13:06
> 
> **Oli Woolf:** Great.
> 
> 
> ### 00:13:07
> 
> **Edoardo Foco:** Uh, so if you could have a read of that, that would be great. It covers a lot of things.
> 
> 
> ### 00:13:12
> 
> **Oli Woolf:** When was that posted? Obviously I've only been with Nala for like a week and a half, so I don't know if I have chat history to see that.
> 
> 
> ### 00:13:19
> 
> **Edoardo Foco:** I'll tag you, give me a second.
> 
> 
> ### 00:13:21
> 
> **Oli Woolf:** Yeah, thank you. Oh, Thursday, June the 11th, actually. Yeah, I do see it. Yeah, I do see it. Okay, so again, for the note-taker, I will review Edoardo's Slack note in the Hiring Infra Engineer channel from June 11th about the first 30, 60, 90 days. Great. Okay, really useful. Um, that probably answers some of the questions I'm about to ask, so forgive me for that. Um, I haven't seen that yet. The, the stakeholders, um, we discussed yesterday, Marcus, uh, Yourself, Eduardo, and yourself, Christos. And then for engineering, some of the key stakeholders would be product managers. Now, um, are product managers also relevant stakeholders to platform or not so much?
> 
> 
> ### 00:14:19
> 
> **Edoardo Foco:** Sorry, I got distracted.
> 
> 
> ### 00:14:21
> 
> **Oli Woolf:** All good. The, the key stakeholders for the platform, um, role Is it similar to the engineering role? So Marcus, yourself, Christos?
> 
> 
> ### 00:14:32
> 
> **Edoardo Foco:** No, it's a bit different.
> 
> 
> ### 00:14:33
> 
> **Oli Woolf:** Sure.
> 
> 
> ### 00:14:33
> 
> **Edoardo Foco:** I mean, yes, yes, for sure. There's also another stakeholder there, which is Petros, which is head of security for all, for everything that, you know, is for SOC 2 compliance certifications and that kind of stuff.
> 
> 
> ### 00:14:48
> 
> **Oli Woolf:** Yep. Petros Kirillist. Yeah.
> 
> 
> ### 00:14:52
> 
> **Edoardo Foco:** Kirillist.
> 
> 
> ### 00:14:52
> 
> **Christos Petropoulos:** Yes.
> 
> 
> ### 00:14:52
> 
> **Oli Woolf:** Yeah. Kirillist. Yeah. Apologies. I'll do my best. It comes from a good place, I promise.
> 
> 
> ### 00:15:00
> 
> **Christos Petropoulos:** Don't worry, man.
> 
> 
> ### 00:15:01
> 
> **Oli Woolf:** You also, you also mentioned, um, Ale in passing as well. How involved is Ale going to be with, uh, Alessandro, with, with, with platform? Would you put him alongside both of you as a key stakeholder, or he actually— maybe should he have been mentioned in the engineering stakeholders yesterday?
> 
> 
> ### 00:15:22
> 
> **Edoardo Foco:** Yes, he should have been mentioned in the engineering stakeholders for sure. Look, me, Christos, and Ale, we operate at the same level across all the organization. So yes, we are the main stakeholders at the end of the day.
> 
> 
> ### 00:15:34
> 
> **Oli Woolf:** Fine. I'm just going to add Ale into—
> 
> 
> ### 00:15:37
> 
> **Edoardo Foco:** Unless it's very much Rafiki-specific or NALA-specific, it's all 3 of us.
> 
> 
> ### 00:15:42
> 
> **Oli Woolf:** Fine. So Alessandro Colaneri, so he's an engineering manager as well. I know, Edoardo, you look after T-Rex. Chris, you look after B. Um, does Ale have his own squad? Where— how does he sit in that dynamic? What— how's he positioned?
> 
> 
> ### 00:16:02
> 
> **Edoardo Foco:** He owns all of the Rafiki engineering, which is 2 squads for now. Uh, treasury and compliance, I think. And, uh, I forgot the name of the other one. Payouts. Sorry, payouts and compliance. And treasury and something else.
> 
> 
> ### 00:16:20
> 
> **Christos Petropoulos:** Yes.
> 
> 
> ### 00:16:20
> 
> **Edoardo Foco:** And collections, maybe.
> 
> 
> ### 00:16:22
> 
> **Oli Woolf:** Okay, great, perfect. So, um, he's not as relevant to platform but certainly relevant to engineering. Um, you would add Petros in as a relevant stakeholder for platform. Are there any other, um, you know, important stakeholders that are worth recognizing?
> 
> 
> ### 00:16:43
> 
> **Edoardo Foco:** So there might be data, there might be data, which is Parth. Um, yep, yeah, for all the infrastructure that touches data.
> 
> 
> ### 00:16:51
> 
> **Oli Woolf:** Okay, great, lovely. Um, so tell me, I think I understand why there's a need for this role and, and the purpose of it, uh, and kind of what problem they'll be expected to solve. Are there any, um, key projects That, uh, you know, they'll be involved in, in their first 6 months?
> 
> 
> ### 00:17:15
> 
> **Edoardo Foco:** Yeah, that's all in the thing that I shared in thread.
> 
> 
> ### 00:17:19
> 
> **Oli Woolf:** Great.
> 
> 
> ### 00:17:19
> 
> **Edoardo Foco:** So I mean, we can read them out loud for now, but, um, sure, if you're, if you're comfortable too.
> 
> 
> ### 00:17:25
> 
> **Oli Woolf:** Yeah.
> 
> 
> ### 00:17:26
> 
> **Edoardo Foco:** Yeah, look, first 90 days is basically understand where we are, take the wheel, uh, map the estate. review the documents that we have, security baseline. So basically assess our security posture, create processes to capture the infrastructure requirements from the different teams. So we don't have a process for that right now. Improve observability, I would say, and then try to understand where AI can help us. 3 to 6 months is optimize and automate. Again, if there are like, for example, there is a service that we know that doesn't scale well, we need to address that. He will need to address that. We have some backlog items that he has to work on, and finally lay the ground for AI-driven incident management and observability. Then 6 to 9 months. Is— so we have this project in mind that we haven't had the capabilities to work on until now, which is basically creating the so-called Simba infrastructure, which is moving some shared services into a separate AWS account.
> 
> 
> ### 00:18:47
> 
> **Oli Woolf:** Okay, great.
> 
> 
> ### 00:18:49
> 
> **Edoardo Foco:** Is that enough?
> 
> 
> ### 00:18:50
> 
> **Oli Woolf:** Yeah, no, that's, that's really useful. Chris, anything to add there?
> 
> 
> ### 00:18:54
> 
> **Christos Petropoulos:** From your side, only item that person might also pick up, Edo, it's the Atlantis bit which we never finished. And if that person does that, then engineering might be more autonomous based on the instructions of that person and how to self-serve. So while they're building, while they're automating, they're helping us self-serve a bit better on the smaller stuff that we do.
> 
> 
> ### 00:19:18
> 
> **Edoardo Foco:** That's actually a very good point. Like We need someone that can actually help engineers be self-serve, basically.
> 
> 
> ### 00:19:29
> 
> **Oli Woolf:** Sure.
> 
> 
> ### 00:19:29
> 
> **Edoardo Foco:** That's a super valid point.
> 
> 
> ### 00:19:31
> 
> **Oli Woolf:** Okay, makes sense. Who will this person report to? Will it be one of you two or Ali, or will they go straight into Marcus?
> 
> 
> ### 00:19:39
> 
> **Edoardo Foco:** It would be me for now.
> 
> 
> ### 00:19:41
> 
> **Oli Woolf:** It'd be you. Okay, great. I've got the question here, who will they be working with and why? There's no dedicated platform team, they'll be the first one, but I'm gonna assume that they'll be working with, you know, engineering, security, data, you know, the areas that we've mentioned. Is that a fair observation?
> 
> 
> ### 00:20:04
> 
> **Edoardo Foco:** Yep.
> 
> 
> ### 00:20:04
> 
> **Oli Woolf:** Yeah, great. Okay, um, initially, will they have any— they won't have any direct reports, will they? Anyone reporting into them? Okay, great. Um, Are there any—
> 
> 
> ### 00:20:16
> 
> **Edoardo Foco:** to be fair, I don't think they will ever have reports. Um, well, depends if we scale a lot, but yeah.
> 
> 
> ### 00:20:25
> 
> **Oli Woolf:** I was gonna say, you, you don't see platform as, as Nala, as Rafiki grows, you don't see platform, um, needing to kind of scale or grow with it and maybe having a similar sort of squad?
> 
> 
> ### 00:20:40
> 
> **Edoardo Foco:** Yeah, so not in the— so first off, we got here without having any infrastructure resources. First thing. Second thing is in the next year, probably not. If we do scale to actually be like, you know, a big employer company and stuff like that, yes, probably we're gonna need one. We're gonna need a team.
> 
> 
> ### 00:20:59
> 
> **Oli Woolf:** Okay.
> 
> 
> ### 00:21:00
> 
> **Christos Petropoulos:** Yeah, but I wouldn't count on it as something to advertise or not advertise, because if you tell them they will, then they might expect it and expect to get to a role that might not exist, but if you tell them it might not, they might not be interested. So it's somewhere in between, but we don't know, and that person is going to help us actually figure that out as we go and grow. And the better it goes, you know, and that's the exciting bit, right?
> 
> 
> ### 00:21:24
> 
> **Oli Woolf:** They're going to have ownership and a voice at the table when it comes to the direction of this kind of platform strategy at NALA and Rafiki. Okay, great. In terms of ways of working, will they jump in with engineering, the engineering way of working? Will they join engineering standups? Do you know what the expectation is there?
> 
> 
> ### 00:21:53
> 
> **Edoardo Foco:** No, we're going to have a lighter version of this. Probably in the first month or 2 months, it's going to be like a daily standup with just me and him.
> 
> 
> ### 00:22:02
> 
> **Oli Woolf:** Yep.
> 
> 
> ### 00:22:02
> 
> **Edoardo Foco:** Um, but then it's going to be a lot lighter.
> 
> 
> ### 00:22:05
> 
> **Oli Woolf:** Okay.
> 
> 
> ### 00:22:06
> 
> **Edoardo Foco:** Like maybe every couple of days, something like that.
> 
> 
> ### 00:22:09
> 
> **Oli Woolf:** Makes sense. Okay, cool. From a technology standpoint, um, what, uh, I know we're an AWS house, right? Um, but what technology, um, is this person going to be required to use or, or learn in this role? Can Kind of run me through the stack.
> 
> 
> ### 00:22:31
> 
> **Edoardo Foco:** So learn, nothing to learn, like he has to know it. Uh, but yeah, it's, uh, I mean, AWS and Terraform are the main things. I don't know, uh, do you want— yeah, I'm not sure if I should map everything, like it's a lot of services.
> 
> 
> ### 00:22:46
> 
> **Oli Woolf:** No, please do, because it will be captured, and it doesn't mean we have to target everything in a search, but it's just good to know if someone asks me what stack we're We're working with ECS, RDS, Kafka.
> 
> 
> ### 00:22:59
> 
> **Edoardo Foco:** I'm thinking CodePipeline, CodeDeploy, CodeBuild. Then we have TwinGate. We have Neo4j database. Christos helped me out.
> 
> 
> ### 00:23:17
> 
> **Christos Petropoulos:** To add more? Yeah.
> 
> 
> ### 00:23:21
> 
> **Edoardo Foco:** Vault. Vault. HashiCorp Vault. Yeah, that's a big one. There's a big one.
> 
> 
> ### 00:23:31
> 
> **Christos Petropoulos:** Let me think.
> 
> 
> ### 00:23:33
> 
> **Edoardo Foco:** IAM.
> 
> 
> ### 00:23:35
> 
> **Christos Petropoulos:** Yeah, for sure. IAM is a big one.
> 
> 
> ### 00:23:43
> 
> **Edoardo Foco:** You know what? Why am I even thinking about this? I should just ask Claude.
> 
> 
> ### 00:23:48
> 
> **Christos Petropoulos:** Yeah, that's a good point, actually. Well, there are others in terms of Kafka and everything, right? But that's also a managed service, right? AWS. Kafka is in the mix.
> 
> 
> ### 00:24:05
> 
> **Edoardo Foco:** Sure.
> 
> 
> ### 00:24:05
> 
> **Christos Petropoulos:** I'm guessing. AppSync is new. It might get more traction. Well, secrets management, CloudWatch-related things, although that's part of observability. Yeah, I think Claude will find more in a second.
> 
> 
> ### 00:24:42
> 
> **Edoardo Foco:** Sure.
> 
> 
> ### 00:24:42
> 
> **Oli Woolf:** While Claude's doing its thing, I'm just kind of reading your note, Edoardo, in the channel. We'll talk about the interview process and then we'll finish on, as we did yesterday, with the absolute non-negotiable skills and go through that, right? But the interview process, I'll do a talent screen, then You've got in your note the technical test will be 90 minutes and mostly based on architecture and a 20-30 minute Terraform run-through. So do we not need a pair program? Do we go talent screen straight to architecture, then to Bar Raiser? Do we just kind of remove pair programming, or how do you want to structure it?
> 
> 
> ### 00:25:26
> 
> **Edoardo Foco:** Yeah, I mean, the architecture should be like an hour and a half. But even this was— is somewhere. But yeah, architecture should be like 1 hour and a half and it's gonna be split in 2 parts. The first part is like pure architecture, like system design. The second one is him writing Terraform. So he has to have like Terraform installed and stuff like that. Sure.
> 
> 
> ### 00:25:53
> 
> **Oli Woolf:** And then if that goes well, so that's straight after talent screen, after I've spoke to them, if that goes well, We then push them to a bar raiser or like a final. Yeah, yeah. Who would do that? Is that where Marcus would jump in, or would, would one of you two jump in? I suppose take it a step back, who would lead the architecture task? Would that be you, both of you, or?
> 
> 
> ### 00:26:16
> 
> **Edoardo Foco:** Yeah, so that would be always 2 people. Probably, yeah, me, Christos, Ale Christos, and Seb, which is an external contractor.
> 
> 
> ### 00:26:27
> 
> **Oli Woolf:** Okay, all right. And then the bar raiser, um, Marcus. Fantastic. Okay, so it's kind of a stage less than engineering, but it's a little bit more intense.
> 
> 
> ### 00:26:38
> 
> **Edoardo Foco:** Yeah.
> 
> 
> ### 00:26:39
> 
> **Oli Woolf:** Great. Um, let's, let's go with that for now. Um, obviously 90 minutes is a big time commitment for people, uh, and I'll, I'll do my best to screen and reject people that are unsuitable as best I can. but there's always a risk that, um, you know, someone slips through. So maybe just something to think about, maybe we have a brief, you know, 15-minute or 30-minute conversation, um, to just go into a little bit after my stage before architecture, um, just from one— whether it's you, whether it's one of your team— just to actually talk shop with these people and make sure they're not just BSing me and they know what what's what before we kind of commit to 90 minutes with them. Something to think about. We can discuss this kind of as we iterate this document, but something I would— I wanted to flag.
> 
> 
> ### 00:27:31
> 
> **Edoardo Foco:** Yeah, um, that's fine. Uh, one thing, one comment, please. This is the first time we do these sort of interviews. There are going to be some teething issues.
> 
> 
> ### 00:27:42
> 
> **Oli Woolf:** Yep.
> 
> 
> ### 00:27:43
> 
> **Edoardo Foco:** I am almost, um, Let's see what you get. But we also need to, you know, again, we've never done them, so we're gonna fuck up a few times. So even if you send us like some little bit shit candidates at the start, I think it's fine. Christos, not sure what you think about it.
> 
> 
> ### 00:28:02
> 
> **Christos Petropoulos:** I mean, we have to iterate either way. But you know what happens usually with this, with these things, the first person you get unfortunately will be the best one. And then everyone afterwards is gonna be worse.
> 
> 
> ### 00:28:17
> 
> **Oli Woolf:** Yeah.
> 
> 
> ### 00:28:17
> 
> **Christos Petropoulos:** Yeah, I mean, we have to, right? There will be stuff, but Oli's point is very important actually, I guess for both reasons, right? One is for us to understand if this is even worth, like, from another perspective. But I guess on the other hand, Oli, we can sell this, right? Hey, this interview process, just one. We're not gonna annoy you. It's just one. You do 90 minutes once and you know. I don't know, but I, I think it makes sense if you just add the tiny bit. Um, sure, like an extra thing and that's it.
> 
> 
> ### 00:28:47
> 
> **Edoardo Foco:** Sure.
> 
> 
> ### 00:28:47
> 
> **Oli Woolf:** Okay, let's see, let's see where we land. I'm conscious of time, um, so hopefully we can all spare a couple of extra minutes and just talk me through, as we did yesterday with the engineering stuff but for platform, the non-negotiables. If I find you a candidate with only these things, they're worth a chat. What are these things from a platform perspective?
> 
> 
> ### 00:29:13
> 
> **Edoardo Foco:** We don't know. Well, let's—
> 
> 
> ### 00:29:15
> 
> **Oli Woolf:** I'll give you a starter. Obviously AWS is, is, is a non-negotiable, right?
> 
> 
> ### 00:29:21
> 
> **Edoardo Foco:** Or AWS and Terraform are non-negotiables.
> 
> 
> ### 00:29:23
> 
> **Oli Woolf:** Okay, great. Um, uh, fine. So again, devil's advocate here, has to be AWS, or if someone can evidence, um, you know, the same skills and the same builds in GCP We're happy for them to like come and do it in AWS with us, or we are like hardline must be AWS?
> 
> 
> ### 00:29:46
> 
> **Edoardo Foco:** I, I would feel a lot more comfortable if it was AWS.
> 
> 
> ### 00:29:50
> 
> **Oli Woolf:** Cool, great. Um, okay, and Terraform as well.
> 
> 
> ### 00:29:57
> 
> **Edoardo Foco:** So Terraform is a must.
> 
> 
> ### 00:30:01
> 
> **Oli Woolf:** Yeah, sure, I'm just looking. So what's the expectation level then with With both of those things? Obviously they're going to be using them day to day as part of like setting up the infrastructure environment and building on the infrastructure environment, but what level are we— what are we looking for them to have done with Terraform and AWS previously as a good signal?
> 
> 
> ### 00:30:22
> 
> **Edoardo Foco:** Jedi. It's human Jedi level. No, uh, dude, it's like senior level. Like we need someone that can actually— that is better than us.
> 
> 
> ### 00:30:32
> 
> **Christos Petropoulos:** Okay, right.
> 
> 
> ### 00:30:33
> 
> **Edoardo Foco:** I wouldn't consider myself a senior, but you know, I can do myself. I don't need someone that can do myself at my level. I need someone senior who can actually shape everything.
> 
> 
> ### 00:30:41
> 
> **Oli Woolf:** Yep.
> 
> 
> ### 00:30:43
> 
> **Edoardo Foco:** Assess it and shape it.
> 
> 
> ### 00:30:45
> 
> **Oli Woolf:** So this, this is, this, this is an interesting question then, because, um, I love that you are, um, aware that actually the person we bring in needs to almost teach us Right.
> 
> 
> ### 00:30:58
> 
> **Edoardo Foco:** Yeah.
> 
> 
> ### 00:30:58
> 
> **Oli Woolf:** Um, but that then poses— that's really interesting and exciting, but it poses potentially a, a different question, which is, if we don't know what we need to know, how do we assess whether the person that we're bringing in is actually good and the right person, you know?
> 
> 
> ### 00:31:15
> 
> **Edoardo Foco:** Um, which is going to be the catch here, and that's why we're going to have teething issues. Um, but we have like a whole process written down run the interview for things that we're looking for and stuff like that. First thing. Second of all, the architecture and design stage is specifically like the interview is specifically designed to poke the person on some specific things that we know we have prepared on those and are the foundations for the rest. The thing is, we know architecture quite well from like a design perspective. We don't know it that well from like a day-to-day working on it. So it's like, I know the— I know how software engineering works pretty well. I don't know Golang in particular that well, you understand? That's kind of like the difference where we're, uh, that we're doing.
> 
> 
> ### 00:32:08
> 
> **Oli Woolf:** Makes sense. Okay, would you, from your knowledge, is there any other non-negotiables for you over AWS and Terraform? Um, you know, we can talk soft skills as well like we did yesterday, but Yeah, I mean, no, not really.
> 
> 
> ### 00:32:23
> 
> **Edoardo Foco:** I mean, those are the main things. The rest he can for sure.
> 
> 
> ### 00:32:29
> 
> **Oli Woolf:** Okay.
> 
> 
> ### 00:32:30
> 
> **Edoardo Foco:** Like, I don't care if he doesn't know, for example, ECR, which I'm sure he knows, or Elasticsearch. It's not the single AWS services that I'm interested. I'm interested in him knowing how, you know, networking works, how he can apply it to Terraform, The security best practices. Yeah.
> 
> 
> ### 00:32:51
> 
> **Oli Woolf:** Great. Okay, that's really useful knowledge. Thank you so much for your time again. I'm going to spend the course of today and tomorrow building another document for platform that we can— that I'll share with you both, and we can iterate and work on so that, you know, sort of hopefully by Monday We're in a good place where we have 2, 2 source of truths. We have an engineering kind of hiring bible and we have a platform hiring bible. And, um, you know, it's hosted on Google and everyone who needs to see it can see it. And then we can use that as our, um, kind of guiding light in terms of what we're looking for, how we're assessing it, what good looks like, etc. So leave that with me. Let me get that built. Um, And yeah, we'll go from there.
> 
> 
> ### 00:33:42
> 
> **Edoardo Foco:** Thanks, man. I appreciate this is not going to be as easy as I imagined.
> 
> 
> ### 00:33:45
> 
> **Oli Woolf:** Thank you so much, Edoardo.
> 
> 
> ### 00:33:46
> 
> **Edoardo Foco:** Engineer role.
> 
> 
> ### 00:33:47
> 
> **Oli Woolf:** Hey, look, if everything was easy, life would be boring, right? I like a challenge. Let's see where we go with it.
> 
> 
> ### 00:33:54
> 
> **Edoardo Foco:** That's, that's good. See you later, man.
> 
> 
> ### 00:33:56
> 
> **Oli Woolf:** Thanks. Bye. Take care. Bye now.
