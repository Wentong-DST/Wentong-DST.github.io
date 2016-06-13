---
layout: post
title:  "Playing with roots."
date:   2016-06-01 00:12:03 +0800
author: Mark N
categories:
---
Tricks with sequences.

<hr>
<hr>
<center>
	$$
	\begin{aligned}
		\sqrt{2\sqrt{2\sqrt{2\cdots}}}
		& = (2(2(2\cdots)^{\frac{1}{2}})^{\frac{1}{2}})^{\frac{1}{2}} \\
		& = 2^{\frac{1}{2} + \frac{1}{2^{2}} + \frac{1}{2^{3}} + \dots} \\
		& = 2^{1} \\
		& = 2
	\end{aligned}
	$$	
</center>
<hr>
<hr>
<center>
	$$
	\begin{aligned}
		\sqrt{2\sqrt[3]{2\sqrt[4]{2\cdots}}}
		& = (2(2(2\cdots)^{\frac{1}{4}})^{\frac{1}{3}})^{\frac{1}{2}} \\
		& = 2^{\frac{1}{2!} + \frac{1}{3!} + \frac{1}{4!} + \dots} \\
		& = 2^{-2 + \frac{1}{0!} + \frac{1}{1!} +\frac{1}{2!} + \frac{1}{3!} + \frac{1}{4!} + \dots} \\
		& = 2^{\text{e}-2}
	\end{aligned}
	$$
</center>
<hr>
<hr>
<center>
	$$
	\begin{aligned}
		\frac{1}{\sqrt{2\left(\frac{1}{\sqrt{2\left(\frac{1}{\sqrt{2\left(\cdots\right)}}\right)}}\right)}}
		& = (2(2(2\cdots)^{-\frac{1}{2}})^{-\frac{1}{2}})^{-\frac{1}{2}} \\
		& = 2^{-(\frac{1}{2} - \frac{1}{2^{2}} + \frac{1}{2^{3}} - \dots)} \\
		& = 2^{-\frac{1}{3}}
	\end{aligned}
	$$
</center>
<hr>
<hr>
<center>
	$$
	\begin{aligned}
	\frac{1}{\sqrt{2\left(\frac{1}{\sqrt[3]{2\left(\frac{1}{\sqrt[4]{2\left(\cdots\right)}}\right)}}\right)}}
	& = (2(2(2\cdots)^{-\frac{1}{4}})^{-\frac{1}{3}})^{-\frac{1}{2}} \\
	& = 2^{- \frac{1}{2!} + \frac{1}{3!} - \frac{1}{4!} + \dots} \\
	& = 2^{-(\frac{1}{0!} - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \frac{1}{4!} + \dots )}\\
	& = 2^{-\text{e}^{-1}}
	\end{aligned}
	$$
</center>
<hr>
<hr>
<center>
	$$ 
	\begin{aligned}
	\sqrt{ 2 + \sqrt{2 + \sqrt{ 2 + \sqrt{ 2 + \sqrt{ 2 + \dots } } } } } & = L \\
	\implies \sqrt{2 + L} & = L \\
	\implies L & = 2 
	\end{aligned}
	$$
</center>
<hr>
<hr>
<center>
	$$ 
	\begin{aligned}
	\sqrt{ k + \sqrt{k + \sqrt{ k + \sqrt{ k + \sqrt{ k + \dots } } } } } & = L, \,\,\,\, k > 0\\
	\implies \sqrt{k + L} & = L \\
	\implies L & = \frac{1}{2} + \sqrt{\frac{4k+1}{4}}
	\end{aligned}
	$$
</center>
<hr>
<hr>