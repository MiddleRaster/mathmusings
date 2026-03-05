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
P_1 = (P_0 - W)y
\\]
\\[
P_2 = (P_1 - Wi)y
\\]
\\[
P_3 = (P_2 - Wi^2)y
\\]
\\[
etc.
\\]

Substituting the first equation into the second gives
\\[
P_2 = ((P_0 - W)y - Wi)y
\\]

and then simplifying yields
\\[
P_2 = P_0y^2 -Wy(y+i).
\\]

Substituting this into the third equation above gives
\\[
P_3 = (P_0y^2 - Wy(y+i) - Wi^2)y
\\]

which simplifies to
\\[
P_3 = P_0y^3 - Wy(y^2 + iy + i^2).
\\]

After a few more rounds, the general pattern becomes obvious
\\[
P_n = P_0y^n - Wy(y^{n-1} + y^{n-2} i + \cdots + y^{1} i^{n-2} + i^{n-1}).
\\]

The part inside the parentheses is a geometric series and, if \\(\lvert i/y \rvert < 1\\) (i.e., that inflation is less than the yyield), can be written

\\[
P_n = P_0y^n - Wy( \frac{1 - \left(\frac{i}{y}\right)^n}{1 - \frac{i}{y}}y^{n-1})
\\]




