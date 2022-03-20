---
layout: post
title: February - Progression
author: Sohom Gupta
blurb: >
    Today, we'll explore an idea that involves something that even a non-math
    person might have encountered: the Arithmetic Triangle _a.k.a_ Pascal's
    Triangle!
tags: monthlycontest
katex: true
---

A storm is to hit the town, the wind has picked up and barometers have dropped.
However, a thunderstorm is more likely to provide the denizens some relief from
the sweltering summer heat. Pura gets ready for today's session, glancing a
last time over the feedbacks from the first. _A bit more user-friendly,
huh?_ Seems legit; she didn't want to alienate anyone with unnecessary jargon -
looking at games or patterns felt better.

The stream begins as usual.  Pura gets back her composure, and begins.

"I received a lot of nice feedback on these sessions - it was definitely very
helpful and encouraging. To step up my game as per your comfort, I fished
through some old papers and came across an idea you might like. This involves
the usage of something even a non-math person might have encountered, the
Arithmetic Triangle _a.k.a_ Pascal's Triangle!

Pascal's Triangle is definitely a very well-known pattern among most, if not
all. You take two elements on a row, add them to get the number between them on
the next row. Just by iterating this process infinitely, and making sure the
borders of the triangle are all $1$'s, you can generate the entire structure.
It has several properties, like the numbers on a row being binomial
coefficients, or the fact that sum of all numbers on row $k$ yields $2^{k-1}$.
Today, we shall look at some more interesting features of the Pascal's Triangle -
but in the form of the Pascal Matrix!"

{% include image.html
    url="contests/2022-02-16/pascal_triangle.png"
    width="500px"
    caption="**Figure 1.** The Arithmetic Triangle as drawn by Pascal in his
    _Traité du triangle arithmétique_, 1665."
%}

