---
layout: post
title:  "Something about dice."
date:   2016-06-01 00:00:01 +0800
author: Mark N
categories:
---


Thought this was interesting.

**A fair 6-sided die is rolled consecutively until the cumulative value of all rolls is at least 6. What is the expected number of rolls required?**

Let $$f(x)$$ denote the expected number of rolls required to obtain at least $$6$$ with initial value $$x$$. Then:

$$
\begin{aligned}
f(6) &= 0 \\
f(5) &= 1 \\
f(4) &= 1 + \frac{1}{6}f(5) = \frac{7}{6} \\
f(3) &= 1 + \frac{1}{6}f(4) + \frac{1}{6}f(5) = \frac{49}{36}\\
f(2) &= 1 + \frac{1}{6}f(3) + \frac{1}{6}f(4) + \frac{1}{6}f(5) = \frac{343}{216}\\
f(1) &= 1 + \frac{1}{6}f(2) + \frac{1}{6}f(3) + \frac{1}{6}f(4) + \frac{1}{6}f(5) = \frac{2409}{1296}\\
f(0) &= 1 + \frac{1}{6}f(1)+ \frac{1}{6}f(2) + \frac{1}{6}f(3) + \frac{1}{6}f(4) + \frac{1}{6}f(5) = \frac{638}{316}
\end{aligned}
$$

So the expected number of rolls required is  $$ \frac{638}{316} \approx 2.16 $$.

**A fair n-sided die is rolled consecutively until the cumulative value of all rolls is at least n. What is the expected number of rolls required?**

Adopting similar notation as above:

$$ 
\begin{aligned}
f(n) &= 0 \\
f(n-1) &= 1 \\
f(n-2) &= 1 + \frac{1}{n}f(n-1) \\
f(n-3) &= 1 + \frac{1}{n}f(n-2) + \frac{1}{n}f(n-1) \\
\vdots & \\
f(1) &= 1 + \frac{1}{n}f(2) + \frac{1}{n}f(3) + \cdots \frac{1}{n}f(n-2) + \frac{1}{n}f(n-1)\\
f(0) &= 1 + \frac{1}{n}f(1)+ \frac{1}{n}f(2) + \frac{1}{n}f(3) +\cdots \frac{1}{n}f(n-2) + \frac{1}{n}f(n-1)\\
\end{aligned}
$$

Appropriate substitution gives

$$f(0) = f(n-1) (1 + \frac{1}{n})^{n-1} = (1 + \frac{1}{n})^{n-1}$$.

Take the limit as $$n \to \infty$$,

$$\lim_{n\to\infty} (1 + \frac{1}{n})^{n-1} = e \approx 2.71828$$.

Also, monotonicity gives a nice upper bound for all expectations (i.e. let $$\mathbf{E} T_{n}$$ denote the expectation for an $$n$$-sided die, then $$\mathbf{E} T_{n} \leq e$$ for all $$n \in \mathbb{N}$$).