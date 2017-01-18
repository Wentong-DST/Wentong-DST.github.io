---
layout: post
title:  "Limiting eigenvalue densities of random matrices."
date:   2016-07-11
author: Mark N
categories:
---

Early this year, I got the chance to do some undergraduate research (UROPS) on random matrix theory (more like a study actually). My UROPS supervisor was [<u>Wang Dong</u>](http://www.math.nus.edu.sg/~matwd/) and the project was recently nominated for the NUS Centre for Remote Imaging, Sensing and Processing (CRISP) Award and so I'm supposed to prepare a 20-minute talk for the judges to decide who to give the award to and whatnot. 

Anyways, I thought it would be nice to do a short introduction and compilation of results here first. The main mathematical tool used is the [<u>moment method</u>](https://en.wikipedia.org/wiki/Method_of_moments_(probability_theory)). Interested readers can refer to my [<u>UROPS paper</u>](/pdf/ma3288.pdf "ma3288.pdf") for the detailed proofs and references. Note that there are very stupid typos and errors which I've yet to correct (most notably the proof for counting Dyck paths)..

**What are random matrices?**

Matrices with random variable entries, e.g.

$$ X_{n} := 
\begin{bmatrix} 
X_{1,1} & X_{1,2} & \dots & X_{1, n-1} & X_{1,n} \\ 
X_{2,1} & X_{2,2} & \dots & X_{2, n-1} & X_{2,n} \\ 
\vdots & \vdots & \ddots & \vdots & \vdots \\ 
X_{n-1,1} & X_{n-1,2} & \dots & X_{n-1, n-1} & X_{n-1,n} \\ 
X_{n,1} & X_{n,2} & \dots & X_{n, n-1} & X_{n,n} \\ 
\end{bmatrix},$$

where each entry $$X_{ij}$$ is some random variable. 

One of the aims in random matrix theory is to establish universality in various random matrix *ensembles*. A common statistic of interest is the random matrix eigenvalue distribution along $$\mathbb{R}$$ (here we assume that the matrix has an appropriate property, such as being Hermitian or symmetric).

**Wigner's semicircle law**

A *Wigner random matrix* is defined as a random Hermitian matrix $$X_{n} \in M_{n}(\mathbb{C})$$ with independent upper triangular entries $$X_{ij}$$, $$1 \leq i \leq j \leq n$$, satisfying the following conditions:

* For all $$i = j$$, we have $$\mathbf{E}X_{ij} = 0$$ and $$\mathbf{E}X_{ij}^{2} = 1$$.
* For all $$i < j$$, we have $$\mathbf{E}X_{ij} = 0$$ and $$\mathbf{E} \lvert X_{ij} \rvert^{2} = 1$$.
* For any $$k \in \mathbb{N}$$, there exists $$M_{k} \in \mathbb{R}$$ such that $$\mathbf{E}\lvert X_{ij}\rvert^{k} \leq M_{k}$$ for all $$1 \leq i, j \leq n$$.

Since $$X_{n}$$ is necessarily Hermitian, it has $$n$$ real eigenvalues (up to multiplicity) -- which we may order and label $$\lambda_{1} \leq \lambda_{2} \leq \dots \leq \lambda_{n}$$. This motivates the definition of the Empirical Spectral Measure (ESM) of eigenvalues,

$$\mu_{n}(x) := \frac{1}{n}\sum_{i=1}^{n}\delta_{\frac{\lambda_{i}}{\sqrt{n}}}(-\infty, x].$$

Note: $$\mu_{n}$$ is a random variable (or random *measure*). The limiting density of interest is the semicircle density,

$$\sigma(x) = \frac{1}{2\pi} \sqrt{4 - x^{2}}\cdot \chi_{[-2, 2]}.$$

The moment method focuses on proving the convergence of _expected_ moments of $$\mu_{n}$$ to $$\sigma$$ (since $$\mu_{n}$$ is random). This is summarized below:

**Lemma**: For any $$k \in \mathbb{N}$$, we have

$$\lim_{n\to\infty}\mathbf{E}\int_{\mathbb{R}}x^{k}\text{d}\mu_{n}=\int_{\mathbb{R}}x^{k}\sigma(x)\text{d}x.$$

Using this deterministic convergence, and other results we can prove the weak convergence $$\mu_{n}\overset{d}\longrightarrow\sigma$$, in probability:

**Theorem** (Wigner): The distribution $$\mu_{n}$$ converges weakly to $$\sigma$$, in probability. Equivalently, for any $$\varepsilon > 0$$ and bounded continuous test function $$f : \mathbb{R} \to \mathbb{R}$$,

$$\lim_{n\to\infty}\mathbf{P}\left(\left\lvert \int_{\mathbb{R}}f(x)\text{d}\mu_{n} - \int_{\mathbb{R}}f(x)\sigma(x)\text{d}x\right\rvert > \varepsilon \right) = 0.$$

As a demonstration of Wigner's semicircle law:

<img src="/pictures/semicircle_law.jpg" height="175" width="650">

**Marchenko-Pastur law**

A *Wishart random matrix* is defined as a $$p_{n}\times p_{n}$$ random matrix of the form $$XX^{*}$$, resulting from the post-multplication of a $$p_{n}\times n$$ random complex-valued matrix $$X$$ with its adjoint $$X^{*}$$. The matrix $$X$$ satifies the following conditions:

* $$\mathbf{E}X_{ij} = 0$$ and $$\mathbf{E} \lvert X_{ij} \rvert^{2} = 1$$, for all $$1 \leq i \leq p_{n}$$ and $$1 \leq j \leq n$$.
* For any $$k \in \mathbb{N}$$, there exists $$M_{k} \in \mathbb{R}$$ such that $$\mathbf{E}\lvert X_{ij}\rvert^{k} \leq M_{k}$$ for all $$1 \leq i \leq p_{n}$$ and $$ 1\leq j \leq n$$.
* The integer sequence $$p_{n}$$ has the property that

$$\lim_{n\to\infty} \frac{p_{n}}{n} = y \in (0,1].$$

Similarly $$XX^{*}$$ has $$p_{n}$$ real eigenvalues, and we define an appropriate ESM for a Wishart matrix,

$$\nu_{p_{n}}(x) = \frac{1}{p_{n}}\sum_{i=1}^{p_{n}} \delta_{\frac{\lambda_{i}}{n}}(-\infty, x].$$

And the limiting density is the famous Marchenko-Pastur density

$$\phi(x) = \frac{1}{2\pi xy}\sqrt{(b-x)(x-a)}\cdot\chi_{[a,b]},$$

where $$a = (1 - \sqrt{y})^{2}$$ and $$b = (1 + \sqrt{y})^{2}$$.

It turns out that (under certain conditions) it is sufficient to prove convergence in expected moments, in order to conclude $$\nu_{n}\overset{d}\longrightarrow\phi$$, in probability.

**Lemma**: For any $$k \in \mathbb{N}$$, we have

$$\lim_{n\to\infty}\mathbf{E}\int_{\mathbb{R}}x^{k}\text{d}\nu_{p_{n}}=\int_{\mathbb{R}}x^{k}\phi(x)\text{d}x.$$

As a demonstration of the Marchenko-Pastur law (here we use $$y = 0.45$$):

<img src="/pictures/marchenko_pastur_law.jpg" height="175" width="650">

**Singular Values of Powers of Random Matrices**

The last result concerns matrices of the form 

$$X^{(m)}X^{*(m)} := \underbrace{XX \cdots X}_{m\text{ times}}\cdot\underbrace{X^{*}X^{*} \cdots X^{*}}_{m\text{ times}}$$

Where $$m$$ is some fixed natural number and $$X$$ is a $$n \times n$$ random matrix satifying the following conditions:

* $$\mathbf{E}X_{ij} = 0$$ and $$\mathbf{E}\lvert X_{ij}\rvert^{2} = 1$$ for all $$1\leq i, j \leq n$$.
* For any $$k \in \mathbb{N}$$, there exists $$M_{k} \in \mathbb{R}$$ such that $$\mathbf{E}\lvert X_{ij}\rvert^{k} \leq M_{k}$$ for all $$1 \leq i, j \leq n$$.

The ESM for this random matrix of interest is defined by

$$\eta_{n}^{(m)}(x) = \frac{1}{n}\sum_{i=1}^{n}\delta_{\frac{\lambda_{i}}{n^{m}}}(-\infty,x].$$

Interestingly, the limiting density is not explicity described in the study. It is instead uniquely defined by its moments for each $$k \in \mathbb{N}$$,

$$C_{m, k} = \frac{1}{mk + 1} \binom{mk + k}{k}.$$

And similarly the convergence of expected moments can be proven, that is: 

**Lemma**: For any $$m, k \in \mathbb{N}$$, we have

$$\lim_{n\to\infty}\mathbf{E}\int_{\mathbb{R}}x^{k}\text{d}\eta_{n}^{(m)}=\frac{1}{mk + 1} \binom{mk + k}{k}=C_{m,k}.$$

Some final remarks concerning this last result:

1. The integers defined by $$C_{m, k}$$ are known as the single-parameter Fuss Catalan numbers. 

2. This result can be seen as a generalisation of the Marchenko-Pastur law, which is essentially the case when $$m = 1$$.


### Selected References

**[1]** Greg W. Anderson, Alice Guionnet, Ofer Zeitouni, “_An Introduction to Random Matrices_”. Cambridge University Press.

**[2]** Jinho Baik, “_Topics in Analysis: Random Matrices, Preliminary Lecture Notes_”. Department of Mathematics, University of Michigan, 2009.

**[3]** Benedek Valkó, “_Lectures 6-7: The Marchenko-Pastur Law_”. Department of Mathematics, University of Wisconsin-Madison, 2009.

**[4]** N. Alexeev, F. Götze, A. Tikhomirov. “_Asymptotic Distribution of Singular Values of Powers of Random Matrices_”. Lithuanian Mathematical Journal, Vol. 50, No. 2, 2010, pp. 121-132.

**[5]** Ronald L. Graham, Donald E. Knuth, Oren Patashnik, “_Concrete Mathematics_”. Addison-Wesley Publishing Company, 1994.