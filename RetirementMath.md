---
layout: default
title: Retirement Math
---

# Retirement Math

When I retired, the first thing I did was search on the web for a formula that would
- tell me how much I could withdraw from my retirement accounts, such that
- each year, I want the withdrawal to be larger to keep up with inflation, 
- assuming that the inflation rate and my accounts' yield rate are constant.

After a bunch of fruitless search, I decided to derive the equation myself.  Here it is:

\\[
P_n = P_0 \cdot y^n - W\cdot y^n \cdot \frac{1 - \left(\frac{i}{y}\right)^n}{1 - \frac{i}{y}} 
\\]

