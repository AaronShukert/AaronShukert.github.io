---
layout: post
title: A MathJax Excersize
subtitle: Proof of Cauchy-Schwarz in an L<sub>2</sub> inner product space.
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [test]
comments: true
---

Given two continuous functions $f:[a,b] \xrightarrow{} \mathbb{R}$ and $g:[a,b]  \xrightarrow{} \mathbb{R}$, we define the L<sub>2</sub> inner product of _f_ and _g_ on this interval, denoted by $\langle f,g\rangle$, by the formula

 $\int_{a}^{b} f(x)g(x)dx$. 
 
 We can quickly check that this is an inner product by showing it satisfies the linearity and symmetric properties.
 
 - Linearity
 
 $\langle \alpha f + \beta g, h\rangle = \int_a^b (\alpha f(x) + \beta g(x)) h(x) dx = \int_a^b\alpha f(x)h(x) + \int_a^b \beta g(x)h(x)$

$ = \alpha\langle f,h\rangle + \beta\langle g,h \rangle.$

- Symmetry

$\langle f,g\rangle =\int_a^b f(x)g(x)dx = \int_a^b g(x)f(x)dx= \langle g,f\rangle$

Now, since we know that this is an inner product, we already know that the Cauchy-Schwarz inequality applies, but sometimes it can be enlightening to build a proof in the context with which you are working. So, in this spirit, we aim to prove the Cauchy-Schwarz inequality which (in this context) is stated as follows: 

$\left\lvert \int_{a}^{b} f(x)g(x)dx \right\rvert \leq \sqrt{\int_{a}^{b} [f(x)]^2dx}\sqrt{\int_{a}^{b} [g(x)]^2dx}$

Before doing so, it is convenient to establish the idea of orthogonality.

#### Definition

Two functions _f_ and _g_ are said to be **orthogonal** on the interval $[a,b]$ if $\langle f, g \rangle = 0$. In this context, that is $\int_a^b f(x)g(x)dx=0$.

From here, given $g \not= 0$, we define $\lambda= \frac{\langle f,g \rangle}{\langle g,g\rangle}$ and $h= f-\lambda g$. It is not hard to show that _h_ is orthogonal to _g_. With these tools, the proof turns out to be rather simple. 


### Proof
**a**. If either _f_ or _g_ are identically 0 along the interval, equality clearly holds and both sides are 0. 

**b**. Now, under the assumption that at least one of _f_ or _g_ is not identically 0 (which we will assume without loss of generality that $g \not= 0$, we prove the theorem as follows. 

For any function _F_, we know that $0 \leq \int_a^b[F(x)]^2dx$. Now, using our function _h_ in place of _F_, we have that 

$ 0 \leq \int_a^b[f(x)-\lambda g(x)][f(x)-\lambda g(x)] dx= \int_a^b[f(x)-\lambda g(x)]f(x) dx + \int_a^b[f(x)-\lambda g(x)]g(x)dx $

Here, hopefully you can see that the last term is $\langle h,g \rangle$ which is 0 due to _h_ and _g_ being orthogonal by the definition of _h_. So, we reduce this to the equation to

$0 \leq \int_a^b[f(x)-\lambda g(x)]f(x) dx = \int_a^b[f(x)^2]dx -\lambda \int_a^b f(x)g(x)dx$.

Now, since we have that 

$\lambda = \frac{\int_a^b f(x)g(x)dx}{\int_a^b g(x)g(x)dx}$

we can re-write the equation by multiplying by the denominator and moving the last term left. Then we get

$[\int_a^b f(x)g(x)dx]^2 \leq [\int_a^b[f(x)^2]dx] [\int_a^b[g(x)^2]dx ]$

Finally, by taking the root of both sides we obtain 

$\left\lvert \int_{a}^{b} f(x)g(x)dx \right\rvert \leq \sqrt{\int_{a}^{b} [f(x)]^2dx}\sqrt{\int_{a}^{b} [g(x)]^2dx}$.

This was mostly just a test to see how similar MathJax is to $\LaTeX$ so I can plan to write much better posts in the future. For now, perhaps someone will find this interesting.
