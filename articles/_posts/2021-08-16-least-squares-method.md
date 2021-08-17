---
layout: post
title: Visualizing the Method of Least Squares
author: Satvik Saha
blurb: A geometric perspective, with a little intuition and linear algebra.
tags: article
katex: true
---


The method of least squares is a standard technique in linear regression, one
which most of us have encountered in the context of curve fitting. The simplest
example is this: given $n$ data points of the form $(x_i, y_i)$, find the line of
best fit through them, of the form $y = mx + c$. When we say 'best fit', we know
that a single straight line may not cut all our points; there may be no way of
solving the system of linear equations 

$$
    mx_i + c = y_i.
$$

Instead, we want to find the line which minimizes our error, with all our data
points lying as close to the line as possible. 

{% include image.html 
    url="articles/2021-08-16/linear_fit.png"
    caption="The red line of best fit is chosen so as to minimize the squares
    of the deviatios from the data points in black."
%}

One way of doing this is to take each point $(x_i, y_i)$ and calculate the
corresponding vertical deviation from our line, $\delta_i = y_i - (mx_i + c)$.
In order to minimize the total magnitude of deviation, we look at the following
quantity - the sum of the squares of deviations.

$$
    E(m, c) = \sum_{i = 1}^n \delta_i^2 = \sum_{i = 1}^n (y_i - mx_i - c)^2.
$$

The line of best fit is the one which minimizes this error. This can be done
directly using calculus; simply set $\partial E / \partial m = 0$ and $\partial E
/ \partial c = 0$. The result is quite cryptic.

$$
    m = \frac{n \sum x_iy_i - \sum x_i \sum y_i}{n
    \sum x_i^2 - \left(\sum x_i\right)^2}, \qquad
    c = \frac{\sum y_i - m\sum x_i}{n}.
$$

In this article, we offer a different perspective, combining intuition with a
little linear algebra.


## Systems of linear equations

Consider the following system of equations.

$$
\begin{align*}
    2x \;+\; \:\;y \;&=\; 7, \\
    x \;+\; 3y \;&=\; 6.
\end{align*}
$$

This can be compactly expressed using column vectors and matrices.

$$
    \begin{bmatrix}
        2 & 1 \\ 1 & 3
    \end{bmatrix} \begin{bmatrix}
        x \\ y
    \end{bmatrix} \;=\; x \begin{bmatrix}
        2 \\ 1
    \end{bmatrix} + y \begin{bmatrix}
        1 \\ 3
    \end{bmatrix} \;=\; \begin{bmatrix}
        7 \\ 6
    \end{bmatrix}.
$$

Using the symbols $A$ for the matrix, $\boldsymbol{a}_1$ and $\boldsymbol{a}_2$
for the columns of $A$, $\boldsymbol{x}$ for the vector of unknowns, and
$\boldsymbol{b}$ for the vector of knowns, we can write 

$$
    A\boldsymbol{x} = x \boldsymbol{a}_1 + y \boldsymbol{a}_2 =
    \boldsymbol{b}.
$$

With this picture, we see that finding a solution $\boldsymbol{x}$ amounts to
finding some multiples of the vectors $\boldsymbol{a}_1$ and $\boldsymbol{a}_2$
which add up to the vector $\boldsymbol{b}$. In our particular case, we see that
$3 \boldsymbol{a}_1 + \boldsymbol{a}_2 = \boldsymbol{b}$, giving us the 
solution $x = 3$, $y = 1$. Note that we didn't need to talk about deviations and
least squares yet; our solution is exact.

{% include image.html 
    url="articles/2021-08-16/span_2d.png"
    caption="The red vector is a linear combination of the blue and green vectors."
%}

Another way to see that our system has a solution is to look at every possible
linear combination $A\boldsymbol{x} = x \boldsymbol{a}_1 + y \boldsymbol{a}_2$.
This is called the span of $\{\boldsymbol{a}_1, \boldsymbol{a}_2\}$. In this
case, it is evident that this fills out the entire plane! Thus, no matter what
$\boldsymbol{b}$ we choose, it will lie somewhere in the plane and hence yield a
solution. Indeed, given arbitrary $\boldsymbol{b} = [p \quad q]^\top$, we can
write

$$
    \frac{3p - q}{5} \begin{bmatrix}
        2 \\ 1
    \end{bmatrix} + \frac{- p + 2q}{5} \begin{bmatrix}
        1 \\ 3
    \end{bmatrix} \;=\; \begin{bmatrix}
        p \\ q
    \end{bmatrix}.
$$

In short, we have $\boldsymbol{x} = A^{-1}\boldsymbol{b}$.


