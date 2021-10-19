---
layout: post
title: September - Inception
author: Sohom Gupta
blurb: >
    Today I come to you with some ideas that are fairly easy, yet provide some
    pretty insight into the wonderful universe of mathematics. These include
    two very popular functions one uses in algebra: the floor and the
    fractional part.
tags: monthlycontest
katex: true
---

Pura, also complimented as the 'Moon Rose' for her gentle yet pallid features,
sits near the platform contemplating her actions for today. It is fairly recent
that she has decided to realize her wish of making mathematics simple,
interesting yet sufficiently challenging for folks that behold its elegance.
From dissonance to delirium would her notes graze a myriad of human minds, and
establish contentment.

The broadcast begins. Pura quickly glances at her watch assuring herself of her
impeccable plans for the evening. A quick smile lights up her face; she inhales
deeply. Let it be a joy ride!

"Today I come to you with some ideas that are fairly easy, yet provide some
pretty insight into the wonderful universe of mathematics. These include two
very popular functions one uses in algebra, the floor and the fractional part."

"The floor function, also called the box function $[\cdot]\colon \mathbb{R} \to
\mathbb{R}$, sends $x$ to the integral part of its real argument. The other one
is the remainder, or the fractional part of the argument, i.e. $\\{x\\} = x -
[x]$. While it is noteworthy that the box function takes only integer values
..."

**(i) Can you find the range of values that $\\{x\\}$ can take when the input is real?**

Pura looks back at her scribble book, realizing with a gasp how she has fallen
prey to the contagion of terrible handwriting. "Well," she thinks, "no use
crying over split milk. So if we are fine with that," she continues, "let's
move on."

"Today we shall fidget with these two functions, trying to see how they work.
Let’s add them first. Oops, $[x] + \\{x\\} = x$, so that’s no fun. Let me
scale the latter with some real constant $b \in \mathbb{R}$. Then, we define
the following function"

$$ f_b\colon \mathbb{R} \to \mathbb{R}, \qquad f_b(x) = [x] + b\{x\}. $$

"If you look at these functions' graphs, you would see that both the floor and
the fractional part functions are discontinuous. But they do make nice patterns
on the Cartesian. I want you to vary $b$ over all reals and check what I call
the three pillars of a good function - **injectivity**, **surjectivity** and
**bijectivity**; and I’m sure these terms need no explanation."`

**(ii) For what values of $b$ is $f_b$ injective, surjective and bijective
respectively? Also is there any set on which $f_b$ is not a _good_ function?
Try to prove what you observe.**

"If you’re done with this, you can possibly see some symmetry in how the domains
(of $b$) are arranged on the real number line. Nevertheless, we desire for
something more beautiful to connect the behaviour of $f_b(x)$ over the real
domain."

"Most of you must be aware of invertible functions. These functions are those
that can both be mapped from $x \mapsto f(x)$ and $f(x) \mapsto x$."

**(iii) Which pillar guarantees a _good_ function to be invertible?**

Pura sits upright and shrugs her shoulders on stream - her chair isn’t the most
comfortable thing in the world. She would probably need to complain; but then
again, it is once a month. Her weekly schedule is far from taxing so taking a
day off after a stream doesn’t sound too bad.

"The last one should be easy, right?" she grins, while imparting a neat torque
to the ballpoint. "Now we will be looking at some more patterns. As we should
know, inverses come in pairs - them being the left and the right inverse. Of
course for an invertible function, both are the same. But for other categories
of good functions, they might have only one of these, maybe even none, who
knows? Well I want you to figure out the following."

**(iv) Suppose a function is only injective. Find out which inverse it might
have if it is invertible. Keep in mind the domain and codomain of $f$ are set
to $\mathbb{R}$ and you can’t change them!**

**(v) Suppose a function is only surjective. Do the same chore as in (iv) and try
to prove your results for both.**

"Well, once you're done with these, we will do a small check of whether
left/right inverses of $f_b$ exist over a given domain for $b$. For this, first
draw a real number line.  Now, we will denote the absence of something by $0$
and the presence of it by $1$, just like the Boolean bits; we'll call them
counter values. Now say that if over a given set (of values for $b$) the left
inverse exists and the right doesn't.  Then we write $10$ over it, where the
left digit stands for the counter value of the left inverse and the right digit
stands for the counter value of the right inverse.  As an example if for $b \in
(−2, −1)$, $f_b$ has only a right inverse and not a left inverse, then we will
write $01$ over the part of the real line between $−2$ and $−1$. That's
everything we need to do.  After you have written them down over all the
required sets/points, start from the extreme left and note down the numbers you
have written one after the other while moving towards the right (e.g. $01$ then
$00$ then $10$ and so on ...)."

**(vi) Between any two such adjacent numbers, at least how many digits have
changed? At most how many digits have changed?**

"If you have got the answer to **(vi)**, then you must be wondering whether the
pattern has a name. Well it is called the Gray code, and is used to order cells
while representing Karnaugh Maps/KM (search it up if you're not aware). Well,
this was just a nice thing I found out, so why not share with you all? Now if
you ask why the Gray code is followed religiously by the inverses here, I
shan't answer you. I would rather task you to think this one out."

**Think:** Suppose that a function $h_b\colon \mathbb{R} \to \mathbb{R}$ varies
with some real constant $b$ linearly. Given that you vary $b$, can there be two
adjacent intervals that share a point such that the function is injective on
one and surjective on the other. Or maybe it is bijective on one and isn't a
good function on the other? How would the function have to behave for such a
thing to happen and break the Gray code that we built?

"Oh! And before I go," Pura retorted, "let us try to gain some satisfaction by
visualising something incredible (TW: vertigo). Open up Desmos, and there is
no favouritism, and plot the equation

$$ r = [\theta] + b(\theta - [\theta]). $$

which you would type as `r = floor(theta) + b(theta − floor(theta))`. This is
just the polar form of the equation we were fidgeting with all the time. Change
the grid to a polar one, choose a colour setting of your choice, set the $\theta$
range from $−100\pi$ to $100\pi$ and the $b$ range from $−100$ to $100$. Zoom
out till you can see the whole thing, let the slider run on auto and behold the
wonderful patterns on your screen!"

## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in), with the subject
_Monthly Contest: September_.
