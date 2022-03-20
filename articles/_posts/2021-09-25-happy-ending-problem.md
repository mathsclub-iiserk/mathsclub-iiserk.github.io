---
layout: post
title: The Happy Ending Problem
author: Sayan Dutta
blurb: >
    When Carver asked, "What do we talk about when we talk about love?" Esther
    Klein replied, "Why, math riddles, of course!" While love at first sight
    has been omnipresent in the works of poets, writers and musicians, love at
    first math problem has always remained an understatement.
tags: article
katex: true
---


## Theorem
A mathematician’s love life is the most underrated phenomenon on earth.

### Proof

On one fine morning of 1933, a young Jewish lady, Esther Klein, brought
a puzzle she designed (and solved all by herself) to her dear friends, Paul
Erdős and George Szekeres. The apparently innocent looking puzzle just states
that given any five points on a plane no three of which lie on a straight line,
there must be four of them which form a convex quadrilateral. Now, a convex
quadrilateral is simply a 4-sided shape where all the turns along the boundary
are in the same direction. In other words, all its vertices point outwards.

{% include image.html 
    url="articles/2021-09-25/convex-concave.svg"
    width="600px"
    caption="Imagine walking along the boundary of these two figures, and
    notice that all the turns that you need to take for the convex polygon are
    right turns, in contrast to the other one where we have a left turn as well
    (marked in red)."
%}

Like excellent friends, Erdős and Szekeres immediately started working on the
problem, and very soon arrived at a solution. If the given five points form a
convex pentagon (a shape with five unidirectional turns), then any four points
will trivially form a convex quadrilateral; if the points are such that four of
them form a convex quadrilateral and another lies inside it, then we already
got the quadrilateral we wanted. Finally, if three of the points make a
triangle inside which lies the other two points, then we can draw a line
through these two inside points and argue that this line will intersect exactly
two different sides of the outer triangle (because it cannot pass through
another point as that will contradict the non-collinearity of the points).
Since there cannot be any other configurations, the puzzle is solved in all
glory.

{% include image.html 
    url="articles/2021-09-25/cases-n-4.svg"
    width="600px"
    caption="These figures illustrate all three possible cases."
%}

Soon after this, the friends generalized the problem and asked: What is the
least number of points we need on a plane to guarantee an $n$-sided convex
polygon for any given $n$?

Meanwhile, Esther and George fell in love with each other over this problem and
it ended with their marriage on June 13, 1937. Instead of wedding rings, these
two mathematicians decided to exchange a riddle for a change (well, they may
have exchanged a ring as well, but I don’t have any source to confirm that). It
is after this good news that Erdős went best-friend-mode and named the problem,
“The Happy Ending Problem”.


Shifting our focus to the mathematics again, the problem was solved by Erdős
and Szekeres by 1935 for the $n = 5$ case, and the answer to that is $9$. The
proof is quite similar to the last one; it just requires checking many more
cases. 

<br>

{% include image.html 
    url="articles/2021-09-25/n-5.svg"
    width="400px"
    caption="Here's a diagram to show that 8 points on a plane may be
    distributed such that no five of them make a convex pentagon. Try playing
    with this picture, and experimenting on how to draw pentagons using the
    points."
%}

Sadly, solutions for any other values of $n$ weren't easy to find using case
checking since the number of cases was quite large. However, in the same paper
where the $n=3,4,5$ solutions were published (note that the $n=3$ case is
trivial as any three points not on a straight line must make a triangle), the
genius of Erdős conjectured a formula that spits out the exact number of points
you need to guarantee a convex $n$-gon. And this conjectured formula was

$$ f(n) = 2^{n - 2} + 1, $$

where $f(n)$ is the minimum number of points required to guarantee a convex
$n$-gon. Later, in 2006, with some previous help from Szekeres, Lindsay Peters
published a paper with a proof (using a computer program) that for a hexagon
(case $n=6$), the least number of points required is $17$, hence providing more
strength to Erdős' conjecture. The proof of this case was finally formalised in
2017 by Filip Marić. 

Just a couple of years before this problem started being discussed, Frank
Ramsey introduced a pivotal theorem which, in very simple terms,
mathematically establishes the fact that absolute randomness is not possible,
i.e. any randomized structure will necessarily contain an orderly substructure.
When applied to this problem, this proves that given enough points on the
plane, it is impossible to avoid a convex $n$-gon for any $n$. In other words,
no matter how big an $n$ you choose, there is a corresponding finite $f(n)$
number of points which guarantees the existence of a convex $n$-gon for that
$n$. While Ramsey's work had already been published, the "Happy Ending
thinkers" weren't aware of it -- in search of a proof for their paper, they
ended up independently rediscovering it.

This was not all. In the same paper, Erdős also introduced a new way of
thinking about the problem: a convex polygon is just a sequence of line
segments whose slopes are either monotonically increasing (forming a _cup_) or
decreasing (forming a _cap_). If one can find a chain of $n$ points forming a
_cup_ or a _cap_, connecting the ends gives the desired $n$-gon.

{% include image.html 
    url="articles/2021-09-25/cup-cap.svg"
    width="600px"
    caption="A chain of points with a cap and a cup highlighted. The
    [Erdős–Szekeres theorem](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93Szekeres_theorem)
    guarantees that given a sufficiently large but finite number of points, one
    can always find a large enough cup or cap of $n$ points."
%}

Using this idea, he was able to bring the upper bound to a
not-so-tight estimate of

$$ f(n) \leq 4^n, $$

which is quite far away from the conjectured value of $2^{n - 2} + 1$,
especially when $n$ is large. But, that was all there was to this paper.


Just when we thought that innovations about this topic had almost halted, came
in Andrew H. Suk. What Suk did was divide the given set of points into two
categories -- subsets which are in convex positions to each other (known as a
hull), and those lying outside this structure (known as spikes).

{% include image.html 
    url="articles/2021-09-25/hull-spike.svg"
    width="500px"
    caption="An illustration of the hull and spike system for a large number of
    points."
%}

Using this classification, he was able to bring down the bound to an unbelievably close
approximation of 

$$ f(n) \leq 2^{n + 6n^{2 / 3} \log{n}}, $$

and finally, it seems, we are just a few steps away from settling the
conjecture and finding the happiest end to the Happy Ending Problem.


Unfortunately, none of the creators of the problem are alive today. Erdős
passed away in 1996, leaving behind a plethora of important conjectures and
thousands of dollars in the form of awards on solving these conjectures.

Szekeres and Klein both breathed their last on 28 August, 2005 at the same
nursing home in Adelaide, within just an hour of each other. While love at
first sight has been omnipresent in the works of poets, writers and musicians,
love at first math problem has always remained an understatement.

The rest of the proof is trivial, and left as an exercise for the reader.
<span style="float: right">$\square$<span>

<br>

## References
[1] Jungic, Veselin, [Introduction to Ramsey Theory: Lecture notes for
undergraduate course](http://www.sfu.ca/~vjungic/RamseyNotes/sec_ES2.html)


<br>

## About the author

Sayan Dutta is an undergraduate student of mathematics, interested in discrete
mathematics and vibrant patterns hidden in the simplest of structures. His
appreciation of beauty stems from his cinephile present, while his chess moves
are just nuances of perfection. He aspires to paint the world in the language
of mathematics and the blossoms of the silver screen.
