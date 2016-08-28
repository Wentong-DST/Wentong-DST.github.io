---
layout: post
title:  "Levels of large deviations."
date:   2016-08-28
author: Mark N
categories:
---

I will be studying Large Deviations for Random Graphs for my Honours thesis. Here's a (rather dense) summary of what I've been studying so far. I'm currently on the "Large Deviations" part, and plan to post softer details concerning the Large Deviation Principle (LDP) in the near future -- assuming the kindness of time.

Large deviation theory is the study of probabilities of rare events (and for example, their rate of decay). There are different "levels" of generalisation in large deviation theory. Level 1 is also known as Cramer's theorem for the empirical average, Level 2 is Sanov's theorem for the empirical measure and Level 3 concerns the slightly abstract large deviation for the empirical process.


**Level 1: Empirical Average.**

Let $$\{X_{i}\}$$ be a sequence of IID, $$\mathbb{R}$$-valued random variables such that for all $$t \in \mathbb{R}$$,  

$$\varphi(t) := \mathbf{E}e^{tX_{i}} < \infty.$$

Let $$S_{n} = \sum_{i=1}^{n} X_{i}$$, then for any $$a > \mathbf{E}X_{i}$$

$$\lim_{n\to\infty} \frac{1}{n}\log\mathbf{P}(S_{n} > na) = -I(a),$$

where $$I$$ is the rate function defined by

$$I(z) = \sup_{t\in\mathbb{R}}\{tz - \log\varphi(t)\}.$$

**Level 2: Empirical Measure.**

Let $$\{X_{i}\}$$ be a sequence of IID random variables taking values in a finite set $$\Gamma=\{1,\dots,r\}\subset\mathbb{N}$$ with marginal probability law $$p = (p_{s})_{s\in\Gamma}$$, and $$p_{s} > 0$$ for all $$s = 1, \dots, r$$. 

Define the empirical measure

$$L_{n} = \frac{1}{n}\sum_{i=1}^{n} \delta_{X_{i}}.$$

Note that $$L_{n}$$ lies in the space of probability measures on $$\Gamma$$, which we will denote by $$\mathcal{M}(\Gamma) = \left\{\nu = (\nu_{1}, \dots, \nu_{r}) \in [0,1]^{r} : \sum_{s=1}^{r}\nu_{s} = 1\right\}$$. 

Let $$d(\mu, \nu) = 2^{-1} \sum_{s=1}^{r}\left\vert\mu_{s} - \nu_{s}\right\vert$$, then the pair $$(\mathcal{M}(\Gamma), d)$$ forms a Polish space.

More importantly, for any $$a > 0$$

$$\lim_{n\to\infty} \frac{1}{n}\log\mathbf{P}(L_{n}\in B[p, a]^{c}) = -\inf_{\nu \in B[p, a]^{c}}\{I_{p}(\nu)\},$$

where $$B[p,a]$$ denotes the closed ball centered at $$p \in \mathcal{M}(\Gamma)$$ of radius $$a$$, and

$$I_{p}(\nu) = \sum_{s=1}^{r}\nu_{s}\log\frac{v_{s}}{p_{s}}.$$

**Level 3: Empirical Process.**

As an extension to Level 2, we can count $$N$$-words for $$N \geq 2$$. Impose periodic boundary conditions that is $$X_{n + m} = X_{m}$$ for $$m = 1, \dots, N-1$$ and introduce the $$N$$-word empirical measure

$$L_{n}^{N} = \frac{1}{n}\sum_{i=1}^{n} \delta_{(X_{i}, \dots, X_{i+N-1})}.$$

The random measure $$L_{n}$$ lies in the space 

$$\mathcal{\tilde{M}}(\Gamma^{N}) = \left\{\nu \in \mathcal{M}(\Gamma^{N}) : \sum_{s_{N}} \nu_{s_{1},\dots,s_{N-1},s_{N}} = \sum_{s_{N}} \nu_{s_{N}, s_{1}, \dots, s_{N-1}}\right\},$$

