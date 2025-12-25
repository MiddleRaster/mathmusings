---
layout: default
title: Fermat's Little Theorem
---

In 1640, Pierre de Fermat wrote, without proof, that, if \\(p\\) is prime and coprime with \\(a\\), then 
\\[
a^{p-1} \equiv 1 \pmod{p}.
\\]

Let's prove it, using only tools that Fermat could have used:  induction and the binomial theorem.

For the first step, let's multiply through by \\(p\\), giving
\\[
a^p \equiv p \pmod{p}.
\\]

For our proof by induction, we'll need a base case. Here are two:  \\(0^p \equiv 0 \pmod{p}) and \\(1^p \equiv 1 \pmod{p}).
Next, we must show that if the theorem is true for \\(a = k\\), then it is also true for \\(a = k + 1\\).


