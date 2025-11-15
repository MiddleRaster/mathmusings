---
layout: default
title: The Integral of One Over X
---

If you've ever taken a first year calculus class, after learning how to integrate polynomials, the next thing you learn is how to integrate \\(1/x.\\)

Now, usually, the teacher just tells you that the answer is \\(\ln(x)\\) without proof. And further, most proofs online use the fact that the inverse function of \\(\ln(x)\\) is \\(e^x\\), again without proof.

This will not do.

Let's prove 
\\[
\int \frac{1}{x} \, dx = \ln|x| 
\\]
from scratch, the way it was done historically. And for that we need to go all the way back to John Napier and his wonderful invention of logarithms in 1614.


### **Step 1: Napier's Logarithm**

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

Compare with \\(Nap(m+n)\\):

\\[
Nap(m+n) = 10^{7}\cdot 10^{7}(1 - \frac{1}{10^{7}})^{m+n}.
\\]

So we have the relation:
\\[
Nap(m)\cdot Nap(n) = 10^{7}\cdot Nap(m+n)
\\]
which looks kind of like a logarithm, but has this extra scaling factor in it. But nevertheless, it's a logarithm of sorts.
<br><br>


### **Step 2: Saint-Vincent's contribution**

In 1647, Gregoire de Saint-Vincent showed that the areas under the curve \\(y = 1/x\\) have additive properties, though he didn't make the connection with logarithms.
Let's prove his result, but in modern terms ('cuz I don't want to schlep through his geometric proof by similarities).

For \\(x>0\\), define the area under the curve \\(y=\frac{1}{t}\\) from \\(t=1\\) to \\(t=x\\) by
\\[
A(x)=\int_{1}^{x}\frac{1}{t}\,dt.
\\]

Then, for the area of a product \\(ab\\), for \(a>0\) and \(b>0\), the area associated with that product is
\\[
A(ab)=\int_{1}^{ab}\frac{1}{t}\,dt.
\\]

Now, split the area at some \\(a\\) from the interval \\([1,ab]\\):

\\[
A(ab)=\int_{1}^{a}\frac{1}{t}\,dt\;+\;\int_{a}^{ab}\frac{1}{t}\,dt.    \tag{1}
\\]

Do a substitution on the second part. In the second integral, set \\(t=a \cdot u\\). Then \\(dt=a\,du\\), and the limits transform as \\(t=a\mapsto u=1\\), \\(t=ab\mapsto u=b\\).
\\[
\int_{a}^{ab}\frac{1}{t}\,dt=\int_{1}^{b}\frac{1}{a\,u}\cdot a\,du=\int_{1}^{b}\frac{1}{u}\,du = A(b).
\\]

The first integral in (1) is \\(A(a)\\), and the transformed second integral is \\(A(b)\\).

Conclusion:  The area function \\(A\\) converts products of abscissas into sums of areas:
\\[A(ab)=A(a)+A(b).\\]
<br><br>


### **Step 3: Sarasa's contribution**

Two years later, Alphonse Antonio de Sarasa, in 1649, made the connection between Napier's work and Saint-Vincent's work. In his *Solutio problematis a R.P. Marino Mersenne Minimo propositi*, he stated, "these areas can fill the place of the given logarithms." He said "fill the place" because of that funky \\(10^7\\) scaling factor of Napier's. But now we've got true logarithms, without any scaling nonsense.
<br><br>


### **Step 4: Bernoulli's contribution**
Ok, we've shown that \\(\int \frac{1}{x} \, dx \\) is some kind of logarithm, but which one? What's the base?

In 1683, Jakob Bernoulli was studying compound interest. In particular, he was looking at what happens when you compound more and more frequently.
For example, if you have $1 and you are getting 100% interest compounded annually, then after a year, you have $2.

But, if you get 50% interest compounded semiannually (twice a year), you end up with $2.25 after a year. 
Similarly, you get approximately $2.44 when it's compounded quarterly, $2.61 for monthly, and $2.71 for daily.

The general formula is
\\[
\left(1 + \frac{1}{n}\right)^n    \tag{2}
\\]

