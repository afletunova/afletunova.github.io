---
title: "How to Hire a Data Person in the AI Era"
date: 2026-06-29
draft: false
weight: 2
tags: ["data", "hiring", "engineering", "ai"]
languages: ["english"]
description: "Most hiring processes are optimised to filter, not to find. A structural look at what to fix, from someone who has been on both sides."
---

Why is everyone now disappointed by the hiring process nowadays, and how does one hire the best match for their data team? I’ll be honest, I want to know the answer to this question myself. I have interviewed candidates for the DE position, and I’ve written those JDs myself. However, the industry is evolving so fast that it is hard to keep up, especially when you have other tasks on your plate. AI is now handling much of the process, and you are keeping old habits while interviewing people: they are effective, quick, and supposed to be fair to everyone. But many would disagree.

Hence, after I landed in the current job market and was interviewed once again, I decided to combine my experience from both sides and try to solve this issue structurally. I came up with this attempt to assess someone’s, as my own, through a completely new prism.

# Where the issue lies

Many of us have heard and seen with our own eyes how many candidates are great on paper and how disappointed you are after you e-meet them in person. You had 1000 applications with 10 interviews set up with the most prominent talents… and one didn’t come at all, another was calling you from their car with a terrible sound, a couple of them, it seems like, heard about DBs for the first time in their life, some of them were terrible communicators, etc., etc., etc.

Where did this all go wrong?

As I see it, most hiring problems start before the first interview.

Easy-apply on LinkedIn, automated application systems, automated tracking systems, pushing candidates to tailor their CVs word-to-word to your JD, and many other little tweaks optimising the whole process flood pipelines with thousands of candidates who are not targeting your role specifically — they are targeting any job. Many of them have been through bootcamps that teach interview patterns, not engineering. They’ve optimised for passing filters, not for doing the work. The result is a loop:

> Companies get flooded -> add filters -> filters reward pattern-matching -> bootcamps teach pattern-matching -> more unqualified candidates pass -> companies add more filters -> genuine specialists get caught in the noise.

Everyone loses. The desperate candidate lands a job they’re wrong for. The company hires someone who can sprint but not lift.

## How can we fix this?

The solution I provide here may not work for all companies, teams, and processes. However, I want to describe the process I want to implement myself.

### Write a job description that describes the job

Vague JDs attract everyone. Be explicit about what the role is, and what it isn’t.

“This is not a backend engineering role. You will not be solving algorithm problems.”

You’ll lose some applicants (yes, those probably have some catchy labels in their CV) and gain better ones. Move nice-to-haves out of the JD entirely — if it matters, ask about it in the interview. If it doesn’t matter enough to ask about, it wasn’t a requirement.

### Remove easy-apply

A candidate who won’t write two sentences about why they fit the role isn’t a serious candidate. Ask one specific question in the application that requires real experience to answer — something that can’t be answered with a bootcamp pattern.

*“Describe a data quality issue you caught before it hit production. What caused it?”*

You can’t fake that.

### Ask your own team the same questions

See how varied their answers are.

If you are asking:

> Walk me through your workflow when you’re assigned a complex new task with a tight deadline. From the moment you receive the requirement to final delivery, what stages do you go through?

Do you know how this works in your own team? How does your own process look? What would everyone in your own team answer on that?

This calibrates your expectations and reveals what your team actually values — not what you think it values. If five engineers answer the same question five different ways, that’s a signal about your culture. Use these answers internally to compare against AI output and candidate responses. You can share them with candidates after they join, as onboarding context.

### The AI policy has two stages, and they’re different.

Here I am trying to solve the issue with a low-quality candidate pool. As a candidate myself, I hate filling those surveys; however, if the role is perfect for me, I am proud to answer. The issue is in the spread.

#### Stage one — the application screen: no AI

Ask a specific experience question that requires real context to answer. Run it through AI yourself first and note what a generic, pattern-matched answer looks like. If a candidate’s response matches that pattern too closely — flag it, don’t reject. Ask follow-up questions. If they want the job, they’ll explain themselves. This step can potentially be automated too.

#### Stage two — the take-home task: AI is allowed and expected

Today the signal shifts from “what do you know” to “how do you work.” Can they direct AI toward the right problem? Do they validate the output or blindly trust it? Can they explain every decision when you ask them about it in a follow-up conversation? If so, that’s the job, and that’s what you need on your team.

These are not contradictory. They test different things at different stages.

Some cons to this approach:

