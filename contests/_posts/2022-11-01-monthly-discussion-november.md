---
layout: post
title: November - ODE to Joy
author: Sohom Gupta, Abhilash Saha, Kishan Saha
blurb: >
    Today, we explore the placid hymns of _An ODE to Joy_ through those that
    run the continuous world ...
tags: monthlycontest
katex: true
---


As wind whistled through the old oak, the hum of hummingbirds filled the woods,
the golden rays of the rising sun streamed over gentle cold waters, as the
cityscape saw the rise of dawn the cry of a fawn echoed in the fog laden air.
The world opened its arms to welcome a new life, well snuggled into the arms of
her exhausted, yet excited mother. That child, created through love, tears and
blood was breathing in the cool air, squinting at the kaleidoscope of the
outside world, at the sunlight flooding the ward floor. That child, named
Estelle, was born to Senn and Pura and there she was, in a moment of triumph,
in a cradle of undying warmth, as an ODE to joy!

Both were elated beyond any measure - despite having seen so much in their
lives; parenthood was as beautiful as the most elusive of ambrosia. It was no
wonder that Senn wanted to stream, even if for a short while; sharing his joys
with all in tow. His plans and thoughts were already laid out, assimilated into
a master-chart and beautified with the best of what he had seen.

"I-I am so happy today, everyone! Haha... I guess we knew that for a while but
it still feels so unbelievable - maybe this feeling is to stay! Today's stream
will be short hahaha - sorry you won't see Pura today, we will definitely
update you though.

"Anyways, as an ode to joy, we will begin today's session discussing ODEs! I
like how it fits today's theme, yeah it's kind of clever, really. Sooo, what
are ODEs again?"

An _Ordinary Differential Equation_ (ODE) is an equation that contains
functions in a given variable and it's derivatives (which should exist). An
example could be

$$
    \frac{d^2f(x)}{dx^2} + f(x) = 0,
$$

where $f$ is a suitable differentiable function that takes the single variable
$x$ as its argument. I expect some familiarity with these, and upon closer
inspection, the earlier example is just the Linear 1st order homogeneous ODE of
a simple harmonic oscillator with unit frequency. We shall try to deal with
linear ODEs for the most part since non-linear ODEs can become too complicated
to solve.

We solve a differential equation by integrating all the derivatives and
isolating our target function $f(x)$ - this might not always be possible but
sometimes it is, and that is all what we care about. We do care about new life
and new ideas as well! But let us not go too overboard today, right?

Sometimes, even a trial solution works. Can you try one out for the one given
above?

**(i) Show that $A\exp(ix)+B\exp(-ix)$ is a solution of the differential
equation above by explicitly computing.**

There are certain differential equations crucial in science. One is the
understanding of how a system evolves, in particular, parameters of the system
under given conditions. Consider a process that is approximately continuous in
time, where a parameter $p$ varies with time with a rate equal to its current
value in the system. The associated differential equation is

$$
    \frac{dp}{dt} = p.
$$

**(ii) Find a solution to the above 1st order ODE given the parameter $p$ had
an initial value of $p(t=0) = p_0$.**

However, certain processes in nature happen on a discrete time domain -
especially those associated with counting measures - such as binary fission of
bacteria in a culture. These are then represented by _difference equations_,
and we would have for a discrete time domain parameter $p$ varying as

$$
    \frac{p_{t+1}-p_{t}}{t+1-t}=p_t.
$$

Consider $p_{t=0}=p_0$. Such an equation can be solved analytically through a
set of recursive relations, from which any value $p_t$ can be figured out.

**(iii) Find a general solution of the above difference equation and compare
the growth rates of it and the associated ODE.**

While mathematically this disparity makes sense ($1$ is a large number),
physically this can be tricky to understand. The units in which $t$ is measured
can be arbitrarily shortened (1 nanosecond, 1 attosecond, 1 femotsecond,
...), which can go up to an order of $10^{-20}$ s! Does it still make sense
that both will have different growth rates? Think for yourself!