whereby letting $$d_{N}(\mu, \nu) = \frac{1}{2}\sum_{s_{1}, \dots, s_{N}} \left\vert\mu_{s_{1}, \dots, s_{N}} - \nu_{s_{1}, \dots, s_{N}}\right\vert$$ turns the pair $$\left(\mathcal{\tilde{M}}(\Gamma^{N}), d_{N}\right)$$ into a Polish space. Furthermore we can show that

$$\lim_{n\to\infty} \frac{1}{n}\log\mathbf{P}(L_{n}^{N} \in B[p^{N}, a]^{c}) = -\inf_{\nu\in B[p^{N},a]^{c}}\{I_{p}^{N}(\nu)\},$$

where $$B[p^{N}, a]$$ denotes the closed ball centered at $$p^{N}\in \mathcal{\tilde{M}}(\Gamma)$$ and

$$I_{p}^{N}(\nu) = \sum_{s_{1}, \dots, s_{N}} \nu_{s_{1}, \dots, s_{N}}\log\frac{v_{s_{1}, \dots, s_{N}}}{\bar{\nu}_{s_{1}, \dots, s_{N-1}}p_{s_{N}}},$$

with $$\bar{\nu}_{s_{1}, \dots, s_{N-1}} = \sum_{s_{N}} \nu_{s_{1}, \dots, s_{N-1}, s_{N}}.$$

Setting $$N = n$$, we can study $$L_{n}^{n}$$ as $$n\to\infty$$. First write

$$\mathbf{X}^{(n)}=(X_{1},\dots,X_{n},X_{1},\dots,X_{n},\dots) \in \Gamma^{\mathbb{N}},$$

$$\sigma^{i}(\mathbf{X}^{(n)})=(X_{i},\dots,X_{i+n-1},X_{i},\dots,X_{i+n-1},\dots) \in \Gamma^{\mathbb{N}},$$

and let

$$R_{n} = \frac{1}{n}\sum_{i=1}^{n} \delta_{\sigma^{i}(\mathbf{X}^{(n)})}.$$

$$R_{n}$$, called the empirical process, is a random measure in the Polish space $$\left(\mathcal{\hat{M}}(\Gamma^{\mathbb{N}}), d\right)$$ whereby

$$\mathcal{\hat{M}}(\Gamma^{\mathbb{N}}) = \{\nu \in \mathcal{M}(\Gamma^{\mathbb{N}}) : \nu \circ \sigma^{-1} = \nu\},$$

$$d(\mu, \nu) = \sum_{N \in \mathbb{N}} 2^{-N} d_{N}(\pi_{N}\mu, \pi_{N}\nu),$$

and $$\pi_{N}: \Gamma^{\mathbb{N}}\to\Gamma^{N}$$ refers to the usual projection, with $$\pi_{N}\mu = \mu\circ\pi_{N}^{-1}$$.

This brings us to the so-called Level 3 LDP. Let $$\{X_{i}\}$$ be an IID sequence as in Level 2. For any $$a > 0$$, let $$B[p^{\mathbb{N}}, a]$$ denote the closed ball centered at $$p^{\mathbb{N}} \in \mathcal{\hat{M}}(\Gamma^{\mathbb{N}})$$ of radius $$a$$ and define

$$J(a) = \inf_{\nu\in B[p^{\mathbb{N}}, a]}\{I_{p}^{\infty}(\nu)\},$$

where

$$I_{p}^{\infty}(\nu) = \sup_{N\geq 2} I_{p}^{N}(\pi_{N}\nu).$$

Then we have the result:

1. $$\liminf_{n\to\infty}\frac{1}{n}\mathbf{P}(R_{n}\in B[p^{\mathbb{N}}, a]^{c}) \geq -J(a),$$

2. $$\limsup_{n\to\infty}\frac{1}{n}\log\mathbf{P}(R_{n}\in B[p^{\mathbb{N}}, a]^{c}) \leq - J(a^{-}) = \lim_{\varepsilon\downarrow 0} J(a - \varepsilon).$$

### Reference

Frank den Hollander. *Large Deviations*. American Mathematical Soc., 2008