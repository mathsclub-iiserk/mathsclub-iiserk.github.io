---
layout: post
title: August - Sequentially Arithmetic
author: Sayan Dutta, Sohom Gupta
blurb: >
    Today, we're going to explore certain distributions of arithmetic
    sequences, and their connection with Riemann integrals.
tags: monthlycontest
katex: true
---


"Good afternoon, dear friends!" Senn took his seat. "We are back after the two
month hiatus. Things weren't the easiest for us but your support has been
phenomenal - we dearly appreciate it. We took this time to set up our own
studio - so that in the future we can stream from home whenever necessary. Pura
is doing better now; all your good wishes shall definitely be conveyed to
Estella as she sees the light of day. Thank you again, and let's begin!"

Since we were engaged in so much, my good friend Tensou 天蒼 has made me the
problems this time. It is pretty advanced this time around, but at least you'll
get a new flavour. We shall look at number sequences and the various properties
they exhibit.

For a real number $x$, let $[x]$ denote the _integral part_ of $x$, and let
$\{x\}=x-[x]$ denote the _fractional part_ of $x$ (or the residue of $x$ modulo
1). We note that $\{x\}\in I=[0,1)\forall x\in \mathbb R$.

Let $\omega=(x_n)_{n=1}^\infty$ be a given sequence of real numbers. For a positive
integer $N$ and a subset $E$ of $I$, let the counting function $A(E; N;
\omega)$ be defined as the number of terms $x_n$, $1 \le n \le N$, for which
$x_n\in E$. If there is no risk of confusion, we shall often write $A(E; N)$
instead of $A(E; N; \omega)$.

**Definition 1**: The sequence $\omega = (x_n)\_{n=1}^\infty$ of real numbers is
said to be _uniformly distributed modulo 1_ (abbreviated _ud mod 1_) if for
every pair of real numbers $a,b$, $0\le a<b\le 1$ we have

$$
    \lim_{N\to \infty} \frac{A([a,b);N;\omega)}{N}=b-a. \tag{1}
$$

So, in simple terms, the sequence $\omega$ is ud mod 1 if every half-open
subinterval of $I$ eventually gets its "proper share" of fractional parts.

**Problem 1**: Show that $(1)$ can be reframed as

$$
    \lim_{N\to \infty} \frac 1N\sum_{n=1}^N c_{[a,b)}(\{x_n\})=\int_0^1
    c_{[a,b)}(x) \:\text{d}x, \tag{2}
$$

where $c_{[a,b)}$ is the characteristic function of the interval $[a,b)\subset
I$.

**Problem 2.1**: Show that $\omega=(x_n)$ is ud mod 1 if and only if for every
real valued continuous function $f$ defined on the closed unit interval
$\overline I=[0,1]$, we have

$$
    \lim_{N\to \infty}\frac 1N\sum_{n=1}^N f(\{x_n\})=\int_0^1 f(x)\text{d}x
    \tag{3}
$$

**Hint**: Recall how step functions (and hence, characteristic functions) are
used to approximate Riemann Integrals.

**Problem 2.2**: Does $(3)$ hold if $f$ is a complex-valued continuous function
on $\mathbb R$?

**Problem 2.3**: By tweaking few parts of the proof of **Problem 2.1** (or
otherwise if you dare) show that a sequence $(x_n)$ is ud mod 1 if and only if
we have

$$
    \lim_{N\to \infty} \frac 1N \sum_{n=1}^N f(x_n)=\int_0^1 f(x_n)\:\text{d}x
    \tag{4}
$$

for every complex valued continuous function $f$ on $\mathbb R$ with period 1.

**Problem 3**: Using $(1)$ or $(3)$, (just to cheer you up) construct any
sequence that is _not_ ud mod 1.

Now, prove that the sequence

$$
    \frac 01, \frac 02, \frac 12, \frac 03, \frac 13, \frac 23,\dots ,\frac
    0k,\frac 1k,\dots ,\frac{k-1}{k},\dots