{% include image.html
    url="contests/2022-02-16/pascal_triangle_modern.png"
    width="500px"
    caption="**Figure 2.** A modern version of Pascal's Triangle. _Image
    courtesy:_
    [Alisa
    Bajramovic](https://dev.to/alisabaj/solving-pascal-s-triangle-in-javascript-4e59)"
%}

Pascal's Matrix is basically Pascal's Triangle written in a left justified
form. Since Matrices can't be technically infinite, we will just take a
truncated version of Pascal's Triangle, say up to the $n$-th row. Then
our corresponding matrix would look like

$$ L_n = 
\begin{pmatrix}
1 &  &  &  &  & & &\\
1 & 1 &  &  &  & & &\\
1 & 2 & 1 &  &  & & &\\
1 & 3 & 3 & 1 & & & &\\
1 & 4 & 6 & 4 & 1 &  & & \\
. & . & . & . & . & . &  &\\
. & . & . & . & . & . & . &\\
1 & n & . & . &. & . & n& 1
\end{pmatrix}_{n\times n}
$$

This might seem to not look like a matrix, but the blank spaces are basically
zeroes. A more formal look is

$$ L_n = 
\begin{pmatrix}
1 & 0 & 0 & 0&0  &0 &. &0\\
1 & 1 &0  &0  &0  &0 &. &0\\
1 & 2 & 1 &0  &0  &0 &. &0\\
1 & 3 & 3 & 1 &0 &0 &. &0\\
1 & 4 & 6 & 4 & 1 &0  &. &0 \\
. & . & . & . & . & . & . &.\\
. & . & . & . & . & . & . &.\\
1 & n & . & . &. & . & n& 1
\end{pmatrix}_{n\times n}
$$

although it is not as neat as the previous one. Note that every row of $L_n$ is
exactly equal to the corresponding row in Pascal's Triangle."

"I shall also ask you to start counting the rows and columns from zero, not
one.  Have you ever written codes in any programming language? Then you would
have seen that indexing if a 2D array/matrix is not done from (1,1), but rather
from (0,0). So the first row of $L_n$ would be row zero. And the second row,
fifth column would be (1,4) - basically subtracting $1$ from whatever the row
and column numbers are. If you go about this way, the (i,j) entry of $L_n$ is
given by

$$ (L_n)_{ij}=\begin{cases} 
      \binom{i}{j} & i\geq j \\
      0 & j>i 
   \end{cases} $$

which is _the number of ways of choosing $j$ different objects from $i$
different objects_"!


{% include image.html
    url="contests/2022-02-16/add_diagonals.png"
    width="500px"
    caption="**Figure 3.** Joining the diagnoals of the Pascal Matrix."
%}

Pura's eyes gleamed as she presented her next work. "Now, let's see a very
interesting property of this matrix. What if we join the diagonals of the
triangle (**Figure 3**)? We do get a sequence of numbers that go as
$1,1,2,3,5,8,13,21,\dots$. This is the [Fibonacci
sequence](https://en.wikipedia.org/wiki/Fibonacci_number)! It is defined as

$$ \{F\}_n=\begin{cases} 
      F_1 = 1\\
      F_2 = 1\\
      F_n = F_{n-1}+F_{n-2} & n\geq 2\\
   \end{cases} $$

Let me help you out a bit. You can write

$$ F_n = \frac{\phi^n-\psi^n}{\phi - \psi} = \frac{\phi^n-\psi^n}{\sqrt{5}} $$

where $\phi = \frac{1+\sqrt{5}}{2}$ and $\psi=\frac{1-\sqrt{5}}{2}$ are the
roots of the equation $x^2=x+1$. How do you get this equation? Just take the
limiting ratio $F_n:F_{n-1}=F_{n-1}:F_{n-2}=\ldots=x$ and substitute it
appropriately in the recursion relation. Done!"

"Now, we shall try to see such sequences in higher powers of the Pascal Matrix.
Consider the square of $L_n$, doing it diligently will make you arrive at

$$ L_n^2 = 
\begin{pmatrix}
1 &  &  &  &  & &\\
2 & 1 &  &  &  & &\\
4 & 4 & 1 &  &  & &\\
8 & 12 & 6 & 1 & & &\\
. & . & . & . & . &  & \\
. & . & . & . & . & . & \\
2^n & n2^{n-1} & . & . & . & 2n& 1
\end{pmatrix}_{n\times n}
$$

We have the general term

$$ (L_n^2)_{ij}=\begin{cases} 
      2^{i-j}\binom{i}{j} & i\geq j \\
      0 & j>i 
   \end{cases} $$

Joining the diagonals gives us the sequence $1,2,5,12,29,\ldots$ (try to work
this out, similarly to _Figure 3_). If the Pascal one gave rise to the
Fibonacci sequence, what does the square of it give rise to?"


**(i) What is the recursive relation of this sequence?**

**(ii) Assuming that this sequence is denoted by $\\{G\\}\_n$ and that
$G_n:G_{n-1}$ converges, find out the general term $G_n$ in exact/closed
form.**

Suddenly, there is chaos in the hallway behind the studio. Pura tries to ignore
the noise - but she hears footsteps getting louder, until the studio door is
shoved open.

It was Senn. "Why are you here?" she exclaims.

"What do you mean?" Senn snaps, irritated. "You promised you would come back
before the storm hits."

"Well I did... but I have to do my job! Just go back, cook something for both
of us, and we're done, right?" she tries to reason.

"Nah it was your turn today." he has a malicious grin. "Go cook, I'll do the
rest for ya."

"Heh. If I let you do this for 1 minute I'll lose all my viewers. Aren't you
making like, 50 different completely illegible breakthroughs
everyday?"

"For human standards, yes. Anyways, what are you showing them?" Senn peeks at
her scribble note. "Ah, those are Pe-"

"Hushh! It's their task to figure it out!" she sneers at him. "Stop being a
killjoy - as it is you come back home once in a while."

"Yep, lot's of work now - have to take a break from the hectic routine. Let me
sit here for a while, kay?" Senn eases himself onto an empty chair. "Won't you
ask them the same for higher powers?"

"Yup." Pura continues. "Now we shall look at higher powers of Pascal's
Matrix. Suppose if you take the cube of $L_n$, or the fifth power, and then add
the diagonals - what sequences will you get?

"Let me help you with this one a bit. Consider the matrix $L_n^k$, where $k$ is
any natural number. Then the general entry is given by

$$ (L_n^k)_{ij}=\begin{cases} 
      k^{i-j}\binom{i}{j} & i\geq j \\
      0 & j>i 
   \end{cases} $$

If you sum up the diagonals of this matrix, what sequence will you get? Note
that the first term will always be $1$. Let me help you with an example again.
If you sum the diagonals of $L_n^3$, you shall get the sequence
$1,3,10,33,109,\ldots$. Now can you find the pattern as you **progress**
through higher and higher powers of the matrix?"

**(iii) Find the recursion relation of the sequence derived by summing diagonals of $L_k^n$.**

**(iv) Assuming the same criterion as in Problem (ii), find out the general term of this sequence.**

"These are pretty standard sequences but boy, oh boy are they beautiful!"
exclaims Senn after Pura is done. "We can try to complicate things more by
taking skewed diagonals along any of the powers but eh, not really suitable for
a stream. Maybe keep them for grad school haha! Pura tries to makes things seem
more appealing than they are, so that people are more engaged."

"What about myself?" she chuckles, cracking her fingers.

"Well,you're already too appealing, don't need those stuff you got from Sewa."


## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in).
