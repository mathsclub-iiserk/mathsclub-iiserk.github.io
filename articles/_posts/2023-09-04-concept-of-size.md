---
layout: post
title: The Concept of Size
author: Aditya Dwarkesh
blurb: >
    _Some things in the world never fail to evoke a deep sense of awe from the
    human mind. Among other things, they may be the miracle of life, the
    vastness of the universe, and the existence of an uncountable set with
    measure zero ..._
tags: article
katex: true
---


Some things in the world never fail to evoke a deep sense of awe from the human mind. Among other things, they may be the miracle of life, the vastness of the universe, and the existence of an uncountable set with measure zero. There is not much that can be put into words regarding the experience of the first two; but in this article, I shall try, among other things, to express the significance of the third.

In mathematics, one often wishes to abstract out and make rigorous concepts which we otherwise fling around rather carelessly in average conversation. It may so happen that on occasion, multiple distinct ways of abstracting out a notion are unearthed. This happens to be the case when it comes to the idea of size; in particular, the size of any collection of objects; in particular, the size of a collection (or set) of numbers.

In this essay, we shall describe and observe the interplay of three different abstractions of our concept of size.

## Cardinality
We shall begin our survey with the second idea. It is almost blatant and straightforward: The size of a set equals the number of elements in it. You pick up a set and count the number of items in it; the idea is entirely grounded in the basic notion of counting.

More rigorously, we say that two sets have the same cardinality if there exists a one-to-one correspondence between their elements. This is clearly true of $A = \{1, 2, 3\}$ and $B = \{4, 5, 6\}$, and they both have cardinality 3; and clearly false of $C= \{7\}$ and $D = \{8, 9\}$. The cardinality of any finite set will be some natural number.

What of the set of natural numbers itself? It has infinitely many elements; its cardinality must be infinite. The funny thing is that its cardinality is exactly equal to the set of even numbers, even though it appears to have twice as many elements; this can be seen through the fact that they can be put in a one-one correspondence by the function $f(n) = 2n$; and we may put this down to one of the many quirks of infinity.

However, we are painting with strokes far too broad if we merely call their cardinality 'infinite'. Can we be sure that the set of natural numbers can be put in a one-one correspondence with any other infinite set?

It can be demonstrated that this is not the case; the set of real numbers has far too many elements for the naturals to handle, something first shown by Georg Cantor via his immortal diagonalization argument, which runs as follows:

Suppose that the set of real numbers can be enumerated. Then, in particular, every real $\{x: 0<x<1\}$ can be enumerated. Do so as follows:

$$
r_1=0.108357...
$$

$$
r_2=0.093492...
$$

and so on.
Define the element $r$ by taking the $n^{th}$ digit of the $n^{th}$ entry and adding $1$ to it (in case the entry is $9$, make it $0$). Since this number will disagree with each entry in the enumeration at the $n^{th}$ digit, it cannot be in the enumeration; we conclude that the set of real numbers cannot be enumerated.

Conventionally, we call infinite sets whose cardinality equals that of the naturals _countably_ infinite; and those whose cardinality equals that of the reals _uncountably_ infinite. The continuum hypothesis is an important problematic in axiomatic set theory, and states that there is no set whose cardinality is strictly between that of the naturals and the reals.

Two more important and perhaps counterintuitive examples of countably infinite sets are the integers (which, when arranged as $\{0, 1, -1, 2, -2,…\}$, can clearly be put in one-one correspondence with the naturals) and the rationals.

Let us show a little elaborately how the rationals are countably infinite, for they will turn out to be representatives of an important paradigm soon. The map $f(\frac{p}{q}) = (p, q)$ evidently puts $\mathbb{Q}$ in one-one correspondence with the Cartesian product $\mathbb{Z} \times \mathbb{N}$; further, we know that $\mathbb{Z}$ and $\mathbb{N}$ are each countably infinite. To complete the proof, we shall show that the Cartesian product of two countably infinite sets is also countably infinite.