## Overdetermined systems

This time, consider the system of equations

$$
\begin{align*}
    2x \;+\; \:\;y \;&=\; 7, \\
    x \;+\; 3y \;&=\; 6, \\
    3x \;-\; \:\;y \;&=\; 3.
\end{align*}
$$

It can be checked that this has no solution; the first two equations only admit
$x = 3$, $y = 1$, but this violates the third. As before, write 

$$
    \begin{bmatrix}
        2 & 1 \\ 1 & 3 \\ 3 & -1
    \end{bmatrix} \begin{bmatrix}
        x \\ y
    \end{bmatrix} \;=\; x \begin{bmatrix}
        2 \\ 1 \\ 3
    \end{bmatrix} + y \begin{bmatrix}
        1 \\ 3 \\ -1
    \end{bmatrix} \;=\; \begin{bmatrix}
        7 \\ 6 \\ 3
    \end{bmatrix}.
$$

$$
    A\boldsymbol{x} = x \boldsymbol{a}_1 + y \boldsymbol{a}_2 =
    \boldsymbol{b}.
$$

In order to see what's happening, let's look at the span of the column vectors
$\boldsymbol{a}_1$ and $\boldsymbol{a}_2$.

{% include image.html 
    url="articles/2021-08-16/span_3d.png"
    caption="The pink plane, which is understood to extend outwards in all
    directions, denotes the span of the blue and green vectors. Note that the
    target point $\boldsymbol{b}$ in red does not lie on this plane. It's
    'shadow' on the plane, $\boldsymbol{b}'$, has been indicated for
    perspective."
%}

Now it is evident that the linear combinations $A\boldsymbol{x} =
x\boldsymbol{a}_1 + y\boldsymbol{a}_2$ fill out a plane in $3\mathrm{D}$ space.
However, our target vector $\boldsymbol{b}$ lies outside this plane! Thus, there
is no way of combining $\boldsymbol{a}_1$ and $\boldsymbol{a}_2$ to get
$\boldsymbol{b}$.


## Finding the best solution

In the previous section, we saw that our target $\boldsymbol{b}$ lies outside our
span, the set of vectors $\{A\boldsymbol{x}\}$. Thus, we cannot extract an exact
solution; instead, we look for the best possible solution $\hat{\boldsymbol{x}}$.
This is chosen in such a way that the corresponding point on the plane,
$A\hat{\boldsymbol{x}}$, lies as close as possible to $\boldsymbol{b}$. Note that
this corresponds to minimizing the square of the length $\Vert
A\hat{\boldsymbol{x}} - \boldsymbol{b}\Vert^2$, which is exactly the sum of
squares of deviations. Thus, we break down the vector $\boldsymbol{b}$ into the
components

$$
    \boldsymbol{b} = A\hat{\boldsymbol{x}} + \boldsymbol{r}.
$$

In order to minimize the distance of $\boldsymbol{b}$ from the plane, i.e. the
length of the component $\boldsymbol{r}$, it is intuitively clear that the
closest point $A\hat{\boldsymbol{x}}$ must be the perpendicular projection of
$\boldsymbol{b}$ onto the plane. Thus, the difference $\boldsymbol{r}$ must be
perpendicular to the plane.

{% include image.html 
    url="articles/2021-08-16/span_3d_perp.png"
    caption="The closest point to $\boldsymbol{b}$ on the plane,
    $A\hat{\boldsymbol{x}}$, is its perpendicular projection. The vector
    $\boldsymbol{r}$ is this orthogonal to the plane."
%}

In particular, $\boldsymbol{r}$ is perpendicular to both $\boldsymbol{a}_1$ and
$\boldsymbol{a}_2$. We write this in terms of the dot product: $\boldsymbol{a}_1
\cdot \boldsymbol{r} = 0$ and $\boldsymbol{a}_2 \cdot \boldsymbol{r} = 0$.
The dot product can be rewritten in the form

$$
    \boldsymbol{v}\cdot\boldsymbol{w} = \sum_{i = 1}^n v_iw_i =
    \boldsymbol{v}^\top\boldsymbol{w}.
$$

Thus, we express our perpendicularity condition as $A^\top \boldsymbol{r} =
\boldsymbol{0}$. This means that 

$$
    A^\top \boldsymbol{b} = A^\top A \hat{\boldsymbol{x}} + A^\top \boldsymbol{r}
    = A^\top A\hat{\boldsymbol{x}}.
$$

Note that $A^\top A$ is a square matrix. Whenever $A^\top A$ is invertible, i.e.
there happens to be a unique solution $\hat{\boldsymbol{x}}$, we must have 

