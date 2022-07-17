---
layout: post
title: Going around in circles - Counting circular permutations with repeated objects is not as easy as it looks!
author: Swastik Patnaik
blurb: >
    So the other day I had a quiz on permutations and combinations. Easy stuff
    right? We have all heard the formula for the number of permutations of _n_
    objects around a circle; _(n - 1)!_ of course! Let us first take a look at
    why this is so ...
tags: article
katex: true
---


So the other day I had a quiz on permutations and combinations. Easy stuff
right? We have all heard the formula for the number of permutations of $n$
objects around a circle; $(n-1)!$ of course! Let us first take a look at why this
is so.

The number of ways to arrange $n$ objects in a line is clearly $n!$. The only thing
that is different in a circle is that since a circle is cyclic, the starting
point does not make any difference. Thus the $n!$ arrangements in a line are
split into equivalence classes depending on the starting point, which are of
course disjoint. Each arrangement has $n$ equivalent arrangements, depending on
the starting point. Thus we have $n! / n = (n - 1)!$ different arrangements for
objects arranged in a circle.

And permutations where objects are repeated? No biggie, it's

$$ \frac{n!}{n_1!\cdot n_2!\cdots n_k!}, $$

where $n_1, n_2, \dots$ are the number of objects of the first kind, second
kind, etc, because we have $n!$ arrangements in the line, out of which $n_1$
objects of the first kind can be permuted in $n_1!$ ways which would still be
the same arrangement, $n_2$ objects of the second kind can be permuted in
$n_2!$ ways, and so on.

What if we combined the 2 problems, permutations around a circle with repeated
objects? Still doesn’t seem like a difficult proposition, does it? One would
logically think it to be 

$$ \frac{(n - 1)!}{n_1!\cdot n_2!\cdots n_k!}, $$

especially if we look at the logic behind both the formulae: $(n - 1)!$ ways to
arrange around a circle, out of which $n_i$ similar objects can be permuted in
$n_i!$ ways; seems intuitively correct.

Turns out ... it's not. Or more accurately, not always.

<br>

[Read the full article here]({% link assets/documents/articles/2022-03-14/going-around-in-circles.pdf %})

<br>

## About the author

Swastik Patnaik is a student of IISER Mohali.
This particular article placed second in our [Article Writing Contest,
2022](https://www.iiserkol.ac.in/~maths.club/events/2022/03/14/article-writing-contest.html).
