---
layout: post
title: March - Leaps and Bounds
author: Sohom Gupta, Sayan Dutta
blurb: >
    Today, I shall present you with some problems which will show you that the
    most fundamental knowledge of mathematics we hold is key to solving many
    complicated or non-intuitive ideas.
tags: monthlycontest
katex: true
---

The stream begins at its due time, maintaining all the characteristic protocol.
Pura checks the desk; assured of all its belongings she turns around to Senn,
who has made himself comfortable on the couch behind. His being there is itself
an issue, nevertheless he is very impressive when invested. She would
definitely see to it.

"From today onward, you shall see me and Senn stream together. Well, it would
be 90% me and 10% my notebook. The viewership of this programme is increasing
by leaps and bounds, and all is possible due to the consistent support you all
have provided. As such, I shall present you today with some problems that shows
you that the most fundamental knowledge of mathematics that we hold is key to
solving many complicated or non-intuitive ideas. I can assure you that these
would be very easy to explain and solve, as long as you can get hold of the
reasoning behind the problems. Over all, I hope it is a fun ride like always!
Let's begin.

"Let me be clear in my statement, today's topic is a bit different from those
before in the sense that we won't be following a particular theme as such.
Instead, you will learn that often visualising a problem from a different
perspective will make the picture much clearer than before. Let us begin with a
nudge to our previous session.

Suppose we have a sequence of numbers defined as

$$
\begin{aligned}
    f_0 &= 0\\
    f_1 &= 1\\
    f_n &= \mu f_{n-1}+\lambda f_{n-2} \text{ }\forall n\geq 2
\end{aligned}
$$

These are a generalisation of fibonacci numbers, and the general term is derived as\\

$$
f_n = \frac{r_+^n-r_-^n}{r_+-r_-}\hspace{0.1 in}\text{where
}r_{\pm}=\frac{1}{2}\left(\mu\pm\sqrt{\mu^2+4\lambda}\right)
$$

where $n$ is any natural number, and $\mu,\lambda$ are non-zero real numbers.
Now say for example, we set $\mu = 7$ and $\lambda = -13$. Then we get
$\mu^2+4\lambda = -3<0$, and so $r_+$ and $r_-$ are both complex! This poses a
question,

**(i) In the sequence $\{f_1,f_2,f_3,\ldots\}$, how many complex numbers are
there? Write $\infty$ if infinitely many. Can you prove your result?**

"Did you get the answer? It's easier than it looks!"

Senn sat up, putting the magazine aside on the table. "Since this session is
all about these, you can put the problem that Albert asked me a couple years
ago Pura. It is a popular one, but some might not get the idea at first
sight."

"That seems reasonable. Well then, let's look at another one of these. Suppose
on the integer lattice of the Cartesian plane, we have a unit square with
vertices at the points (0,0), (0,1), (1,1), (1,0) in clockwise order
respectively. At each vertex there is a cricket, which can leap over any of the
three others in a symmetric fashion. Say the cricket at (0,0) leaps over the
one at (0,1) - it then lands on (0,2). Leaping over (1,0) lands it on (2,0) and
leaping over (1,1) lands it at (2,2).

{% include image.html
    url="contests/2022-03-14-crickets.jpg"
    width="500px"
    caption="**Figure 1.** The initial positions of the crickets are shown and
    the square is drawn in red. The three dotted paths are the leaps of the
    cricket at the origin over three of its neighbours."
%}

"Note that whatever be the direction of the jump or the position of the cricket,
it will always be an integer point (where both coordinates are integers) due to
the very nature of the jump and starting position. Initially they were sitting
of the vertices of a square of unit side and then at every step, **one**
cricket jumps over any one of the others.

**(iii) Can you give at least one sequence of steps such that at the end of it,
the crickets sit on the vertices of a square of side 2?**

**(iv) Is there a sequence of steps such that the crickets now sit on the
vertices of a square of integer side n, where n is any arbitrary integer
greater than 1? Could you prove your answer, whether yes or no?**

