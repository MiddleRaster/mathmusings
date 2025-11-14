---
layout: default
title: The Inegral of One Over X
---

If you've ever taken a first year calculus class, after learning how to integrate polynomials, the next thing you learn is how to integrate \\(1/x.\\)

Now, usually, the teacher just tells you that the answer is \\(\ln(x)\\) without proof. And further, most proofs online use the fact that the inverse function of \\(\ln(x)\\) is \\(e^x\\), again without proof.

This will not do.

Let's prove 
\\[
\int \frac{1}{x} \, dx = \ln|x| 
\\] from scratch, the way it was done historically. And for that we need to go all the way back to John Napier and his wonderful invention of logarithms in 1614.


What Napier did was discover what he called a wonderful method of multiplying two numbers together by two table lookups, addding those, and then a final table lookup. 
Old people, such as myself, recognize this as using logarithm tables (and slightly less old people might recognize it as similar to how a sliderule works). 
Of course, he didn't call it that. Instead, let's call it Nap(x) or 
 \\[
\mathrm{Nap}(x)
\\] 
Here's what he did: he started with a really big number, 10,000,000 and repeatedly multiplied it by 9,999,999/10,000,000. Why did he pick these big numbers? 
Because the decimal point hadn't come into common use yet. He didn't want to work with fractions, so he scaled everything up by 10 million, which he figured was good enough.
In modern notation, we have for any integers \\(\(m,n\):\\)
\\[
N(m) = 10^{7}(1 - \frac{1}{10^{7}})^m, \quad
N(n) = 10^{7}(1 - \frac{1}{10^{7}})^n.
\\]