$$

is ud mod 1.

Now, let $(x_n)$ be a sequence in $I$. For a subinterval $[a, b)$ of $I$ and $N
\ge 1$, let $S([a, b); N)$ be the sum of the elements from $x_1, x_2,\dots
,x_N$ that are in $[a, b)$. Show that $(x_n)$ is ud mod 1 if and only if

$$
    \lim_{N\to \infty}\frac{S([a, b); N)}{N}=\frac 12(b^2-a^2)
$$

for all subintervals $[a,b)$ of $I$.

**Problem 4**: Deduce from $(1)$ that if the sequence $(x_n)\_{n=1}^\infty$ is
ud mod 1, then so is $(x_n+\alpha)_{n=1}^\infty$ for a real constant $\alpha$.
Now, show that if a sequence $(x_n)$ is ud mod 1, and if $(y_n)$ is a sequence
such that

$$
    \lim_{n\to \infty}(x_n-y_n)=\alpha,
$$

where $\alpha$ is a real constant, then $(y_n)$ is ud mod 1.

Now, we want to generalize our ideas of distribution modulo 1.

Let $\Delta$ be a subdivision of the interval $[0,\infty)$ so that

$$
\begin{align*}
    &\Delta : 0=z_0<z_1<z_2<\dots\\
    &\lim_{k\to \infty} z_k=\infty
\end{align*}
$$

For $z_{k-1}\le x<z_k$, let us define

$$
\begin{align*}
    &[x]_{\Delta}=z_{k-1}\\
    &\{x\}_{\Delta}=\frac{x-z_{k-1}}{z_k-z_{k-1}}
\end{align*}
$$

so that $0\le \{x\}_{\Delta}<1$.

**Definition 2**: The sequence $(x_n)\_{n=1}^\infty$ of nonnegative real numbers
is said to be _uniformly distributed modulo $\Delta$_ (abbreviated _ud mod
$\Delta$_) if the sequence $(\{x_n\}\_{\Delta})_{n=1}^\infty$ is ud mod 1.

Note that if $\Delta$ is the subdivision for which $z_k=k$, this concept
reduces to that of ud mod 1.

**Problem 5**: Let $(x_n)$ be an _increasing_ sequence of nonnegative real numbers with

$$
    \lim_{n\to \infty} x_n=\infty.
$$

Let $A(x,\alpha)$ be the number of $x_n<x$ with $\{x_n\}_{\Delta}<\alpha$ and
let $A(x)=A(x,1)$. Check that the sequence $(x_n)$ is ud mod $\Delta$ if and
only if we have

$$
    \lim_{x\to \infty}\frac{A(x,\alpha)}{A(x)}=\alpha
$$

for all $\alpha\in(0,1)$.

Now, prove that

$$
    \lim_{k\to \infty}\frac{A(z_{k+1})}{A(z_k)}=1
$$

is a necessary condition for $(x_n)$ to be ud mod $\Delta$.

"Wow, Problem 5 is pretty hard at first glance! Instead of the general
approximating a continuous function by step functions, we here need to
approximate it with piece-wise linear components. Can you try it out?" 

**Bonus question**: Use $(4)$ to show that the sequence $(x_n)$ is ud mod 1 if and only if

$$
    \lim_{N\to \infty}\frac 1N\sum_{n=1}^N e^{2\pi ihx_n}=0
$$

for all integers $h\neq 0$.

**Hint**: You may want to use the Weierstrass Approximation Theorem. Using this
or otherwise, classify the values of $\theta$ for which the sequence
$(n\theta)$ is ud mod 1. If you can't provide a proof, you may also want to
make an intuitive guess and write an intuitive explanation down.

Senn quietly closed the scribble book. "Pura doesn't approve of this at all -
she thinks the problems are cut out for senior undergrads - but I'm sure some
of you are math majors and were pining to get hands on something non-trivial.
Here it is! And for the rest, we'll go back to our own flavour from next month,
when we get more time to interact!"

## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in).