$$
    \hat{\boldsymbol{x}} = (A^\top A)^{-1} A^\top \boldsymbol{b}.
$$

Returning to our example, calculate 

$$
    A^\top A =  \begin{bmatrix}
        2 & 1 & 3 \\ 1 & 3 & -1
    \end{bmatrix} \begin{bmatrix}
        2 & 1 \\ 1 & 3 \\ 3 & -1
    \end{bmatrix} = \begin{bmatrix}
        14 & 2 \\ 2 & 11 
    \end{bmatrix},
$$ 

$$
    A^\top\boldsymbol{b} = \begin{bmatrix}
        2 & 1 & 3 \\ 1 & 3 & -1
    \end{bmatrix} \begin{bmatrix}
        7 \\ 6 \\ 3
    \end{bmatrix} = \begin{bmatrix}
        29 \\ 22
    \end{bmatrix}.
$$

Using the fact that $A^\top A$ is invertible, we end up with
$\hat{\boldsymbol{x}} = (A^\top A)^{-1}A^\top \boldsymbol{b} = [11 / 6 \quad 10 /
6]^\top$.


## Lines of best fit

We return to our original problem of fitting a line $y = mx + c$ through $n$ data
points $(x_i, y_i)$. In other words, we seek the best solution $\hat{m}$,
$\hat{c}$ for the system of $n$ equations,

$$
    mx_i + c = y_i.
$$

Identify 

$$
    A = \begin{bmatrix}
        x_1 & 1 \\ x_2 & 1 \\ \vdots & \vdots \\ x_n & 1
    \end{bmatrix}, \quad 
    \boldsymbol{x} = \begin{bmatrix}
        m \\ c
    \end{bmatrix}, \quad 
    \boldsymbol{b} = \begin{bmatrix}
        y_1 \\ y_2 \\ \vdots \\ y_n
    \end{bmatrix}.
$$

Thus, we calculate 

$$
    A^\top A = \begin{bmatrix}
        \sum x_i^2 & \sum x_i \\ \sum x_i & n
    \end{bmatrix}, \quad 
    A^\top \boldsymbol{b} = \begin{bmatrix}
        \sum x_i y_i \\ \sum y_i
    \end{bmatrix}.
$$

The determinant of $A^\top A$ is given by 

$$
    \Delta = n\sum_{i = 1}^n x_i^2 - \left(\sum_{i = 1}^n x_i\right)^2.
$$

When $\Delta \neq 0$, we can directly calculate 

$$
\begin{align*}
    \hat{\boldsymbol{x}} &= (A^\top A)^{-1} A^\top \boldsymbol{b} \\
    &= \frac{1}{\Delta} \begin{bmatrix}
        n & -\sum x_i \\ -\sum x_i & \sum x_i^2
    \end{bmatrix} \begin{bmatrix}
        \sum x_i y_i \\ \sum y_i 
    \end{bmatrix} \\
    &= \frac{1}{\Delta} \begin{bmatrix}
       n\sum x_i y_i - \sum x_i \sum y_i \\ \sum x_i^2 \sum y_i - \sum x_i y_i
       \sum x_i
    \end{bmatrix}.
\end{align*}
$$

With a bit of rearrangement, we retrieve the relations 

$$
    \hat{m} = \frac{n \sum x_iy_i - \sum x_i \sum y_i}{n
    \sum x_i^2 - \left(\sum x_i\right)^2}, \qquad
    \hat{c} = \frac{\sum y_i - \hat{m}\sum x_i}{n}.
$$

## Generalizing

The same process can be applied to any sort of fit $y_i = f(x_i)$, as long as the
$f$ is a linear combination of the unknown parameters. For instance, in order to
fit the points $(x_i, y_i)$ to a parabola $y = ax^2 + bx + c$, we would write 

$$
    A = \begin{bmatrix}
        x_1^2 & x_1 & 1 \\
        x_2^2 & x_2 & 1 \\
        \vdots & \vdots & \vdots \\
        x_n^2 & x_n & 1
    \end{bmatrix}, \quad 
    \boldsymbol{x} = \begin{bmatrix}
        a \\ b \\ c
    \end{bmatrix}, \quad 
    \boldsymbol{b} = \begin{bmatrix}
        y_1 \\ y_2 \\ \vdots \\ y_n
    \end{bmatrix}.
$$

When $f$ happens to be non-linear in its parameters, there are special
circumstances under which the system can be linearized and solved iteratively by
invoking the Jacobian; this is a topic for a completely new discussion.

<br>

## References
[1] Margalit, Dan and Rabinoff, Joseph, [_Interactive Linear Algebra_](https://textbooks.math.gatech.edu/ila/)