Without any loss of generality, we shall prove that $\mathbb{N}\times\mathbb{N}$ is countably infinite. Let us represent its elements by the following matrix:

$$
\begin{pmatrix}
(1, 1) & (1,2) & (1,3) & \cdots\\
(2, 1) & (2, 2) & (2, 3)\\
(3, 1) & \cdots\\
\vdots\\
\end{pmatrix}
$$


We can index each element of this matrix with a natural number by running through its diagonals; that is, we first count (1, 1); then, (1, 2) followed by (2, 1); then, (1, 3), followed by (2, 2), followed by (3, 1); and so on. This provides the required one-one correspondence between $\mathbb{N} \times\mathbb{N}$ and $\mathbb{N}$, and concludes our proof of the rationals being countably infinite.

In this sense, the movement from the set of all rational numbers to the set of all real numbers is a veritable explosion; a mathematical Big Bang. Complete comprehension of the incredible increase in structural complexity is in itself a kind of sensory overload.

We have said that the set of real numbers is uncountable infinite. More is true: _Any_ interval of real numbers is uncountably infinite. Therefore, our first system of measuring size is incapable of much variegation in this situation; it assigns the same size to $(0, 1)$ and $(0, \infty)$. This is because it is only concerned with how perfectly two sets can 'talk' to each other; and the two mentioned above happen to be able to do that perfectly well, in spite of some clear differences; akin to how two very different people can communicate given only that they share a language.

## Measure

Our everyday notion of the word 'size' is entrenched with the concept of space. With cardinality, which maintains itself as a matter of simple counting, there is no such spatial association; but this is brought back with great vigor by the concept of measure.

In the simplest possible terms, the notion of measure is a generalization of the notion of length. The standard method of 'measurement' for the real numbers is called the Lebesgue measure; under it, the 'length' of any interval $[a, b]$ is the difference $(b-a)$.

In general, the length of an arbitrary set of real numbers is the 'minimum' length of intervals with which it can be 'covered'. (We say that a set is covered by a collection of intervals if it is a subset of their union.) More formally, we write, for $E\subseteq \mathbb{R}$, where $l(I_k)$ is the length of the interval:

$$
m(E)=\textrm{inf}\{\sum_{k=1}^nl(I_k) : (I_k)_{k\in\mathbb{N}} \hspace{2mm} \textrm{is a sequence of open intervals with} \hspace{2mm} E\subseteq \bigcup_{k=1}^\infty I_k \}
$$

This definition requires some unpacking. Consider, to begin with, the singleton set $\{0\}$. It can be covered by any interval of the form $(-\epsilon, \epsilon)$, where $\epsilon$ is some positive real number. Now, we want the length of the _minimum_ such interval. Suppose this length is $l>0$. But we can always cover $\{0\}$ with the interval $(-\frac{l}{4},\frac{l}{4})$, whose length equals $\frac{l}{2}<l$. Therefore, in conclusion, the measure of this set will be zero. We can reproduce this same argument for any finite union of singletons.

Now, using this definition, we can show that any countable set has measure zero. For let $S$ be a countable subset of $\mathbb{R}$, and enumerate its elements as $(s_1, s_2,…)$. Cover each singleton $\{s_n\}$ by an interval of the form $(s_n-\frac{\epsilon}{2^{n+1}}, s_n+\frac{\epsilon}{2^{n+1}})$, where $\epsilon$ is an arbitrarily small real number. The union of these intervals will cover the whole set $S$.

Now, the sum of the lengths of these intervals is $\sum_{n=1}^\infty2\cdot(\frac{\epsilon}{2^{n+1}})=\epsilon\sum_{n=1}^\infty\frac{1}{2^n}=\epsilon$ (it is a fact the reader may take for a given that the series $\frac{1}{2^n}$ sums up to unity).