Now, while ODEs are pretty fun and ubiquitous - they are not always solvable
analytically. In those cases, we need to make certain approximations or even be
happy to just talk about the nature of the solution(s). Some algorithms in
particular, talk about an unique solution and presents a robust and easy method
to get to a reasonable estimate for them. These are called _iterative methods_.

Very similar to our _difference equations_, iterative methods consider a
sequence $\{y\}_n$ which converges to the true solution $y$ almost everywhere.
One such algorithm is attributed to Emile Picard and some other greats of his
time.

Given a 1st order ODE

$$
    \frac{dy}{dx} = F(x,y)
$$

with a continuously differentiable function $F$ on some compact domain
(Cartesian product of two intervals) which is bounded and Lipschitz continuous
admits a unique solution.

Boundedness and Lipschitz continuity are such that $\exists M,C\in\mathbb{R}$ and

$$
    \begin{align*}
        |F(x,y)|&\leq M\\
        |F(x,y)-F(x,y')| &\leq C|y-y'|\\
    \end{align*}
$$

Under these conditions, the solution is given by

$$
    y(x) = y(0) + \int_{x_0}^x F(t,y(t))dt.
$$

In principle, one begins with $y_0(x) = y(0)$ then uses this integral to obtain
$y_1(x)$ from $y_0(x)$ and so on till it converges.

One simple ODE can be represented as

$$
    \frac{dy}{dx}=y^2+1.
$$

Say the initial condition is $y_0(x) := y(0) = 0$. Then we have for every
$n\geq 0$,

$$
    y_{n+1}(x) := \int_0^x(y_n^2(x)+1)dx.
$$

**(iv) Find the general term for $y_n(x)$. Also, explicitly solve the ODE with
standard techniques. Check the convergence of the solution found using Picard's
algorithm with the fully analytic solution.**


Sometimes though, 1st order ODEs come coupled and cause issues. Consider a very
elementary coupled ODE problem

$$
    \begin{align*}
        \frac{dx}{dt} &= x + y,\\
        \frac{dy}{dt} &= y - x.
    \end{align*}
$$

Standard techniques of solving 1st order ODEs doesn't seem to work here because
of the inherent coupling of the two terms. If we try to forcefully eliminate
$x$ from the terms (which we can here), we get

$$
    \frac{d^2y}{dt^2}-2\frac{dy}{dt}+2y=0,
$$

a homogeneous 2nd order ODE acting like an oscillator with a continuous feed of energy.

Another way to deal with this is how computers often work under implicit
schemes - go matrix mode!

Let us rewrite the coupled equations of this 2D dynamical system as

$$
    \binom{\dot{x}(t)}{\dot{y}(t)} = \begin{pmatrix}
        1 & 1\\
        -1 & 1
    \end{pmatrix} \binom{x(t)}{y(t)}
$$

Define the transfer matrix as M and the vector as $\boldsymbol{X}$ to get

$$
    \boldsymbol{\dot{X}} = M\boldsymbol{X}.
$$

The solution to this problem comes from Putzer's algorithm. It is not too
difficult to show that the trial solution

$$
    \boldsymbol{X(t)} = e^{Mt}\boldsymbol{X(0)},
$$

where exponentiation of a square matrix $M$ is given by

$$
    e^M = I + M + \frac{1}{2}M^2+\frac{1}{3}M^3+\ldots.
$$

Here, $t$ is just a scalar so it just tags along. If one finds a suitable
general power $M^k$, it is easy to exponentiate the matrix.

**(v) Could you try solving the given 1st order coupled ODEs, at least to a
reasonable estimate?**

Here's where we should be done, and I should be going back to Estelle - but
let's add something in bonus!

You had the transfer matrix M, now time to find the fixed points. These are
points such that $\boldsymbol{\dot{X}(t)} = \boldsymbol{0}$. It is clear that
the solution for that is

$$
    x^* = y^* = 0.
$$

Now that we have a fixed point, it's time to look at the eigenvalues of $M$.
How do they look like? Are they positive? Negative? Imaginary? Complex? The
answer you get might strongly hint at the stability of the fixed point, _i.e._
whether a trajectory started near $(0, 0)$ will approach it, be repelled by it
or just orbit it!

Go ahead and think of this, while I get back to my baby!

## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in).