And Bernoulli realized that when n approaches infinity, that formula approaches a limit. We now call it \\(e.\\)

That's great, but that formula only works for an interest rate of 100%. What about other rates?  Take formula (2) and perform a subsitution (for fixed r):
\\[
n = \frac{m}{r}
\\]

Substituting into (2) gives:
\\[
e \;=\; \lim_{m \to \infty} \left(1 + \frac{1}{\,m/r\,}\right)^{\,m/r\,}
     \;=\; \lim_{m \to \infty} \left(1 + \frac{r}{m}\right)^{\,m/r\,}
\\]

Raising both sides to the power of r:
\\[
e^{r}
= \left( \lim_{m \to \infty} \left(1 + \frac{r}{m}\right)^{\,m/r} \right)^{r}
= \lim_{m \to \infty} \left[ \left(1 + \frac{r}{m}\right)^{\,m/r} \right]^{r}
= \lim_{m \to \infty} \left(1 + \frac{r}{m}\right)^{m}.
\\]

Renaming m back to n results in our final formula:
\\[
\lim_{n \to \infty} \left(1 + \frac{r}{n}\right)^n = e^{r}                \tag{3}
\\]


### **Step 5: Euler's contribution**
Euler took the Bernoulli equation and set \\(n = 1/x\\), giving
\\[
e = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^{n}
   = \lim_{x \to 0^{+}} (1+x)^{\,1/x}
\\]

Now, you can **define** an inverse of any logarithm, whatever the base, let's call it \\(InverseOfLogBaseB,\\) such that

\\[
InverseLogBaseB(LogBaseB(x)) = x,
\\]

and

\\[
LogBaseB(InverseLogBaseB(x)) = x.
\\]

From normal logarithm rules, including our LogBaseB, we know it's an additive function, so we can say
\\[LogBaseB(a^n) = n*LogBaseB(a).\\] 
This works for rational powers, too (say, q), not just integer values of n.

So, 
\\[
a^q = InverseOfLogBaseB(q*LogBaseB(a)).
\\]

Now pick \\(a = 1+x\\), and \\(q = 1/x\\), and we get
\\[
(1+x)^{\tfrac{1}{x}} = InverseOfLogBaseB((LogBaseB(1 + x) / x).                  \tag{4}
\\]

Now, let's switch gears and look into the area under the curve 1/x starting at 1 and going to 1+x.
We can find an overly large rectangle that encoumpasses the whole thing; it's rectangle from by upper-left point \\((1,1)\\)
and the lower-right point is \\((1+x,0).\\)
We can also find a too small rectangle by using the other end of the 1/x curve; 
it's the rectangle from the upper-right point \\((1+x, 1/(1+x))\\) and the lower-left point \\((1,0).\\)
The real area of the curve will be between these two. In other words, the area of the bigger rectangle is:
\\[
(1-0)*(1+x-1) = x
\\]

And the area of the smaller rectangle is:
\\[
(1+x-1)*(1/(1+x)-0) = x/(1+x).
\\]

So we have:
\\[
x/(1+x) <= LogBaseB(1+x) <= x.
\\]
Dividing by x gives:
\\[
1/(1+x) <= LogBaseB(1+x)/x <= 1.
\\]
Now, letting x approach 0 means that both the right and left sides approach 1, 
so by the squeeze theorem, \\[LogBaseB(1+x)/x = 1.\\]

Finally, from Bernoulli's equation with \\(n=1/x,\\) we have \\[\lim_{x \to 0} (1+x)^{\tfrac{1}{x}} = e.\\]
We also showed that \\(LogBaseB(1+x)/x\\) is exactly \\(1.\\) Plugging both of those facts into equation 4, gives:
\\[
e = InverseOfLogBaseB(1). 
\\]
So the base B is \\(e.\\) 

And that means that 
\\[
InverseOfLogBaseB(x) = e^x
\\] and 
\\[
LogBaseB(x) = ln(x).
\\]
And that completes our proof that the area under the curve \\(1/x\\) is indeed \\(ln(x).\\)
