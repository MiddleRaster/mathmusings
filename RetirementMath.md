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

Turns out this is called **the Formula for a Growth Annuity**.

## Derivation
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
P_n = P_0 y^n - W y \left( \frac{1 - \left(\frac{i}{y}\right)^n}{1 - \frac{i}{y}}\, y^{n-1} \right)
\\]
or
\\[
P_n = P_0 y^n - W y^n \left( \frac{1 - \left(\frac{i}{y}\right)^n}{1 - \frac{i}{y}}\\right)        \tag{1}
\\]

(And yes, I know I can factor out a \\(y^n\\).)

## Uses

Now, using equation (1), we can calculate when we’ll run out of money, for given yield and inflation rates and a withdrawal that keeps up with inflation.

Setting \\(P_n=0\\) and solving for \\(n\\), yields
\\[
n = \frac{\ln\left( 1 - \displaystyle\frac{p_0}{w}\,(1 - i/y) \right)}{\ln\left(\frac{i}{y}\right)}
\\]

So, for example, if we want to live off of $100,000 per year and have $1,000,000, and we assume that the rate of inflation is 3.25% and that the yield of the S&P 500 will average out to 9%, then 
\\[
n = \frac{\ln\left( 1 - \displaystyle\frac{1000000}{100000}\,(1 - 1.0325/1.09) \right)}{\ln\left(\frac{1.0325}{1.09}\right)}
\\]

or n = 13.8 years.


Alternatively, we might want to know how much we can withdraw so that the balance ***never*** reaches 0. Setting n to infinity and noting that the denominator is negative (since the inflation rate is less than the yield rate), we have:

\\[
-∞= \ln\left( 1 - \displaystyle\frac{p_0}{w}\,(1 - i/y) \right)
\\]

So, 
\\[
0 = 1 - P_0/W (1- i/y)
\\]

Or, 
\\[
W= P_0 (1- i/y)
\\]

Using our example numbers, above, shows that we can withdraw up to $52,752.29 (inflation-adjusted) per year and we’ll never run out of money.  
 






