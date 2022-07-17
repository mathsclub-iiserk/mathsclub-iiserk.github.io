---
layout: post
title: May - Generating Oh,no!mials
author: Sohom Gupta
blurb: >
    Today, we're going to take a fun trip through something we all did as high
    school students - monomials, binomials, trinomials ... polynomials!
tags: monthlycontest
katex: true
---


Amongst the cool breeze, under shadows dancing around neon lights, city folk
hurry home - to their cozy bedrooms while the gentle rain hums on the periphery
of all concrete. The purple sky ushers the chronicles of lore unheard of; as if
even the supreme had an epiphany about the vastness of this world, about the
idiosyncratic sequences that cluster at all works of valour that are
unrecognized. Senn takes a quick nap while people are getting ready around him;
the session shall commence in half an hour. He dreams of deserts and black
holes and weddings, which eventually converge into a wet, fertile rainforest
owing to the nice petrichor of the outside world. Slowly the buzz of insects
come to a standstill, the forest stops prancing in merry and the canopy opens a
narrow path for sunlight to rush down on a small struggling sprout, which
spreads its arms joy never seen before.

Thirty minutes pass. Senn is back at his desk, getting things ready. He has
some idea how to work things out, but the most of it will have to be picked up
on the run. Evenings that scream _freedom_, yet not from the confines of
your house - could mean movies, coition or math.

"Greetings everyone! I hope I don't seem alien or queer in faith and family to
any of you out there. As you might have been informed of, Pura is on an
extended leave for her own sake - which is why I am continuing her work. She is
not gone forever, and should ideally be back in a few months. Another
resolution could be to conduct the session from somewhere more cozy, for which
we shall debate. But let's begin with our session; it might be a fun trip
through something we all did as high school students - monomials, binomials,
trinomials ... Polynomials!

To begin we shall understand what a polynomial is in a pretty lax manner.
Suppose you have the uni-variable set $X=\{1,x,x^2,x^3,\ldots\}$. Take any
finite subset of this set, say $X\supset S=\{x^{r_1},x^{r_2},\ldots,x^{r_l}\}$,
where without loss of generality, you can assume the order
${r_l}>r_{l-1}>\ldots>r_2>r_1$ since the original set has an implicit order on
the indices.

Then a linear combination of the elements of this set, say

$$ p_S(x) = k_1x^{r_1}+k_2x^{r_2}+\ldots+k_lx^{r_l} $$

with $k_i\in\mathbb{R}$ and $k_l\neq 0$ is a polynomial of degree $r_l$ with
**real coefficients**. In actuality, you can draw the coefficients from
any field $F$. Also, keep in mind that $x$ itself is a variable, _i.e._
it can be defined over any field (_even rings, if you know them_). For
now, we will only look at real valued polynomials with real coefficients.

In general, you can define a polynomial of degree $n\in\mathbb{N}_0$ by the sum

$$ p(x)=a_0+a_1x+a_2x^2+\ldots+a_nx^n $$

where the coefficient of the highest order term is non-zero, _i.e._
$a_n\neq 0$.

I know how many of you might have much to say. Polynomials can be understood
from a very elementary level, and so there are hundreds of easily
comprehendible results out there. I shall avoid dipping in populated waters,
since they might be polluted waters! Let's try prying into some less lay, more
play territory.

Consider a binomial $(1+x)$ exponentiated by a natural number $n$. Then we
define

$$ p(x)=(x+1)^n. $$

Clearly $p(x)$ is a polynomial of degree $n$, and by the binomial expansion
formula, you can check it term by term as

$$
p_{\beta_n}(x)=\binom{n}{0}x^n+\binom{n}{1}x^{n-1}+\binom{n}{2}x^{n-2}+\ldots+\binom{n}{n}x^0
$$

where the $r^\text{th}$ term is $T_r = \binom{n}{r}x^{n-r}$.

Given any polynomial one can vary, often a question comes in mind - what is the
largest term of the polynomial? By this, I don't mean the degree; just the
largest term if you were to put some arbitrary value of $x$. Obviously, your
largest term will depend on $x$ in that case.

As $x$ goes off towards infinity and the coefficients $a_i$ are constants, we
can safely assume that the leading order term ($x^n$ where $n$ is the degree)
dominates the behaviour of the polynomial, _i.e._ we can write the
approximation

$$ p(x)\sim a_nx^n, \qquad x\to\infty. $$

However for $x$ comparable to (or much less than) the coefficients $a_i$, this
might not be the case. The polynomial $p(x)=10^{370}x+2x^2$ is basically
dominated by the $10^{370}x$ term for a long time (_e.g._
$p(10)=10^{371}+200\approx 10^{371}$).

**(i) Given the polynomial $p_{\beta_n}(x)$ above, find the largest term
$T_r$ for arbitrary $x$ and $n$.**

**(ii) Show that if you fix $n$ and increase $x$ indefinitely, then the
largest term will eventually be the leading order term
$T_0=\binom{n}{0}x^n=x^n$.**

**(iii) What is the minimum value of $x$ for which $x^n$ is the SOLE
largest term?**

"Were you able to get the results with proof?" Senn asked, as he turned a leaf
of Pura's scribble book. He was never fond of preparing for a session - that
killed his natural dynamic and creative nature. Nevertheless, math wasn't one
where you could dump straight facts right out of the blue; and even if he
could, they would be too obscure for anyone to remotely understand. Teaching
math is a hard profession to walk into, but greatly fulfilling when it works.