- **Timing.** This front-loads work. You’re building a rubric, writing good JD questions, calibrating your team, rotating your task bank. None of this happens in a week. Start when things are calm — not when your lead engineer just left, and you need someone in 30 days. The cost of a bad process doesn’t go away; it just gets passed on to the hire.
- **Keep your interviewers informed about the job market.** Hiring managers and interviewers often don’t know what bootcamps and career coaches are teaching, what patterns candidates are optimising for, or what the candidate experience of their process actually feels like. A recruiter who asks candidates what they found comfortable (and what they didn’t) generates intelligence that improves the process for everyone.

# How to assess their skills

Here’s the actual matter. Assuming we’ve now collected a higher-quality pool, what do we do with them next?

I’ll be talking exclusively about the job I know first-hand, but I truly believe that those practices can be applied to adjacent fields.

## Data (Platform | AI | Analytics) Engineer

Usually, this role requires the candidate to handle the load of incoming data, organise it in coherent layers, and cover maintenance and idempotence.

### Skills worth assessing

| Skill                                | Why it matters                                                                |
| ------------------------------------ | ----------------------------------------------------------------------------- |
| SQL (query writing and optimisation) | Core tool, used daily                                                         |
| Data modeling                        | Schema decisions have long-term consequences                                  |
| Pipeline thinking                    | How data moves, transforms, fails, recovers                                   |
| Tool fluency                         | dbt, Airflow, Spark (role dependent)                                          |
| Debugging                            | Given broken data or a broken pipeline, find the problem                      |
| Tradeoffs                            | When to use what (Postgres vs ClickHouse, batch vs streaming)                 |
| Python for data                      | Transformation and scripting, not algorithms                                  |
| Data quality instincts               | Do they ask “what if the source is wrong?”                                    |
| Ambiguity handling                   | Real data problems are underspecified                                         |
| Cost and scale awareness             | Will this query kill production?                                              |
| Vector databases                     | Embedding storage, similarity search (matters for RAG and semantic retrieval) |
| LLM integration patterns             | Prompt engineering, validation, when *not* to use an LLM                      |
| Embedding pipelines                  | How to chunk, embed, update, version vectors at scale                         |
Your specific role might require only couple of those skills, or their full combination. However, I will try to describe the process how I see it for all of them.
#### Skills NOT relevant for most data roles

- Leetcode-style algorithm problems: you can argue that your candidate should understand what’s happening under the hood, and I do agree with that. However, I don’t find this skill more valuable than everything else to spend your and candidates’ time on this.
- Low-level CS (memory management, pointers): same applies here
- Syntax recall under pressure: especially, in the era of AI, this skill might fully disappear. However, with great working flexibility, syntax recall can be picked up by any good candidate on the job if needed.
- Backend or frontend system design unrelated to data: that's just not supposed to be something you need to evaluate them for. Leave it for nice-to-haves or a quick follow-up if they’ve mentioned something connected.

### Assessment Methods

Now, let’s talk about exact ways to assess those skills from the section above. I won’t cover every skill separately; instead, I want to give you a set of possible formats to accommodate a vast pool of candidates, giving everyone the opportunity to show their strengths.

#### Take-home project

| Pros                                            | Cons                                                                              |
| ----------------------------------------------- | --------------------------------------------------------------------------------- |
| Flexible, no observer pressure                  | Interviewer must set clear, transparent expectations                              |
| Candidate can work in their natural environment | Open-ended problems may not work if the interviewer expects one specific solution |
| Tests real output quality                       | Penalises out-of-the-box thinking if rubric is rigid                              |
| Can be scoped to data-specific tasks            | Time investment may disadvantage candidates with caregiving responsibilities      |

**Best for:** SQL modelling, dbt project, pipeline design task, embedding pipeline design, RAG system implementation

#### Portfolio review

| Pros                                                                                  | Cons                                                     |
| ------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| Shows real work, not performance under stress                                         | Many engineers work under NDA or in private repos        |
| Reveals what the candidate finds worth building                                       | Not their intellectual property to share                 |
| Great signal for senior candidates                                                    | Skews toward candidates with side projects and free time |
| **Best for:** supplementary signal, or candidate-elected alternative to the take-home |                                                          |

**Rule:** offer portfolio as a candidate-elected format, evaluated on the same rubric as the take-home. This exists because NDA and IP constraints are real. Forcing a take-home when strong public work already exists wastes everyone’s time. This helps you to make decisions based on results instead of the format.

#### Open-source contribution

| Pros                                                                    | Cons                                         |
| ----------------------------------------------------------------------- | -------------------------------------------- |
| Real code, real context, real decisions                                 | Optional — not everyone contributes publicly |
| Shows initiative and communication (PR descriptions, issue discussions) | Skews toward candidates with free time       |
|                                                                         | NDA or employer restrictions may apply       |