But recall $\epsilon$ can be arbitrarily small; in other words, for every alleged measure $m(S)=l>0$, we can cover the set $S$ with intervals such that their length sums up to $0<\epsilon=\frac{l}{2}<l$, which would contradict the definition of measure (which, remember, is the _smallest_ sum of the lengths of the intervals with which the set can be covered). With this, we conclude that the measure of $S$ is zero.

This makes it clear that, unlike cardinality, the Lebesgue measure is blind to the differences between a finite set and an infinite but countable set; they all have measure 0.

On the other hand, unlike cardinality (again), the Lebesgue measure _is_ sensitive to the differences between sets which were all blanketed as uncountable; while $[0, 1]$, $[0, 2]$ and $[0, \infty)$ all have equal cardinality, their measures are 1, 2 and infinity respectively.

Since the set of rational numbers has measure zero, the set of irrational numbers must have measure equal to that of the real numbers—for the disjoint union of the rationals and the irrationals equals the real numbers. Now, when a statement is false on a set of measure zero, we say that it is _almost nowhere false_ (or _almost everywhere_ true). Since $\mathbb{Q}$ has measure zero, it is _almost everywhere_ true that a given real number is irrational; or, to put it another way, _almost every real number is irrational._ This measure-theoretic result gels well with the intuition germinated by the spectacular jump in cardinality (by virtue of the irrationals) from the rationals to the reals.

There is an interesting limitation to be accepted here, a kind of trade-off made by the notion of measure, which is in some sense due to the additional structure of spatiality inherent in it. It is that while _any_ set has a well-defined cardinality (whether or not we may be able to actually determine it), there exist certain _non-measurable_ subsets of the real numbers, that is, sets which do not possess a well-defined 'length'.

Such anomalous sets may be viewed as being reticent to converse with us in spatial terms; however, they do still have a well-defined cardinality (that is, they are uncountably infinite).

## Density
To reiterate, our measure-theoretic lens led us to the following conclusion: _Almost every real number is irrational._
Unbelievably enough, a twisted negation of this statement also happens to be true: _Every real number is almost rational._ Once we understand this, we can appreciate what makes this third notion of size necessary.

What does it mean to say that every real number is almost rational? Retaining the sense of spatiality in the notion of 'almost', we may repackage this as saying that any real number is _arbitrarily close_ to a rational number.

There is a highly effective one-two punch by which we may prove this proposition. First, we can show that there exists some rational number between any unequal pair of real numbers—say, $a$ and $b$. Second, we pinch the pair down to make the distance between them arbitrarily small; since there will always be a rational number between them, we can conclude that there will a rational number arbitrarily close to $a$ (or $b$).

Let $a$ and $b$ be the two real numbers, and suppose without any loss of generality that $a<b$. By the unboundedness of the naturals, there will be a natural number $n$ such that $n>\frac{1}{b-a}$.

Define M as the set of integers $z$ such that $z>an$. Since M is bounded below, it will have a least element; call this $m$. Thus, we have $m>an\iff \frac{m}{n}>a$. Furthermore, $m-1<an \implies \frac{m}{n}<a+\frac{1}{n}<a+(b-a)=b$. Thus, $\frac{m}{n}$ is a rational number between the two arbitrary reals a, b.

Any real number is only the slightest of movements away from some rational number. This is what associates a certain sense of largeness to the set of rationals; and we say that the set of rationals is _dense_ in $\mathbb{R}$.

It is even easier to see that the set of irrational numbers is dense in $\mathbb{R}$: To find an irrational number between $a$ and $b$, first locate a rational number $q$ between $\frac{a}{\sqrt{2}}$ and $\frac{b}{\sqrt{2}}$; then $q\sqrt{2}$ will be the required irrational between $a$ and $b$. (And so, counterintuitively, every real number is also 'almost' irrational.)

