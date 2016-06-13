---
layout: post
title:  "A Catalan lemma."
date:   2016-01-01 00:00:00 +0800
author: Mark N
categories:
---


Nice identity relating Catalan numbers $$C_{k} = \frac{(2k)!}{(k+1)!k!}$$ and the moments of the semicircle distribution $$\mathbf{E}X^{k} = \int_{-2}^{2}x^{k}\sigma(x)\text{d}x$$ where $$\sigma(x) = \frac{1}{2\pi}\sqrt{4-x^{2}}$$. 

I learnt about this when I was studying random matrix theory (part of an undergraduate research project). It is an important result used in the *moment method* proof of Wigner's semicircle law.

**Lemma:** Using the notation above, 
<center>
$$
\mathbf{E}X^{k} = 
\begin{cases} 
C_{\frac{k}{2}} & \text{ if } k \equiv 0 \mod 2\\
0 & \text{ if } k \equiv 1 \mod 2.
\end{cases}
$$    
</center>

*Proof*. When $$k$$ is odd, then $$x^{k}\sigma(x)$$ is an odd function. Hence $$\mathbf{E}X^{k} = 0$$. When $$k$$ is even, write $$2k$$ for simplicity and observe that
<center>
$$
\begin{aligned}
\mathbf{E}X^{2k}
& = \int_{-2}^{2} x^{2k}\sigma(x)\,\text{d}x\\
& = \int_{-2}^{2} \frac{1}{2\pi} x^{2k} \sqrt{4 - x^{2}}\, \text{d}x\\
& = \frac{2^{2k+1}}{\pi}\int_{-\pi/2}^{\pi/2} \sin^{2k}\theta \cos^{2}\theta\,\text{d}\theta\\
& = \frac{2^{2k+1}}{\pi}\left(\int_{-\pi/2}^{\pi/2} \sin^{2k}\theta\,\text{d}\theta - \int_{-\pi/2}^{\pi/2}\sin^{2k + 2}\theta\,\text{d}\theta\right)\\
& = \frac{2^{2k+1}}{\pi}\left(\int_{-\pi/2}^{\pi/2} \sin^{2k}\theta\,\text{d}\theta - (2k+1)\int_{-\pi/2}^{\pi/2}\cos^{2}\theta\sin^{2k}\theta\,\text{d}\theta\right)\\
& = \frac{2^{2k+1}}{\pi}\left(\int_{-\pi/2}^{\pi/2} \sin^{2k}\theta\,\text{d}\theta \right)- (2k+1)\mathbf{E}X^{2k}\\
\implies
\mathbf{E}X^{2k}
& = \frac{2^{2k+1}}{(2k+2)\pi}\int_{-\pi/2}^{\pi/2} \sin^{2k}\theta\,\text{d}\theta\\
& = \frac{2^{2}(2k-1)}{(2k+2)}\mathbf{E}X^{2k-2}.
\end{aligned}
$$
</center>
Similarly, the definition of Catalan numbers above imply a recurrence relation of the form
<center>
$$
\begin{aligned}
C_{k}
& = \frac{(2k)!}{(k+1)!(k)!}\\
& = \frac{(2k)(2k-1)!}{(k+1)(k)!(k)(k-1)!}\\
& = \frac{2k(2k-1)}{(k+1)(k)}C_{k-1}\\
& = \frac{2^{2}(2k-1)}{2k+2}C_{k-1}.
\end{aligned}
$$
</center>
It is clear that $$\mathbf{E}X^{0} = 1 = C_{0}$$. Inductively, $$\mathbf{E}X^{2k} = C_{k}$$ for all integers $$ k \geq 0$$; and this completes the proof.