**Rule:** optional signal, never a gate. Combine with portfolio.
#### Bring your own work

| Pros                                                             | Cons                                                    |
| ---------------------------------------------------------------- | ------------------------------------------------------- |
| Candidate speaks about something they built with genuine context | Must be optional, since not everyone has shareable work |
| Reveals passion, depth, and decision-making                      | Requires interviewer skill to probe effectively         |
| No NDA problem if candidate chooses what to share                |                                                         |

**Best for:** senior roles, architecture and design assessment

#### Async video explanation

| Pros                                              | Cons                                          |
| ------------------------------------------------- | --------------------------------------------- |
| No real-time pressure                             | Optional (accessibility varies)               |
| Candidate can prepare and present at their best   | Requires open or shareable project to explain |
| Tests communication to non-technical stakeholders |                                               |

**Rule:** optional, pairs well with portfolio or bring-your-own-work

#### Pair programming (async version preferred)

| Pros                                                                                                                                             | Cons                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------- |
| Collaborative, more natural                                                                                                                      | Synchronous version reintroduces observer pressure  |
| Tests how they think, not just what they produce                                                                                                 | Requires a well-scoped problem from the interviewer |
| Good for assessing communication style                                                                                                           | Async version requires more setup                   |
| **Best for:** debugging sessions on data-related problems — broken pipelines, bad SQL, wrong aggregations, broken vector search, embedding drift |                                                     |

**Not:** greenfield algorithm problems

#### System design discussion

| Pros                                                                                       | Cons                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Tests real senior skills (tradeoffs, architecture, failure modes)                          | Less useful for junior candidates without existing solutions base  |
| No memorisation required                                                                   | Requires an interviewer who can hold a real technical conversation |
| Reveals how candidates handle ambiguity and pushback                                       | Hard to standardise across interviewers                            |
| Naturally covers data modeling, pipeline design, tooling decisions, vector database choice |                                                                    |

**Best for:** senior and staff roles
**For mid-level:** ability to ask good questions without a pre-existing solutions base is sufficient signal.

#### Collaborative debugging

| Pros                                               | Cons                                                 |
| -------------------------------------------------- | ---------------------------------------------------- |
| Directly relevant for data roles                   | Requires realistic, well-prepared debugging scenario |
| Tests data quality instincts and pipeline thinking | Harder to set up than a leetcode problem             |
| Reveals how they communicate under uncertainty     |                                                      |
| No memorisation required                           |                                                      |

**Best for:** data platform, analytics engineering, data engineering roles
**Scenario examples:** broken dbt model, wrong aggregation, pipeline silently dropping rows, retrieval returning irrelevant results, embedding version mismatch

#### Paid trial day

| Pros                                                   | Cons                                                                    |
| ------------------------------------------------------ | ----------------------------------------------------------------------- |
| Closest to real work conditions                        | Expensive for the company                                               |
| Candidate works on actual problems, not synthetic ones | Legally murky — may constitute employment in some jurisdictions         |
| Strong signal for culture fit                          | Candidate may not be able to take a day off from current job            |
|                                                        | Full-day investment with no guaranteed outcome — power imbalance        |
|                                                        | Risk of exploitation: real work extracted under the guise of assessment |

**Rule:** must be paid, no exceptions

#### AI-assisted interview

| Pros                                                              | Cons                                                    |
| ----------------------------------------------------------------- | ------------------------------------------------------- |
| Reflects actual working conditions                                | Requires interviewers to redesign their rubric entirely |
| Tests judgment — do they validate AI output or blindly trust it?  | Some companies not ready culturally                     |
| Tests planning and problem decomposition before implementation    | Harder to compare candidates on a fixed scale           |
| Less stress, more signal                                          |                                                         |
| Reveals if the candidate’s tool use matches the company’s process |                                                         |

**Best for:** any role
**Key signal:** do they think and plan before prompting? Do they question the output?

#### Pre-shared case interview

| Pros                                                            | Cons                                                                 |
| --------------------------------------------------------------- | -------------------------------------------------------------------- |
| Candidate has time to learn the context before the conversation | Requires a well-prepared, realistic case, not a toy problem          |
| Tests context retention and navigational reasoning              | Case may leak over time — rotate regularly                           |
| Interview becomes a discussion, not a performance               | Interviewer needs skill to probe beyond the prepared answers         |
| Directly mirrors real engineering work                          | Candidate can over-polish — probe for edge cases they didn’t prepare |
| No artificial time pressure on problem-solving                  |                                                                      |

