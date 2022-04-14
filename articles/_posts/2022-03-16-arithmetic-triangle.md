---
layout: post
title: "The Arithmetic Triangle: A Guidebook to Math"
author: Sohom Gupta
blurb: >
    "_This Table has truly exceptional and admirable properties; for besides
    concealing within itself the mysteries of Combinatorics, it is known by
    those expert in the higher parts of Mathematics also to hold the foremost
    secrets of the whole of the rest of the subject._" - James Bernoulli
tags: article
katex: true
---

The _Arithmetic Triangle_ is one of the most simple yet beautiful constructions
in mathematics. Frequently called as Pascal's Triangle, the history of it dates
back to centuries before Pascal's work. Indian mathematicians like _Pingala_
and _Varāhamihira_ had ideas of generating binomial coefficients via
the additive identity

$$ \binom{n}{r}=\binom{n-1}{r}+\binom{n-1}{r-1} $$ 

as well as the Jain mathematician _Mahāvīra_ in his revamped, modern
representation of binomial coefficients via factorials. It was also known
independently in other parts of the world; called the _Khayyam Triangle_ in
Iran, _Yang Hui's Triangle_ in China (to this date) and _Tartaglia's Triangle_
in Italy. Nevertheless, in his treatise _Traité du triangle arithmétique_,
Pascal gave a mathematical treatment like never before [[1]](#references).


{% include image.html 
    url="articles/2022-03-16/pascal_triangle.png"
    width="500px"
    caption="**Figure 1.** The Arithmetic Triangle as constructed by Pascal in
    his _Traité du triangle arithmétique_, 1665."
%}

He presented us with 19 _consequences_/properties of the Arithmetic Triangle,
as well as many lemmas and fields of usage of the same. These include the
inclusion of chance based two player games that involve the transfer of
money/shares [[2]](#references). He also talked about the its use in binomial
expansions and combinatorics, ones which are more common to the general math
student. However, ignorant would be the mathematician's mind that refuses to go
beyond this and explore the diverse, apparently unrelated corners of
mathematics connected by this simple construction.

_What is the worth of learning something that you can look up on the
net?_ - Sohom Gupta.

We shall therefore delve into some of the lesser known ideas surrounding the
Arithmetic Triangle. A bit of focus is all you need to realize the kaleidoscope
of mathematics imbibed into this construct.


## The Pascal Matrix

Mathematically formulating any pictorial dataset may not be trivial, but for
Pascal's Triangle, it is easier than expected. Pascal's Matrix, to the author,
is the best way to let us study it completely, to any general degree. So let's
define it quickly; note that there can be many versions of the matrix but we'll
look at the simplest one, the lower diagonal Pascal Matrix $L_n$:

$$
L_n = 
\begin{pmatrix}
1 &  &  &  &  & &\\
1 & 1 &  &  &  & &\\
1 & 2 & 1 &  &  & &\\
1 & 3 & 3 & 1 & & &\\
. & . & . & . & . &  & \\
. & . & . & . & . & . & \\
1 & n & . & . & . & n& 1\\
\end{pmatrix}_{(n+1)\times (n+1)}
$$

where the blank spaces are all zeroes. This resembles an inclined plane, but
the ride down it is bumpy with all the $1$'s pointing up! At least all rows of
the matrix correspond to the rows of Pascal's Triangle (_except the zeroes,
which got Thanos snapped_). We have

$$
(L_n)_{ij}=\begin{cases} 
      \binom{i}{j} & i\geq j \\
      0 & j>i 
   \end{cases},
$$

where counting of rows and columns start from zero (**point to be
noted!**).

## Eigenvalues and Eigenvectors

The lower Pascal Matrix $L_n$ has determinant $1$, as the determinant of a
lower triangular matrix is just the product of its diagonal elements. Its
eigenvalues are the solutions of

$$
\text{det}(L_n-\lambda I_n)=(1-\lambda)^n=0
$$

which gives $\lambda = 1$ ($I_n$ is the $(n+1)\times (n+1)$ Identity matrix - did you
get it?).

**The diagonal elements all being $1$ makes $L_n$ a unitriangular matrix, and
therefore _unipotent_ [[3]](#references), _i.e_, $L_n-I_n$ is nilpotent, having
the null matrix as a higher power.** (_Non-mathematicians, don't work yourself
up.  This is the jargon we deal with all day :/_).

An eigenvector $v_n$ of $L_n$ would thus satisfy $L_nv_n=v_n$. Say we have

$$
v_n=
\begin{pmatrix}
x_1\\
x_2\\
x_3\\
. \\
. \\
x_n\\
\end{pmatrix}_{n\times 1}
$$

A dedicated solution of the eigenvalue problem (_which is just equating the
elements of the left and right matrices_) would set $x_1=x_2=\ldots=x_{n-1}=0$.
This is an interesting property of unipotent triangular matrices like $L_n$ -
the set of linearly independent eigenvectors has a single element.

_Imagine a $40\times 40$ Hamiltonian that has only one eigenvector. It's
actually a treasure for Physics students tasked with calculating the Energy
Eigenvalues and Eigenstates._

## Higher Powers and Hypercubes [[7]](#references)

_Ok, that reference is cheeky; not that it matters._

Higher powers of the Pascal Matrix follow an interesting pattern. Note that,
taking $i\geq j$

$$
(L^2_n)_{ij}=\sum_{k=j}^i(L_n)_{ik}(L_n)_{kj}=\sum_{k=j}^i\binom{i}{k}\binom{k}{j}=\sum_{k=j}^i\binom{i}{j}\binom{i-j}{k-j}=\binom{i}{j}2^{i-j}
$$

In fact, we can generalize this easily to higher powers via induction (_as
opposed to deduction)_, arriving at

$$
(L^k_n)_{ij}=k^{i-j}\binom{i}{j}
$$

for all $k$ among naturals [[4]](#references), [[5]](#references). The
particular case for $k=2$ is very interesting.

$$
H_n = 
\begin{pmatrix}
1 &  &  &  &  & &\\
2 & 1 &  &  &  & &\\
4 & 4 & 1 &  &  & &\\
8 & 12 & 6 & 1 & & &\\
. & . & . & . & . &  & \\
. & . & . & . & . & . & \\
2^n & n2^{n-1} & . & . & . & 2n& 1\\
\end{pmatrix}_{(n+1)\times (n+1)}
$$

I call it $H_n$ as the $(i,j)$ entry in it is precisely the number of $j$
dimensional Hypercubes on the boundary of an $i$ dimensional Hypercube. Don't
know what a hypercube is? They are the family of polytopes given by (Point,
Line Segment, Square, Cube, Tesseract, ...), basically the $[0,1]^n$ subset of
$\mathbb{R}^n$. Every hypercube has smaller hypercubes on its boundary, _e.g._
cubes have points, line segments and squares on its boundary, often referred to
as vertices, edges and faces. Remember $V-E+F=2$ for a cube? Well, now you just
need to check whether

$$ (H_n)_{30}-(H_n)_{31}+(H_n)_{32}=2 $$

and it is! In fact, just by looking at the pattern of numbers in $H_n$, we can
even extend Euler's formula for the hypercube family to higher dimensions. Also
note that while you'd get $2^r$ when summing the $r^{th}$ row of the Pascal
Matrix, you'll get $3^r$ for this _Hypercube matrix_. It is easy to see how
higher powers behave.

Before moving on, do note that $L_n^k$ is always unipotent, _i.e._ has all
eigenvalues equal to unity.

## Recurrence Relations

_Recurrence relations are relations that recur_. By the way, there's a way to
retrieve Fibonacci numbers from the Pascal Matrix! Indeed, looking closely into
the pattern in **Figure 2** and formulating it via matrix definition gives us
this popular equality

$$ F_n=\sum_{r=0}^{\left\lfloor\frac{n}{2}\right\rfloor}\binom{n-r}{r} $$

We describe the Fibonacci numbers as $F_0=0$, $F_1=1$, $F_n=F_{n-1}+F_{n-2}$
for $n\geq 2$. Did you know that the ratio $F_{n+1}:F_n$ tends to the **Golden
Ratio**?

_Life is full of surprises, ain't it? Everytime you see it
on your favourite flower, do make a prayer to the Arithmetic
Triangle._

Such a discovery is exciting, but how about more? What if we apply the same diagonal addition on powers of $L_n$?

{% include image.html 
    url="articles/2022-03-16/add_diagonals.png"
    width="400px"
    caption="**Figure 2.** Diagonal summation to obtain Fibonacci numbers from
    Pascal's Triangle. Image courtesy: [Wikipedia/Pascal's
    Triangle](https://en.wikipedia.org/wiki/Pascal's_triangle)"
%}

You'd quickly see that the same process applied on $H_n$ will give us the sequence

$$ 1,2,5,12,29,70,169,\ldots $$

Wait. This can be generalized by $G_0=0, G_1=1$, and

$$ G_n=2G_{n-1}+G_{n-2} $$

for $n\geq 2$! These are called Pell numbers, and they satisfy the equality

$$ G_n=\sum_{r=0}^{\left\lfloor\frac{n}{2}\right\rfloor}2^{n-2r}\binom{n-r}{r} $$

If you move further and calculate the diagonal sums of say, $L^k_n$, you'll
only come across terms of the sequence $a_0=0$, $a_1=1$ and
$a_n=ka_{n-1}+a_{n-2}$. These are called Fibonacci
k-sequences [[6]](#references).

_What can you say about the ratio $a\_{n+1}:a_n$ as $n$ tends to infinity? May
not be golden, but shall certainly glitter._

## Other niceties

In chess, a rook moves either vertically or horizontally (**exclusive** OR). It
can move from 1 square to as many squares as possible in either direction
without leaving the board. But if one were to take a chessboard and find out
the number of distinct paths a rook placed at a corner can take to another
square (without any back-tracing), where to look but the Pascal's
Triangle!

{% include image.html 
    url="articles/2022-03-16/rook_paths.jpg"
    width="300px"
    caption="**Figure 3.** Number on a square is the number of distinct paths
    the rook can take to reach there. Note that it coincides with Pascal's
    construction of the Arithmetic Triangle. Image courtesy: MS Paint."
%}

Pascal would be proud to see **Figure 3**. _Source: trust me bro._

And not just in games, but also very weird and unique shapes in math -
fractals! Odd/Even numbers form a very nice pattern on the Arithmetic Triangle.
If we were to shade them in different colours on an Arithmetic Triangle
extended to infinity, it would become a popular fractal known as _Sierpinski
Triangle_, which has zero area but infinite perimeter. I don't know what is
more fascinating than this _beauty **of** the beast_.

_Did you know that fractals are somewhat represented in real life as well, e.g.
the coast of a continent/island as seen from outer space?? This means that if
you zoom in, you'll see a similar structure to what you initially saw - that is
what self-similarity is all about. A math fractal can be zoomed in as much as
possible and we shall always see a replication of the original one! Ever looked
into the very vibrant Mandelbrot or Julia sets? Do it, the clock is ticking..._

{% include image.html 
    url="articles/2022-03-16/sierpinski.png"
    width="550px"
    caption="**Figure 4.** Shading of the Arithmetic Triangle where the even
    numbers are coloured white and the rest black. This closely resembles the
    self-similar fractal called Sierpinski Triangle."
%}

## Much more to see

While that is all I have to present now, it is not the end! There are many more
recurrence relations popping out of the Triangle, the Pascal Matrix has other
forms which provide us with more interesting results, it is also used to devise
winning strategies in games of chance where you need to bet a share (as Pascal
mentioned in his treatise). It can never be fulfilling enough for an
inquisitive mind to end their venture with the end of this article. So take up
your pen and paper, and wade through the countably infinite world of the
Arithmetic Triangle!

<br>

## References

1. Wikipedia, [Pascal's Triangle](https://en.wikipedia.org/wiki/Pascal's_triangle)
2. Pascal, B., [The Arithmetic
Triangle](https://devapeur.files.wordpress.com/2016/11/pascal-arithmetic-triangle.pdf)
3. Wolfram MathWorld, [Unipotent](https://mathworld.wolfram.com/Unipotent.html)
4. Zhang, Z., The linear algebra of the generalized Pascal matrix, 
_Linear Algebra and its Applications_, **250**, 51-60 (1997).
5. Edelman A. and Strang G., Pascal matrices, _American Mathematical Monthly_, **111:3**, 189-197 (2004)
6. Falcon S., The k-Fibonacci matrix and the Pascal matrix, _Open Mathematics_,
**9.6**, 1403-1410 (2011).
7. Gupta S., Theory on Dimensions, _Int J Sci Res Publ_, **7**(11) (2017)
