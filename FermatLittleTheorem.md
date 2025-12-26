---
layout: default
title: Fermat's Little Theorem
---

In 1640, Pierre de Fermat wrote, without proof, that, if \\(p\\) is prime and coprime with \\(a\\), then 
\\[
a^{p-1} \equiv 1\pmod{p}.        \tag{1}.
\\]

Let's prove it, using only tools that Fermat could have known about: in our case, induction and the binomial theorem.

For the first step, let's multiply through by \\(a\\), giving
\\[
a^p \equiv a\pmod{p}.
\\]

For our proof by induction, we'll need a base case.  Here are two:

\\(0^p \equiv 0\pmod{p}\\) and \\(1^p \equiv 1\pmod{p}\\).

Next, we must show that if the theorem is true for some \\(k\\), that is, \\(a = k\\), then it is also true for \\(a = k + 1\\). So we must show that, given 
\\[
k^p \equiv k\pmod{p}        \tag{2},
\\]
then
\\[
(k + 1)^p \equiv k + 1\pmod{p}
\\]
is also true.

Applying the binomial theorem to the left side, we get:
\\[
(k+1)^p = \sum_{j=0}^{p} \binom{p}{j} k^{\,j} =  \binom{p}{0}k^{0} + \binom{p}{1}k^{1} + \binom{p}{2}k^{2} + \cdots + \binom{p}{p-1}k^{p-1} + \binom{p}{p}k^{p}.
\\]

Now, each binomial coefficent is of the form \\[\frac{p!}{j!(p-j)!}\\] for all \\(0<j<p\\).

Note that when \\(j=0\\) or \\(j=p\\), the binomial coefficient is 1. For all other values between \\(1\\) and \\(p-1\\) we have the prime \\(p\\) in the numerator.
All the elements of the factorials in the denominator are smaller than the prime \\(p\\), so after all the divisions are done, there's still a non-zero multiple of \\(p\\) left in the numerator. 
(As a side note, these are exactly the numbers in the \\(p\\)th row of [Pascal's Triangle](https://en.wikipedia.org/wiki/Pascal%27s_triangle).) Therefore, we have:

\\[
(k+1)^p = 1 + a_{1}\,p\,k + a_{2}\,p\,k^{2} + a_{3}\,p\,k^{3} + \cdots + a_{p-1}\,p\,k^{\,p-1} + k^{p}.
\\]

Since all the middle terms are divisible by \\(p\\) (that is, \\(\equiv 0\pmod{p}\\)), we have remaining:
\\[
(k + 1)^p \equiv 1 + k^p\pmod{p}.
\\]

The final step is to apply our induction hypothesis:  from eq 3, we can replace \\(k^p\\) with \\(k\\), leaving:
\\[
(k + 1)^p \equiv k + 1\pmod{p}.
\\]
which is exactly what we were trying to prove.

Therefore, \\(a^p \equiv a\pmod{p}\\).

Finally, to get to Fermat's exact version (eq 1), we merely divide by \\(a\\), but note that this is only possible if \\(a\\) is invertible; that is, if \\(a \not\equiv 0 \pmod{p}\\),
which is the same as saying \\(a\\) is coprime with \\(p\\). And when that is true, we have Fermat's Little Theorem: 

if \\(p\\) is prime and coprime with \\(a\\), then
\\[
a^{p-1} \equiv 1\pmod{p}.
\\]
