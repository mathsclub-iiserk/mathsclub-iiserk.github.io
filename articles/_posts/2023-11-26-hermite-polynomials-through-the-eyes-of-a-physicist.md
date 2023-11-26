---
layout: post
title: Hermite Polynomials, through the eyes of a Physicist
author: Karthikeyan Ganesan
blurb: >
    _This article is indeed a part of the webpage of Identity and please do not come at me for this, because the idea for this article was provided to me by one of the founding members of Identity, who is a Mathematician disguised as a Physicist and hence does not want the world to know him. I know you Mathematicians do not like it when a Physicist tries to explain concepts in Math to you..._
tags: article
katex: true
---


## Introduction

I begin by stating the obvious: this article is indeed a part of the webpage of Identity and please do not come at me for this, because the idea for this article was provided to me by one of the founding members of Identity, who is a Mathematician disguised as a Physicist and hence does not want the world to know him. I know you Mathematicians do not like it when a Physicist tries to explain concepts in Math to you (I learned this the hard way in my second year Math course's presentation), but one of your founding members is a sadist (like all Mathematicians?) and hence wanted me to write this article. 

## A bit of Physics

All of you Math Majors in IISER-K (and beyond) would have definitely taken some Physics courses during your first and second years, so I will try to explain some Physics. In the world of Quantum Mechanics (think Schrodinger's cat, if you have never heard of this before), there is the concept of a Harmonic Oscillator, which is described by the Hamiltonian:

\\[\hat{H} = \frac{\hat{p}^{2}}{2m} + \frac{1}{2}m\omega^{2}\hat{x}^{2}\\]

where \\(\hat{p}\\) and \\(\hat{x}\\) are the momentum and position operators.
The corresponding equation to find the energy eigenvalues (denoted by E) is:

\\[\hat{H} \psi \rangle = E \psi \rangle\\]


Using the definition of momentum and position operators, as well as the definition of wavefunction in position, one obtains the Time-independent Schrodinger equation:

\\[-\frac{\hbar^{2}}{2m}\frac{d^{2}\psi(x)}{dx^{2}} + (\frac{1}{2}m\omega^{2}x^{2} - E)\psi(x) = 0\\]

If we use the ladder operator formalism, we obtain:

\\[E = (n+\frac{1}{2})\hbar\omega\\]

which implies energies are quantised and hence so are the wavefunctions:

\\[\psi(x) \leftrightarrow \psi_{n}(x)\\]

Using the above relations, and if Energy is measured in units of \\(\hbar\omega\\) and position in units of \\(\sqrt{\frac{\hbar}{m\omega}}\\), then we obtain the equation:

\\[-\frac{1}{2}\frac{d^{2}\psi_{n}(x)}{dx^{2}} + (\frac{1}{2}x^{2} - (n+1/2))\psi_{n}(x) = 0\\]

Further simplification gives us:

\\[\frac{d^{2}\psi_{n}(x)}{dx^{2}} + (2n+1 - x^{2})\psi_{n}(x) = 0\\]


## Hermite Polynomials, the Mathematical way

It is interesting to realise that even Mathematicians seem annoyed by Physicists changing the definition of concepts to their liking, as there are two types of Hermite Polynomials, and the jokes write for themselves if you look at their names:

- the Probabilist's Polynomial: \\(He_{n}(x) = (-1)^{n} e^{\frac{x^{2}}{2}} \frac{d^{n}}{dx^{n}}e^{-\frac{x^{2}}{2}}\\)
- the Physicist's Polynomial: \\(H_{n}(x) = (-1)^{n} e^{x^{2}} \frac{d^{n}}{dx^{n}}e^{-x^{2}}\\)

To me, as a physicist, I don't (and never will or want to) understand that a factor of half requires a separate definition, since I have the liberty of ``redefining" things the way I want to. In other words, I can just say \\(x \leftrightarrow \frac{x}{2}\\) and move on with my life!






The corresponding graphs for various values of n are given below:

{% include image.html 
    url="articles/2023-11-26/Physicist.png"
    width="500px"
    caption="The Physicist version."
%}

{% include image.html 
    url="articles/2023-11-26/Probabilist.png"
    width="500px"
    caption="The Probabilist's one."
%}



## Properties

I will only focus on the properties that are of interest to Physicists:

- Symmetry (Oh, we all love Symmetry): \\(H_{n}(-x) = (-1)^{n}H_{n}(x)\\) and \\(He_{n}(-x) = (-1)^{n}He_{n}(x)\\)
    If you are wondering why Physicists love Symmetry, there is a course in 4th year by ADG sir, just for that. You'll definitely ``enjoy" that course, so do take it!
- Orthogonality, which is also adored by Physicists, especially in the world of Quantum Mechanics:
    \\[\int_{-\infty}^{+\infty} H_{m}(x) H_{n}(x) w(x) \,dx\ = 0 \\]
    \\[\int_{-\infty}^{+\infty} H_{m}(x) H_{n}(x) w(x) \,dx\ = 0  \\]
    where \\(w(x)\\) are the weight functions. For He: 
    \\[w(x) = e^{-\frac{x^{2}}{2}}\\]
    For H:
    \\[w(x) = e^{-x^{2}} \\]
    The above conditions hold only when \\(m = n\\). What happens when \\(m = n\\)? Well, that is a homework for you!

## The Intertwining

Recall the last equation in section 2:
$$ \frac{d^{2}\psi_{n}(x)}{dx^{2}} + (2n+1 - x^{2})\psi_{n}(x) = 0  $$

Observe that if we define our wavefunction as:
$$ \psi_{n}(x) = (2^{n}n!\sqrt{\pi})^{\frac{-1}{2}} e^{-\frac{x^{2}}{2}} H_{n}(x)$$
where $H_{n}(x)$ is the Physicist's version (no surprises) of the Hermite Polynomail, then, the previous equation is satisfied! The above expression is what is called ``Hermite Functions".






The wavefunctions for different values of n are given below:

{% include image.html 
    url="articles/2023-11-26/Hermite_Functions.png"
    width="600px"
    caption="The beautiful wavefunctions of a beautiful concept."
%}


These Hermite Functions have some other functions (pun intended) of their own, for which you can approach the mathematicians in Identity. As I mentioned before, I only care about concepts related to Physics, especially Quantum Mechanics. That is all I have to offer about the good parts of Hermite Polynomials. 


By the way, if you are physicist who is insecure about yourself because you're surrounded by Mathematicians (like me), just remember this quote from one of my favourite professors:


_"Two fours and one six add up to 14, not 16. If you're really that bad at addition, you should try your hand in Mathematics. They are amazing at coming up with ways to justify new ways of addition just because they messed it up somewhere or the other."_



<br>

## About the author

Karthikeyan Ganesan is an undergraduate student pursuing a BS-MS degree at IISER Kolkata, with an interest in mathematical physics.
He is also a writer. 