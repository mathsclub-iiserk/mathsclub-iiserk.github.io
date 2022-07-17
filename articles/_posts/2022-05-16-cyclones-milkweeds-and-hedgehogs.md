---
layout: post
title: Cyclones, Milkweeds, and Hedgehogs
author: Soumya Das Gupta
blurb: >
    The article explores a theorem that states that even dimensional spheres do
    not admit a smooth non-vanishing nowhere zero tangent vector field. The 3
    dimensional analogue of this is called the Hairy ball theorem, or as the
    Europeans say, the Hedgehog theorem, in layman’s term which says that if
    you have a ball with hair sprouting out of every point, it cannot be combed
    without creating a bald spot or a cow-lick!
tags: article
katex: true
---

> "_Once the storm is over, you won't remember how you made it through, how you managed to survive.
> You won't even be sure in fact, whether the storm is really over.
> But one thing is certain, when you come out of the storm you won't be the same person who walked in.
> That's what the storm is all about._"
> -- Haruki Murakami.

_(It ain't no matter if the stuff introduced in sections 1, 2, and 3 are
unfamiliar to you, reader. You can enjoy the Hairy consequences just as much if
you start right from section 4. Happy read!)_

## Vector fields, sections, tangent and vector bundles

**Tangent bundle:** Let $M$ be a smooth manifold, and for any point $x \in M$
let $T_xM$ typify the tangent space anchored at $x$. Then, the tangent bundle
$TM$ of $M$ is defined as follows.

$$ TM = \bigcup_{x \in M} \{x\} \times T_xM. $$


**Vector bundle:** A vector bundle is a triple $(\pi, E, B)$, where $E$ and $B$
are smooth manifolds, and $\pi\colon E \to B$ is a smooth map satisfying the
following.

- $\pi$ is surjective.
- There is an open cover $(U_i)_{i \in I}$ of $B$ with a collection of
  diffeomorphisms $h_i\colon \pi^{-1}(U_i) \to U_i\times \mathbb{R}^n$ where
  $h_i(\pi^{-1}(x)) = \\{x\\}\times \mathbb{R}^n$.
- For all $i, j \in I$, the map $h_i\circ h_j^{-1}$ restricted to $(U_i \cap
  U_j) \times \mathbb{R}^n$ is smooth.


**Section:** A (smooth) section of a vector bundle $(\pi, E, B)$ is a (smooth)
map $m\colon B \to E$ such that $\pi\circ m = \mathop{id}_B$.


**Vector field:** If $M$ is a smooth manifold, a (smooth) vector field $F$ on
$M$ is a section $F\colon M \to TM$. For our purpose, a vector field on $S^{n -
1}$ is a section of the tangent bundle. In a more prosaic but visually vibrant
term, it is a map $F\colon S^{n - 1} \to \mathbb{R}^n$ such that for all $p \in
S^{n - 1}$, we have $\langle F(p), p \rangle = 0$ and $F$ is continuous, where
$\langle\cdot,\cdot\rangle$ can be taken as the standard dot product.

<br>

[Read the full article here]({% link assets/documents/articles/2022-03-14/cyclones-milkweeds-and-hedgehogs.pdf %})

<br>

## About the author

Soumya Das Gupta is a student of the Chennai Mathematical Institute.
This particular article placed fifth in our [Article Writing Contest,
2022](https://www.iiserkol.ac.in/~maths.club/events/2022/03/14/article-writing-contest.html).