On the other hand, it is almost trivial that no interval of the form $[a,b]$ is dense in $\mathbb{R}$: Simply consider the real number $b+1$, which can be made no closer than the distance 1 to the set given. To put it in an even more painfully obvious form: It is not true that every real number is almost in the interval $[a, b]$.

It may be remarked that, thus presented, the notion of density only makes sense in the context of the parent space $\mathbb{R}$: We are concerned with what every _real_ number 'almost' is. This notion can be generalized to any arbitrary parent space $X$, and a question can be asked regarding what every element in $X$ 'almost' is. For example, it is an important theorem of real analysis that any continuous function on an interval is 'almost' a polynomial function (contrary to appearances); more concisely, the set of polynomials on $[a, b]$ is dense in the space formed by the set of all continuous functions on $[a, b]$.

## Conclusion

We have surveyed three distinct senses of the word ‘size’ in its application to sets.

1. Set-theoretic size: In this sense, ‘size’ is deprived of its spatiality, and it serves only to fix how well two different sets can communicate with one another.
2. Measure-theoretic size: In this sense, ‘size’ means length; it serves to fix how intimately coordinated a set’s elements are within itself.
3. Topological size: In this sense, ‘size’ fixes how deep a subset penetrates into its parent set; it serves to fix a subset’s relation to its parent set.

Let us reconsider some cases in which these senses of the word agree and disagree.

The paradigmatic example was $\mathbb{Q}$: As we have seen, it is large in the topological sense (since it is dense), but small in the measure-theoretic sense (since it has measure zero). As for the third modality, it is countably infinite; therefore, even though it has infinitely many elements and penetrates everywhere into the parent set by them, its length remains zero.

Next, consider the set $[0, 1]$. Even though its set-theoretic size is large (uncountably infinite), it is not dense and thus topologically small; its elements are not as coordinated as those of $\mathbb{Q}$ in the required manner. On the other hand, they are coordinated enough to give it a measure of one.

There are, however, certain constraints as well. As we have seen, any countable set will have measure zero. Therefore, we may say that being set-theoretically large is a _necessary_ condition for a set to be measure-theoretically significant.

However, this is _not_ a sufficient condition, as the much more unintuitive example of the Cantor set $\mathcal{C}$ shows. This is a subset of $[0, 1]$ constructed by iteratively deleting open middle thirds: First, one deletes the interval $(\frac{1}{3}, \frac{2}{3})$ from it to obtain $[0, \frac{1}{3}] \cup [\frac{2}{3}, 1]$. Repeating the process for each of the segments yields $[0, \frac{1}{9}] \cup [\frac{2}{9}, \frac{1}{3}] \cup [\frac{2}{3}, \frac{7}{9}] \cup [\frac{8}{9}, 1]$; and doing this infinitely many times yields the Cantor set in the limit.

{% include image.html 
    url="articles/2023-09-04/cantor_set.png"
    width="800px"
%}

If we take $[0, 1]$ as our parent set, then the Cantor set is topologically small (not dense) and also measure-theoretically small (has measure zero). What is unexpected is that it happens to be very large, set-theoretically: Indeed, it is an uncountably infinite set. Even though they are so numerous, the elements of $\mathcal{C}$ are too discordant and fail to link up to amount to anything spatially.

Finally, an example in which all three notions are in agreement: Consider the set of irrational numbers in the parent space $[0, 1]$. This is dense, has measure one, and is uncountably infinite. It is large in all three senses of the word.

All of this may appear to amount to nothing but a strange, inscrutable game. Under the guise of clarification, we take a word we know well and complicate it entirely, giving it multiple meanings which do not even do us the minimum dignity of agreeing with one another. Such is the case with mathematics: The greater the degree of rigor and clarity we strive for, the more abstract and confusing the situation becomes. As with life.


<br>

## About the author

Aditya Dwarkesh is an undergraduate student pursuing a BS-MS degree at IISER Kolkata, with an interest in mathematical physics.
He is also a writer. For more, you can visit his [website](https://adityadwarkesh.github.io/).
