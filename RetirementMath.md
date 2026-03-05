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

where  
\\(P_n\\) is the \\(n\text{th}\\) year's principal at year \\(n\\),  
\\(P_0\\) is the initial principal at time 0,  
\\(W\\) is the initial withdrawal which grows to keep up with inflation,  
\\(y\\) is the yield ***ratio*** (e.g., 1.09 (9%)), and  
\\(i\\) is the inflation ***ratio*** (e.g., 1.0325 (3.25%)).  

Here's the derivation:  

\\[
P_1 = (P_0 - W) \cdot y
\\]
\\[
P_2 = (P_1 - W \cdot i) \cdot y
\\]
\\[
P_3 = (P_2 - W \cdot i^2) \cdot y
\\]
\\[
etc.
\\]

Substituting the first equation into the second gives:
\\[
P_2 = ((P_0 - W) \cdot y - W \cdot i) \cdot y
\\]














