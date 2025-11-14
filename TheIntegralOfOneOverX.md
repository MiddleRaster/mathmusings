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


### Step 1: Napier's Logarithm

What Napier did was discover what he called a wonderful method of multiplying two numbers together by two table lookups, addding those, and then a final table lookup. 
Old people, such as myself, recognize this as using logarithm tables (and slightly less old people might recognize it as similar to how a sliderule works). 
Of course, he didn't call it that. Instead, let's call it \\(\mathrm{Nap}(x)\\) .

Here's what he did: he started with a really big number, 10,000,000 and repeatedly multiplied it by 9,999,999/10,000,000. Why did he pick these big numbers? 
Because the decimal point hadn't come into common use yet. He didn't want to work with fractions, so he scaled everything up by 10 million, which he figured was good enough.
In modern notation, we have for any integers \\(\(m,n\):\\)
\\[
Nap(m) = 10^{7}(1 - \frac{1}{10^{7}})^m, \quad
Nap(n) = 10^{7}(1 - \frac{1}{10^{7}})^n.
\\]

Multiply them:

\\[
Nap(m)\cdot Nap(n) = [10^{7}(1 - \frac{1}{10^{7}})^m]\cdot [10^{7}(1 - \frac{1}{10^{7}})^n].
\\]

Simplify:

\\[
Nap(m)\cdot Nap(n) = 10^{14}(1 - \frac{1}{10^{7}})^{m+n}.
\\]

Compare with \(N(m+n)\):

\\[
Nap(m+n) = 10^{7}(1 - \frac{1}{10^{7}})^{m+n}.
\\]

So we have the relation:
\\[
Nap(m)\cdot Nap(n) = 10^{7}\cdot Nap(m+n)
\\]
which looks kind of like a logarithm, but has this extra scaling factor in it. But nevertheless, it's a logarithm of sorts.
<br><br>

### Step 2: Saint-Vincent's contribution
In 1647, Gregoire de Saint-Vincent showed that the areas under the curve \\(y = 1/x\\) has additive properties, though he didn't make the connection with logarithms.
Let's prove his result, but in modern terms ('cuz I don't want to schlep through his geometric proof by similarities).

For \\(x>0\\), define the area under the curve \\(y=\frac{1}{t}\\) from \\(t=1\\) to \\(t=x\\) by
\\[
A(x):=\int_{1}^{x}\frac{1}{t}\,dt.
\\]

Then, for the area of a product \\(ab\\), for \(a>0\) and \(b>0\), the area associated with that product is
\\(
A(ab):=\int_{1}^{ab}\frac{1}{t}\,dt.
\\)

Now, split the area at \\(a\\):\\([1,ab]\\) at \\(a\\):
\\(
A(ab)=\int_{1}^{a}\frac{1}{t}\,dt\;+\;\int_{a}^{ab}\frac{1}{t}\,dt
\\).

Do a substitution on the second part. In the second integral, set \\(t=a \cdot u\\). Then \\(dt=a\,du\\), and the limits transform as \\(t=a\mapsto u=1\\), \\(t=ab\mapsto u=b\\).
\\(
\int_{a}^{ab}\frac{1}{t}\,dt=\int_{1}^{b}\frac{1}{a\,u}\cdot a\,du=\int_{1}^{b}\frac{1}{u}\,du.
\\)

The first integral is \\(A(a)\\), and the transformed second integral is \\(A(b)\\):  A(ab)=A(a)+A(b).

Conclusion:  The area function \\(A\\) converts products of abscissas into sums of areas:A(ab)=A(a)+A(b),\\(\quad a>0,\;b>0))\.
<br><br>






### Step 3: Sarasa's contribution

Alphonse Antonio de Sarasa, in 



