"If you have studied binomial coefficients before, you might know of a nice
result. It says that the middle order binomial coefficients $\binom{n}{r}$ (for
$r=(n-1)/2$ and $(n+1)/2$) are equal to each other when $n$ is odd. This
derives from the symmetry of the coefficients,

$$ \binom{n}{r}=\binom{n}{n-r}.$$

Clearly $\binom{n}{r}x^{n-r}$ is not symmetric as you vary $r$ - but do they
show any adjacent term equality like in the normal coefficient case?

In $p_{\beta_n}(x)$ keep $x$ fixed as some **natural number** and vary $n$
from $1$ to $t$ for some large number $t$. Count the number of cases where
there were TWO LARGEST TERMS of the series, _i.e._
$\operatorname{max}\{T_i\}=T_r=T_{r+1}$ for some $r$. Call such values of $n$
as **bimodal**.

**(iv) Find the density of bimodal states as $n$ varies in $\{1,2,\ldots,t\}$,
$t\gg 1$. Density is equal to the ratio of bimodal states to all states.**

**(v) Let $\rho_{n,x}(t)$ be the ratio of bimodal states. What value(s)
of $t$ can you take so that $\rho_{n,x}(t)$ is independent of $t$?**

Once you have chosen some value of $t$ such that $\rho_{n,x}(t)$ is independent
of $t$, call this the standard bimodal density $\rho_{n,x}$.

**(vi) Show that $\rho_{n,x}$ is a decreasing function of
$x\in\mathbb{N}$.**

Now that we have worked on a binomial generated polynomial, let's go to some
other niceties.

Let us talk of generating functions. They are ubiquitously used in various
fields of math and science, and can vastly simplify non-trivialities. In an
elementary sense, the generating function of a sequence $(a_0,a_1,a_2,\ldots)$
of reals is given by the infinite degree polynomial

$$ g(x)=a_0+a_1x+a_2x^2+\ldots = \sum_{n\in\mathbb{N}_0}a_nx^n. $$

A generating function can be written in a nice closed form if the infinite
series converges. If the sequence is finite, then we can be more assured of its
convergence.

Consider the function $f(x,t)=e^{xt-\frac{1}{2}t^2}$. This has a valid power
series expansion for all real $x$ and $t$ (even complex, in that case) given by

$$ e^{xt-\frac{1}{2}t^2}=\sum_{n=0}^{\infty}w_n(x)\frac{t^n}{n!} $$

which is a generating function of the sequence $\{w_n(x)\}$. It should not be
too much work to see that we can get each term of the sequence through the
relation

$$ w_n(x) = (-1)^ne^{\frac{x^2}{2}}\frac{d^n}{dx^n}e^{-\frac{x^2}{2}}. $$

**(vii) Show that $w_n(x)$ is a polynomial of degree $n$ on $x$.**

**(viii) Show that $w_n(x)$ is monic, _i.e._ the leading
coefficient $a_n=1$.**

Often terms in a generated sequence can be found out using a series of
operations on the generating function. Note that different operations need not
commute, so they are generally treated on a right to left manner, same when we
compose functions or functions and operations. For example,

$$ \sin\left(\frac{d}{dx}\right)(y)=\sin\left(\frac{dy}{dx}\right)\neq
\left(\frac{d}{dx}\right)\sin(y)=\cos(y)\frac{dy}{dx}. $$

In case of $w_n(x)$ though, we can apply one operator many times to find out
the term. Suppose we define an operation on the number $1$ $n$ times given as

$$ \mathcal{O}_n(x) = \left(Ax-B\frac{d}{dx}\right)^n\cdot 1 $$

where $A$ and $B$ are positive reals. It is easy to find out the first few
iterations.

$$
\begin{align*}
    \mathcal{O}_0(x)&=1\\
    \mathcal{O}_1(x)&=\left(Ax-B\frac{d}{dx}\right)\cdot 1 = Ax\cdot 1 - B\frac{d}{dx}(1) = Ax\\
    \mathcal{O}_2(x)&=\left(Ax-B\frac{d}{dx}\right)\left(Ax-B\frac{d}{dx}\right)\cdot 1\\
    &= \left(Ax-B\frac{d}{dx}\right)Ax =A^2x^2-AB\\
    \text{and so on ...}
\end{align*}
$$

**(ix) If we claim that $\mathcal{O}_n(x)=w_n(x)$, find the values of $A$
and $B$.**

Given these values of $A$ and $B$, and the relation
$\frac{d}{dx}w_n(x)=nw_{n-1}(x)$, we can try to formulate recurrence relations
describing $w_n(x)$. Consider a Fibonacci-esque recurrence relation
given by

$$ w_{n+1}(x)=\alpha(x)w_n(x)+\beta(x)w_{n-1}(x). $$

**(x) Find $\alpha(x)$ and $\beta(x)$. Reason as to why the recurrence
relation is not linear.**

"I believe these were not too trivial for anyone!" Senn exclaimed, closing the
scribble book. "Also, it'd be great to know that many were introduced to new
stuff today, things that aren't already known. Indeed, polynomials do extend
beyond their elementary treatment and can prop up in the most unexpected
situations, such as on a chess board or MS Paint."

_The more you know, the more Oh,no!mials._

## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in).
