---
title: Improve your product with Operational Excellence Meetings
description: How we use on-call rotations and a weekly meeting to make the product better.
tags: 
    - DevOps
    - Engineering
    - Product
layout: 'blog-post.njk'
date: 2023-10-29
---

### The 2 AM Alert Problem

So I really don't like being on-call. In fact, nobody likes being on-call in software engineering. And nobody likes being woken up late at night to fix something. For over a year though my team has used the on-call rotation to nearly eliminate alerts, how did we do this? By implementing an Operational Excellence meeting every week. This has greatly improved our process and has enhanced our product. We even go weeks without ever getting a single alert!
  
The Operational Excellence meeting is run every week to go over alerts that have happened. The on-call person for that last week runs the meeting and explains anything they went through and observations they made. Importantly, we discuss what solutions would prevent these alerts from happening in the first place and we prioritize that work.

The feedback loop is immediate and impactful. No one wants to get paged at 2 AM, especially not myself. Making the goal of “let’s not get paged for this again” is very motivating. Engineers share the burden of on-call and are incentivized to fix problems they and their colleagues might have to face again in the future. This aspect of social accountability is very powerful and helps to keep the team motivated and seek more experience in problem areas.

The most important aspect of this meeting is prioritizing the work. New features may be important to the business, but what could be more important than keeping your product working? Incentivizing no downtime over other big new features will pay huge dividends in keeping both customers and engineers happy. We even found that analyzing errors and alerts can lead to new features that make the product better, like discovering a slew of errors coming from a critical part of the workflow: maybe we can re-design this a part of the app to prevent these errors from happening in the first place.

### How to run an Ops Excellence meeting

First, I think one of the most important parts of this is to make sure that *everyone* is accountable in the team, not just DevOps engineers. Everyone should be on-call, and everyone should be responsible for fixing problems. This is a great way to cross-train and make sure that everyone is familiar with the codebase. It also helps to make sure that everyone is invested in the product and its success.

Second, the meeting should be run by the on-call person for the previous week. This person should be responsible for taking notes and making sure that the meeting is run efficiently. This person should also be responsible for making sure that new work is prioritized and that the team is on the same page about what needs to be done. Obviously a manager needs to be present to make sure work gets on the board and assigned, but the on-call person should be the one to make sure that the work is understood and prioritized during the meeting.

We spend the first 10 minutes or so reviewing an incidents that occurred over the last week. The on-call person should keep a list of an incidents they ran into. Your on-call incident tracker like PagerDuty can provide a simple list here, but I think it helps to write up a document for each meeting with things the on-call person ran into. Maybe they had to restart a server, or maybe they had to fix a bug in the code. Whatever it is, it should be written down and discussed. This is a great time to ask questions and get feedback from the team. It's also a great time for the upcoming on-call person to ask for help if they're not sure how to fix something.

Next, we have a monitoring dashboard that we look over, timeboxed to 10 minutes. This part tends to get a little in the weeds, so the timebox is important. The basic idea is pour over a week's worth of output from your services and look for any anomalies, spikes in graphs, sudden unexpected drops, that sort of thing. If someone sees something that looks out of the ordinary, you pause to look into it and record and observations.

This is a good time to reflect on improvements to the dashboard and I like to encourage comments like "we should really log that" or "could we also include this stat somewhere?" Expanding and improving the dashboard should be a function of the Operational Excellence meeting and with time you should have a dashboard that effectively communicates what you need to know at any given time in the system. This is also a good time to reflect on the dashboard itself and make sure that it's not too noisy. If you're getting alerts all the time, maybe you need to re-think what you're monitoring.

We spend the last 10 minutes or so discussing any new work that needs to be done. This is a great time to discuss any new features that need to be added to the dashboard, any new work that needs to be done to prevent alerts from happening again, or any new features that might be coming down the pipeline and how they might affect the system as a whole. Engineers should feel like this is an open forum where their ideas are heard and they can contribute to the service in a meaningful way.

Finally, we like to make sure that any new action items that came out of the meeting are assigned and prioritized. In the past I've noticed that this could be one of the easiest places for things to slip, so a manager should be present and give engineers permission to drop certain other tasks in favor of fixing something that's broken.

### The Results

In one instance of this meeting, we found that there were extremely long round-trip times occuring on certain requests. The Ops Excellence meeting exposed this problem by reviewing the dashboard, but we also dug into the problem a little, discovering that a handful of services were sending data requests to adjacent services, only for those services to make requests back to the original service for information that was already collected at the beginning of the request! We were able to fix this hop-around of requests and greatly improve the overall response rate.

In leading this meeting I've often found that people present who know about certain areas of the code want to make improvements. Letting them take ownership of that area and make it better is a pretty obvious improvement. But the real opportunity lies in creating spaces for one subject matter expert to oversee a fix with someone who doesn't. I feel like Ops Excellence is a great cross-training opportunity in that sense. Taking on areas that are unfamiliar may be slow at first, but over time it creates better expertise and more confidence in the team overall.

If Ops Excellence is done well, the alerts begin to stop, engineers are less afraid to be on-call, customers are happier, and the whole organization is more confident in the product. I couldn't see a better way to spend a half hour or so a week.
