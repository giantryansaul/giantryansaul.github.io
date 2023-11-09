---
title: Improving your Product and Team with Operational Excellence Meetings
description: How we use on-call rotations and a weekly meeting to make our product better.
tags: post, DevOps, Engineering, Product
layout: 'blog-post.njk'
date: 2023-10-29
---
Nobody likes being on-call in software engineering. And nobody likes being woken up late at night to fix something. But for over a year my team has used the on-call rotation to make our product better and even go weeks without ever getting an alert!  
  
At my current job, we use an Operational Excellence meeting every week to go over alerts that have happened. The on-call person for that last week runs the meeting and explains anything they went through and observations they made. Importantly, we discuss what solutions would prevent these alerts from happening in the future and prioritize the work.

The feedback loop is immediate and impactful. No one wants to get paged at 2 AM, especially not myself. Making the goal of “let’s not get paged for this again” is very motivating. Engineers share the burden of on-call and are incentivized to fix problems they and their colleagues might have to face again in the future. This aspect of social accountability is very powerful and helps to keep the team motivated and seeking more experience in problem areas.

The most important aspect of this meeting is prioritizing the work. New features may be important to the business, but what could be more important than your product working? Incentivizing no downtime over other big new features will pay huge dividends in keeping both your customers and engineers happy. We have even found that analyzing errors and alerts can lead to new features that make the product better, like discovering a slew of errors coming from a critical part of the workflow: maybe we can re-design this a part of the app better to prevent these errors from happening in the first place.

In one scenario, we found that there were extremely long round-trip times occuring on certain requests. The Ops Excellence meeting exposed this problem, but during one of these meetings we sat down and dug into the problem a little, discovering that a handful of requests were sending data requests to adjacent services, only for those services to make requests back to the main service for information that was already collected at the beginning of the request! We were able to fix this hop-around of requests and greatly improve the overall response rate.

In leading this meeting I've often found that people present who know about certain areas of the code want to make improvements. This is a great opportunity to let them take ownership of that area and make it better. But the real opportunity lies in creating spaces for one subject matter expert to oversee a fix with someone who doesn't. I feel like Ops Excellence is a great cross-training opportunity in that sense. Taking on areas that are unfamiliar may be slow at first, but over time it creates better expertise and more confidence in the team overall.

If Ops Excellence is done well, the alerts begin to stop, engineers are less afraid to be on-call, customers are happier, and the whole organization is more confident in the product. I couldn't see a better way to spend an hour a week.