**How it works:** share a realistic problem, codebase excerpt, or incident description 24–48 hours before the interview. In the session, ask questions about it. Not “solve this” but “what would you investigate first?”, “what’s the risk if you change X?”, “what’s missing from this design?” The candidate who has genuinely engaged with the material thinks out loud differently from the one who skimmed it.
**Best for:** senior roles, data platform, any role where context navigation matters more than syntax recall

# Scoring method

What I propose here is not to choose one of those methods above, but to have flexibility to choose any and yet assess the candidate right.

Everyone is different. If your team is so same-wired and everyone prefers one and only one format over the others — in this case, feel free to choose it and use it for everyone else, if you think it solves your problem. If not — I suggest you come prepared beforehand and do your own homework. The result would not disappoint you and save your resources spent on yet another mishire.

## The scoring rubric. Same regardless of path

Whether a candidate submits a take-home or a portfolio, they are evaluated on the same skills table. The format is their choice. The standard is not.

| Skill                  | Take-home signal                                   | Portfolio signal                                              |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------------------- |
| SQL and data modeling  | Task output                                        | Schema design, query patterns in code                         |
| Debugging              | Task scenario                                      | Git history — what did they fix and how                       |
| Pipeline thinking      | Task design choices                                | Architecture decisions, PR descriptions                       |
| Data quality instincts | Did they flag edge cases?                          | Did they handle nulls, duplicates, schema drift?              |
| Tradeoffs              | Can they explain why                               | Can they explain why                                          |
| AI use                 | Session shared in follow-up                        | N/A — use follow-up conversation                              |
| Vector databases       | Task output — choice of storage, indexing strategy | Implementation in code, docs on similarity metrics used       |
| LLM integration        | Prompt structure, validation logic, error handling | How they call APIs, when they skip LLM, cost controls         |
| Embedding pipelines    | Chunking strategy, versioning, update logic        | Code handling document ingestion, reindexing, drift detection |
**On portfolio debugging evidence:** if the portfolio has no visible debugging, check the git history. If git history is private or absent, use the follow-up conversation to probe. Don’t assume the gap and verify it instead.

**AI does the first-pass portfolio review.** Use AI as an independent reviewer companion: read commits, map the portfolio against the skills table, flag gaps and strengths. This is not a replacement for the human call; it’s prep and assistance for it. The human interviewer comes in knowing where to probe without the need to start from scratch.

**One shared gap-filling interview.** After take-home or portfolio review, every candidate gets one common interview to fill gaps in the rubric. Same questions, same skills table. No side-quests based on curiosity. If a skill isn’t in the table, it’s not being assessed this round.

**Keep a transcript or notes from the interview.** The judgment-heavy part of the process needs to be auditable. If a hire goes wrong or a rejection gets challenged, “I had a feeling” doesn’t hold. Write it down.

**The interviewer holds final veto.** You’re hiring a human for a human team. AI-assisted review flags patterns, but it doesn’t make calls. If a candidate reads as robot-perfect — no rough edges, every answer polished, nothing surprising — that is itself a flag worth noting.

**If the interviewer reads real experience behind interview-pressure anxiety, flag as potential.** Freeze responses and blank moments under artificial stress are not the same as lack of skill. If the substance is there, be it in the take-home, in the system design, in how they respond when given a moment to think, reassess them. Hold them as a strong option pending a comparison candidate rather than rejecting on anxiety alone.

**If the pipeline is thin, hire.** If there’s a strong candidate and no one else credible in sight for roughly two weeks (N/A if you have months to fill the role), make the decision. A harder test or a longer wait doesn’t create better candidates. You already have the information you need.

**The take-home is reusable.** A completed assignment can later be shared by the candidate as portfolio material, with your permission and theirs. Make this explicit upfront. It removes one reason candidates hesitate to invest time.

**On comparing candidates:** compare two or three, then commit. If you have two strong candidates and keep looking, you’re not being rigorous; you’re stalling. Set the cap before you start.

# Your Homework

## Be honest about the mess

Your pipelines are not perfect. There are trade-offs that were made under pressure, schemas that were half-migrated, decisions that made sense at the time and don’t anymore. That’s how production works.

A senior engineer knows this. They’ve been there. They won’t be scared by it; they’ll get involved quicker.

Say it in the job description. Not “you’ll work on exciting data infrastructure challenges”, but something closer to: “you’ll inherit a system that has grown fast, has real technical debt, and will need someone who can work pragmatically through it while building something better.” This does two things. It filters out candidates who only want greenfield work, and those are the wrong hires for this role. And it attracts engineers who find untangling a real system genuinely interesting. Those are usually the better ones.

