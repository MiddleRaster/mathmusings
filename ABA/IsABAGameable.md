---
layout: default
title: Is the ABA Metric Gameable?
permalink: /ABA/IsABAGameable.html
---

# Is the ABA Metric Gameable?

## Introduction

I've been reading on the web and a lot of people confidently say that all metrics can be gamed.
Notably, when talking about flow metrics, such as cycle time, WIP and throughput, they claim that you could make yourself look good by slicing up the work into extremely small pieces.

And if your main metric is some kind of throughput, then that's certainly true.

But what about cycle time or lead time, and specifically, my favorite metric, the [average age of open bugs (ABA)](https://middleraster.github.io/ABA/TheMetricForSoftwareDevelopment.html)?

## Tiny Work Items

There are two different cases:

1. If you don't have WIP limits (Scrum) or they're set way too high (poorly done Kanban):
   
   From Little's Law, we have
   \\[Cycle\ Time = \frac{WIP}{Throughput}\\]
   
   Say someone slices up his stories 10x thinner.
   The WIP goes up by 10x and throughput goes up by 10x (if measured in items/day).
   The **cycle time doesn't change.**
   
2. If your WIP limits are all set to 1 (per worker):
      
   From Little's Law, with WIP = 1, we have
   \\[Cycle\ Time = \frac{1}{Throughput}\\]
   
   This time, if someone slices up his stories 10x thinner, his throughput goes up by 10x and the cycle time goes down by 10x.

   However, and this is the important bit, his **lead time** doesn't change.

   The difference between lead time and cycle time is where you draw the boundaries of the system:
   - in cycle time, the "ready backlog" is not included, while
   - in lead time, the "ready backlog" is included.


   So when he slices up his stories really fine, that must be done at the ready backlog level and he ends up with 10 times as many stories.
   But, 
   \\[Lead\ Time = \frac{WIP \cdot 10}{Throughput \cdot 10}\\]
   
   So again, the lead time is invariant.

Is it possible for him to slice up his stories later, after the ready backlog? Not per the Scrum Guide.

What about dysfunctional Scrum teams? Sure. But it doesn't matter because, from the PO's perspective, all she cares about is that the PBIs selected for this sprint are done.

What about Kanban teams? They are the ones actually measuring WIP, throughput and lead- and cycle-time.
      
In Kanban, splitting a work item is allowed only if it follows the team’s explicit workflow policies; nothing is forbidden by roles, but everything must be transparent, agreed upon, and consistent with WIP limits.
So if one person does it, it's with the knowledge of the rest, so they could all do it and any advantage disappears.

Another way of looking at it is that Kanban is all about flow, making things flow through the system smoothly and as quickly as possible ([cycle time, not throughput](https://middleraster.github.io/Kanban/KanbanThoughts.html)!).
In such a world, the Product Owner could measure the arrival rate, rather than throughput, and so splitting a story would be irrelevant.


## Is Average Bug Age Gameable?

Is ABA be similarly invariant to slicing?

First, it makes little sense to break a bug into multiple smaller bugs, but I suppose it's possible.

However, remember that we're not looking at the rate at which bugs are being completed (throughput), but rather we're looking at the average age of the remaining, **open** bugs.

You could split a bug all you want, but, assuming you have a "bugs-first" policy, then you work on the little pieces first and complete them.
The average age of the remaining open bugs is unchanged; that is, invariant.

What if you don't have a "bugs-first" policy?
Then those split bugs start aging and if you let them fester, the ABA will be worse than if you didn't split them.


## Summary

Ok, here's one way:  you write a tool that closes each bug, and re-opens a new one with the same text.

At *StupendousCorp*, only testers were actually allowed to close bugs; devs were only allowed to *resolve* bugs.
Using such a tool means getting the testers in cahoots (which is unlikely) and is easily detectable (as in, "Hey, how come all our bugs were opened yesterday?"). 


I haven't found a good way to game ABA, but that doesn't mean it's impossible; it only means I haven't found a way yet.

Still, I would be extremely leery of using ABA as a metric to measure devs against each other, though I do think it's appropriate to measure dev teams/groups/orgs/divisions against each other this way.
