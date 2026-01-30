---
layout: default
title: Is the ABA Metric Gameable?
permalink: /ABA/IsABAGameable.html
---

# Is the ABA Metric Gameable?

## Introduction

I've been reading on the web and a lot of people blithely say that all metrics can be gamed.
Notably, when talking about flow metrics, such as cycle time, WIP and throughput, they claim that you could make yourself look good by slicing up the work into extremely small pieces.

And certainly, if your main metric is some kind of throughput, then that's certainly true.

But what about cycle time or lead time, and specifically, my favorite metric, the average age of open bugs (ABA)?

## Tiny Work Items

There are two different cases:

1. If you don't have WIP limits or they're set way too high
   
   From Little's Law, we have
   \\[Cycle\ Time = \frac{WIP}{Throughput}\\]
   
   Say someone slices up his stories 10x thinner.
   The WIP goes up by 10x and the Throughput goes up by 10x.
   The **cycle time doesn't change.**
   
2. If your WIP limits are all set to 1 (per worker)
      
   From Little's Law, with WIP = 1, we have
   \\[Cycle\ Time = \frac{1}{Throughput}\\]
   
   This time, if someone slices up his stories 10x thinner, his throughput goes up by 10x and the cycle time goes down by 10x.

   However, and this is the important bit, his **lead time** doesn't change.

   The difference between lead time and cycle time is where you draw the boundaries of the system:
   - in cycle time, the "ready backlog" is not included, while
   - in lead time, the "ready backlog" is included.

   So when he slices up his stories really fine, that must be done at the ready backlog level and he ends up with 10 times as many stories.
   But, 
   \\[Lead\ Time = \frac{WIP*10}{Throughput*10}\\]
   
   So the lead time is invariant.

   Is it possible for him to slice up his stories later? Not per the Scrum Guide.

   What about dysfunctional Scrum teams? Sure. But it doesn't matter because, from the PO's perspective, all she cares about is that the PBIs selected for this sprint are done.

   What about Kanban teams? These are the ones actually measuring lead- and cycle-time, WIP and throughput and then the invariant from Little's Law kicks in.
   
## Is Average Bug Age Gameable?