Hiding the mess costs you. The candidate discovers it in week two, wonders what else you weren’t honest about, and starts looking again. Or worse: they stay, resent it, and do the minimum.

Honesty about the state of the system is a hiring differentiator. Most companies won’t do it. The ones that do build better teams.

## Build a task bank

Once you have fewer, better candidates in the funnel, the assessment itself matters more.

**Have a ready-at-hand bank of tasks built from your actual problems.** Debug a broken pipeline. Find a memory leak. Explain why this query is slow. You’ve already seen them in production. Turn them into tasks. AI can help you generate them directly from your project board.

**Keep tasks under 3 hours.** Respect the candidate’s time. This is also a signal about your company culture: how you treat candidates is how you treat employees.

**Track how long it takes.** Ask every candidate directly: *“How long did this take you? Be honest — this won’t change our assessment of your skills. We want to keep our tasks reasonable, and we appreciate your time.”*

Track the distribution. If 80% of strong hires finish in 90 minutes and you’re advertising 3 hours, adjust. If someone takes 4 hours and produces excellent work, that’s a signal about their working style and tells nothing about their ability. The data is for you to optimise the process.

**Ask if they used AI.** Your goal here is not to penalise, but to understand. Use it as a conversation starter in the follow-up.

**Rotate the bank every 3-6 months.** Tasks circulate. They end up on Glassdoor and in candidate Discord servers. A bank means you always have a replacement ready.

**Scope tasks to the actual job.** A data platform engineer should debug a dbt model or design a schema; do not ask them to reverse a string. The task itself tells candidates what the job really is.

**On team time:** yes, reviewing a take-home costs someone an hour. But 1 hour reviewing once is cheaper than 3 rounds of interviews across multiple candidates, multiplied by interviewer time, plus 6 months of a bad hire’s salary and the cost of rehiring. If your team is genuinely looking for a great fit, spending that hour once or twice is worth it. Running hours of interviews that don’t show the actual skill is not.

Transparency about all of this (time expectations, AI policy, how you evaluate) is a differentiator itself. Most companies don’t say any of this out loud. Candidates remember the ones that do, and good candidates will be more prone to apply if they feel like it.

# P.S.: What we’re actually testing in the AI era

There is a skill that doesn’t show up in LeetCode at all: **context retention and navigational reasoning**.

Knowing not just how to solve a problem, but where it lives in the system. What it touches. What will break if you change it. Where to look when something goes wrong. How to reconstruct intent from code that was written by someone who no longer works there.

Leetcode hands you full context. Real engineering is actually the opposite: you’re given almost none, and your first job is to build it before you can even define the problem.

For a data platform engineer, for instance, this is arguably the most critical skill. A pipeline failure at 3am isn’t “here’s an array, find the intersection.” It’s “something is wrong somewhere in a system you didn’t fully build, affecting data you don’t fully understand, for stakeholders who are already angry.” The engineer who can hold that context, navigate to the right place, and not break three other things while fixing one — that’s exactly who you need.

A CS degree and hundreds of algorithmic problems don’t develop this skill. Production does.

Tools and knowledge are more accessible today than they have ever been. Expecting a candidate to recall a 50-year-old sorting algorithm from memory is not a proxy for engineering ability; it’s a proxy for exam performance.

Consider this: a candidate doesn’t know off the top of their head why a sort is behaving unexpectedly in ClickHouse. But they go to the documentation, find that the behaviour changed in a previous version, discover that the engine is actually MergeTree, which requires `FINAL` for consistent reads, and recommend partitioning the data beforehand to avoid the problem entirely.

That is the person you need.

Memorised knowledge is static. You need the ability to read documentation, understand context, and apply a specific fix to a specific system. That’s the engineer who solves problems you haven’t anticipated yet.

And it’s directly testable: give a candidate an unfamiliar error or an obscure system behaviour, let them research, and watch what they do. Do they find the right source? Do they understand what they read? Do they apply it correctly? That’s a stronger signal than whether they can recite an algorithm under pressure.

And if you still want to stick to your old pipelines, ask yourself: are you screening 200 candidates because your process is efficient, or because your process is a funnel that discards most of the signal early and hopes something good survives?

The pipeline problem isn't talent. It's that most hiring processes are optimised to filter, not to find.

---

AI usage disclosure: I used Claude Sonnet 4.5 to structure my thoughts into more readable material, to complement my opinions with external evidence, and to ask the model to run external research. Specifically, I asked the model to help me combine my thoughts and industry testimonies into structured pros vs cons tables. I also used Grammarly as an editorial tool to fix some typos and stylistic choices, since English is my second language.