"You should note that the solution to this problem isn't apparently rooted in
the permutations of the various possible steps, but somewhere else. Can you
find it?"

Pura began going through her scribble-book, trying to check back on the things
she had planned. There could be a large list of all such problems, simple yet
cleverly disguised. She started on her next problem, but it was Senn's turn.

"Pura's third problem is pretty standard, so I'll tweak it a bit. There is a
finite series of lightbulbs arranged along a straight line. Each bulb has 3
possible states: **Off** (O), **Dim** (D) or **Bright** (B). Initially all
bulbs shine bright. Now an user has the following three valid operations in
hand.

- Change $B\to O$.
- Change $D,O\to O,B$ in left to right order.
- Change $B,O\to D,B$ in left to right order.

"The user is free to go on for as long as he/she likes carrying out one
operation after the other. But can he/she go on forever?

**(v) Show that the user will run out of valid operations after a finite number
of steps.**

"All of these problems can be represented visually, which might prompt you to
work with examples just in case." Senn went back to the couch and plopped on it
soundly. "But there can be problems very complicated, in fact, really
difficult - which become almost trivial based on the questions we ask. For
example, we can often easily compute the limit of a function, but having to
prove the same can be tricky. In some other cases, computation is the difficult
one while the proof is easier than you think. Didn't you put up something
similar, Pura?"

"Yeah, I remember it. The first time I saw it, I was stumped as well due to
its wording, so I'll try to explain it properly.

"Let us define something called an _Random Sum_. It is a sum where the terms
depend upon a random choice by the user. The expectation value of such a sum is
calculated by something known as **Wald's Lemma** given we know the probability
distributions from which the terms are drawn, but we will ignore that for
today. We will consider uniform distributions where the user can choose any
value with equal probability. An easy example is:

$$ \sigma = \sum_{i=1}^{N}\chi(i) $$

where $\chi(i)$ can take any integer value in the set $\{1,2,3,\ldots,i-1\}$
uniformly. Clearly, $\sigma$ may be different each time you calculate the sum -
you can check by trying to programme the sum in any programming language. Now
consider two functions that go as follows:

- $\Gamma(n)=1+\frac{200}{\log_2{n}}$
- $\chi(n) = |p_1-p_2-1|$ for two random primes $10^n>p_1>p_2>1$ such that
  $p_1-p_2<n$. If there are no such primes then $\chi(n)=1$.

"This should be pretty clear to all. $\Gamma$ is fully deterministic, while
$\chi$ is a random variable which draws two **distinct** primes at random such
that their difference is less than the argument and they are bounded by $10^n$,
and gives the value $|p_1-p_2-1|$. Now consider the infinite sum

$$ \tau = 1+\sum_{n=2}^{\infty}\Gamma(n)\chi(\Gamma(n)) $$

**(vi) Given any choice of the random primes for each and every term in the
sum, will it converge to a finite value? Prove if yes. If not, show a case
where it shall not converge to a finite value.**

"Do you want a hint? All I would say is that the answer lies in the underlying
behaviour of the given function/random variable. You would probably be
surprised when you witness how easy it is to get fooled by such a morbid
looking sum.


Since we're almost at the end," Pura sat up, de-stressing her shoulders, "let
us put one last problem for those who have cleverly found their way across
these simply nasty ones. The last problem will also invoke a similar idea, and
will be a fun exercise for those who got it. If you didn't, nothing to be sad
about, _for good times shall come_."

**(vii) A k-length partition of a positive integer $N$ is defined as a
decreasing sequence $\{a_1,a_2,a_3,\ldots,a_k\}$ (not strict), such that
$a_1+a_2+\ldots+a_k=N$. Show that the number of $r$-length partitions is the
same as the number of partitions with $a_1=r$.**

"Good times are here!"

Pura turned back to see Senn (who had sneaked out in the middle) back with two
packets of dessert; a wide grin on his face.


## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in).
