---
layout: post
title:  "Products of uniform random variables."
date:   2016-06-01 00:12:02 +0800
author: Mark N
categories:
---

**What is the density of the product of two i.i.d. uniform random variables $$X, Y \sim \mathcal{U}(0,1)$$?**

Let $$F_{Z}$$ and $$f_{Z}$$ denote the distribution and density of $$Z = XY$$ respectively. Then

$$ 
\begin{aligned}
F_{Z}(z) & = \mathbf{P}(Z \leq z) \\
& = \mathbf{P}(X \leq z , Y \in [0,1] ) + \mathbf{P}(X > z, Y \leq z/X) \\
& = \int_{0}^{z} \int_{0}^{1} \,dy \,dx + \int_{z}^{1} \int_{0}^{z/x} \,dy \,dx \\
& = z - z \ln z \\
\implies f_{Z} (z) 
& = \dfrac{d}{dz} (z - z \ln z) \\
& = -\ln z.
\end{aligned} 
$$

**What is the density of the product of $$n$$ i.i.d. uniform random variables $$X_{1}, \dots,X_{n} \sim \mathcal{U}(0,1)$$?**

*Claim:* The density is given by $$ f_{Z_{n}} (z) = \frac{ (- \ln z )^{n-1} }{(n-1)!}$$, where $$Z_{n} = \prod_{i=1}^{n}X_{i}$$.

*Proof.* Apply induction. When $$n = 1$$ the statement is true. Therefore, suppose it is true for some $$ n \in \mathbb{N} $$. Let $$Y = X_{1} \cdots X_{n}$$, then $$f_{Y}(y) = \frac{(-\ln y)^{n-1}}{(n-1)!} $$. By considering $$Z_{n+1} = X_{1} \cdots X_{n}X_{n+1} = Y X_{n+1}$$, this implies

$$
\begin{aligned}
F_{Z_{n+1}}(z) & = \mathbf{P}( Z_{n+1} \leq z ) \\
& = \mathbf{P}( Y \leq z , X_{n+1} \in [0,1] ) + \mathbf{P}( Y > z , X_{n+1} < z/Y ) \\
& = \int_{0}^{z} \int_{0}^{1} \frac{(- \ln y)^{n-1}}{(n-1)!} \,dx_{n+1} \,dy + \int_{z}^{1} \int_{0}^{z/y} \frac{(- \ln y)^{n-1}}{(n-1)!} \,dx_{n+1} \,dy \\
& = \int_{0}^{z} \frac{(- \ln y)^{n-1}}{(n-1)!} \,dy + \int_{z}^{1} \frac{z}{y} \cdot \frac{(- \ln y)^{n-1}}{(n-1)!} \ln y \,dy \\
& = \left (\frac{z(-\ln z)^{n-1}}{(n-1)!} + \frac{z(-\ln z)^{n-2}}{(n-2)!} + \dots + \frac{z(-\ln z)^{1}}{1!} + z\right ) \\
& + \left ( \frac{z(-1)^{n-1}(\ln 1)^{n}}{n!} - \frac{z(-1)^{n-1}(\ln z)^{n}}{n!} \right ) \\
& = \sum_{i=0}^{n} \frac{z(-\ln z)^{i}}{i!}.
\end{aligned} 
$$

Differentiating the result above finishes the proof;

$$ 
\begin{aligned}
f_{Z_{n+1}}(z) & = \frac{d}{dz} F_{Z_{n+1}}(z) \\
& = \frac{d}{dz}\left (\sum_{i=0}^{n} \frac{z(-\ln z)^{i}}{i!}\right ) \\
& = 1 + \sum_{i=1}^{n} \left ( \frac{(-1\ln z)^{i}}{i!} - \frac{(-\ln z)^{i-1}}{(i-1)!} \right ) \\
& = 1 + \left ( \frac{(-\ln z)^{1}}{1!} - 1 \right ) + \left ( \frac{(-\ln z)^{2}}{2!} - \frac{(-\ln z)^{1}}{1!} \right ) + \dots \\
& \dots + \left ( \frac{(-\ln z)^{n-1}}{(n-1)!} - \frac{(-\ln z)^{n-2}}{(n-2)!} \right ) + \left ( \frac{(-\ln z)^{n}}{n!} - \frac{(-\ln z)^{n-1}}{(n-1)!} \right ) \\
& = \frac{(-\ln z)^{n}}{n!}.
\end{aligned} 
$$