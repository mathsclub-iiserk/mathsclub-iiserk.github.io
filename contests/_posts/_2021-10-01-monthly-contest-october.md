---
layout: post
title: October - Amity
author: Sohom Gupta
blurb: >
    Today, we shall be taking a break from rigorous mathematics and be looking
    at a form of chess, much simpler than what the professionals play. Instead
    of an 8×8 chessboard, we’ll take a 8×1 chessboard and take only three of
    each set of pieces, namely the King (K), the Rook (R) and the Knight (N).
tags: monthlycontest
katex: true
---

Pura assumes her position for this month, more confident than before. There has
been some good responses for last month's exploration, leading to the necessary
morale boost for her. Today she wanted to try out something simple and
beautiful. She waits for the final setup, and begins.

"It is my pleasure to present myself before all of you once again; this time
with a new set of ideas and challenges. We all should be somewhat familiar with
various board games - that is, excluding the Ouija. Today, we shall be taking a
break from rigorous mathematics and be looking at a form of chess, much simpler
than what the professionals play. Indeed, instead of an 8×8 chessboard, we'll
take a 8×1 chessboard and take only three of each set of pieces, namely the
King (K), the Rook (R) and the Knight (N). Check the setup below."

{% include image.html
    url="contests/2021-10-01/chess_alpha.png"
    width="600px"
    caption="**Figure 1.** The one-dimensional chessboard is as shown. Each
    side has a King, a Rook and a Knight arranged as K-N-R from the edge of the
    board towards the center. There are two open squares in the center of the
    board. If you don't have a board at home, then try drawing a board and
    using coins to represent the pieces; manually playing will make you more
    confident in the rules. **Warning!** Online board editors are discouraged
    since traditional Knight moves are different from the ones to be used
    here."
%}

"First, I shall describe how the King and the other pieces move. All pieces
should remain on the board unless captured. Captured pieces can't return to the
board later.  The pieces move as follows."

1. **K**: The King can move 1 square left or right. If there is a piece of an
   opposite colour adjacent to it, it can capture that piece. **Kings can’t be
   adjacent to each other.** They should have at least 1 space between them,
   either an open square or one with a piece. A King can not capture a piece of
   the same colour as it. A King cannot be captured, but it can be checked
   which I'll explain later. 
2. **N**: The Knight is a jumping piece. It skips one square either to the left
   or right. For example, a knight on _b_ can go to _d_, but cannot go left as
   there is nothing left of _a_. A knight can jump over pieces of either colour
   while moving (like N _b_ $\to$ _d_ jumps over a Rook on _c_). If there is a
   piece of an opposite colour occupying the square the Knight moves to, then
   that piece is captured. Knights cannot move to squares occupied by pieces of
   the same colour.
3. **R**: The Rook can only move on open squares. It can go both left or right
   as many open squares as there are. For example, Rook on _c_ can go to _d_
   and _e_.  If it goes to _f_, it has to capture the black Rook. It cannot go
   to _b_ as it can't capture a piece of the same colour. Note that if a Rook
   captures another piece, it will replace that piece's position of the board,
   i.e. it can't take more than one piece in one turn.

"We must also explain the scenarios of _check_, _checkmate_, and _stalemate_."

"A King is in **check** when an opponent's piece (not King) is _one move_ away
from capturing it, e.g. say the white knight is on _f_ which threatens to
capture the black king on _h_, or the black pieces are removed and the white
rook on _c_ threatens to capture the black king on the next move. When a king
is checked, it _must escape check_; _no other move is legal_. If the king
cannot escape check, then it is **checkmate**, and the person whose king is in
check loses."

"A King cannot run into a check, i.e. if there is a piece blocking the white
rook from attacking the black king, then black cannot move the piece away from
in between the king and the rook since that would mean the rook checks the
king.  Also, say the white King is on _d_ and _e_ is in the range of the black
_g_ Knight.  Then the white King can’t move to _e_ since then it will come
under check from the black Knight. A check can only be given by a piece to the
opponent's king, and the opponent has to escape the check via blocking, or
running away, or capturing the attacking piece to not lose the game."

"The game is stalemated if one of the players is not in check, but also has no
legal moves - this is called **stalemate**. For example, let the white rook
capture the black rook on turn 1. Then the black king has no moves, and the
only move of the black knight is _g_ $\to$ _e_, which is illegal as it would
put the black king in check. So, black has no legal moves, but is not in check
-- it is a stalemate."

Pura sits up, recollecting her ideas about this and thinking whether she forgot
a rule or two. Convinced otherwise, she continues. "So I have mentioned all
the rules and how the pieces move. Those of you who have played chess or
watched games should be familiar with most of the rules, and I'll not elaborate
any further. Let's get into the real stuff!"

"Let me tell you the notations to be used here. We won't use the standard ones
and will try to be a bit more descriptive. Conventionally white goes first. A
complete turn is finished when both white and black make a move. If a piece,
say a Knight, moves from _a_ to _c_, we denote it as $N_ac$. If there is a
piece on _c_ that it captures, then we will write $N_a\times c$, where the
$\times$ denotes the capture. If upon arriving at _c_, it captures a piece and
also puts the opponents King in check, we would write $N_a\times c+$, where the
$+$ denotes the check. If the check cannot be escaped, i.e. it's a checkmate,
then we write $N_a\times c\\#$, where the $\\#$ denotes the checkmate. If the
knight does _not_ check the opponent's king, but somehow stalemates it, then we
write $N_a\times c\\&$, where the $\\&$ denotes the stalemate."

"Let me denote a random game in which black loses, can you figure out how it
goes?"

$$ 1.\; R_cd\;\; N_ge \;\;2.\; R_d\times e\;\; K_hg \;\;3.\; N_bd\;\; K_gh \;\;4.\; R_e\times f\# $$

"Take your time to get familiar with the notation - it would be really easy to
summarize a game once you do! Once you are done try practicing with the pieces
by yourself on a board or diagram. If you're feeling confident, let's start!"

**(i) Conventionally, white makes the first move. Show that White can always
win regardless of whatever Black plays. Write down the longest game in chess
notation where White wins. It is obvious that you assume black plays logically,
i.e. tries to prevent checkmate.**

**(ii) Using chess notation, write down the shortest possible game (ending in
either checkmate or stalemate).**

**(iii) Using chess notation, write down the quickest win for white, not
assuming logical play from black (this is sometimes called a _helpmate_).**

"We have still not touched upon our primary goal of Amity. The Kings are
aggressive - they would either wish to crush the other via a checkmate or be in
an eternal stalemate, staring each other down! Only if they have no way of
doing either, they will shake hands and go back to their Queens, who are with
the Bishops in the castle - thus reaching Amity."

**(iv) Show that there will never be a case where Amity is reached when there
are just two Kings on this board. Further show that Amity is reachable on an
8×8 chessboard with two kings, each able to move 1 square in any of the eight
directions (other rules are the same).**

**(v) What is the minimum number of pieces (and what are they) for checkmate to
be possible? In other words, removing any one piece (not King) would create a
situation where checkmate is never possible.**

"Once we are done with this, let us simplify our board even more, so that we
only have to worry about two pieces." Pura laid back for a while, going over
the different possibilities of a 2D chess game already clouding her mind. It is
indeed interesting how things become so incredibly complicated with fundamental
increase of complexity that they quickly go beyond human grasp; Pura herself
though, does seem to be more aware of them.

"Let us only remove the Rooks. Then the new configuration of the board would be
as shown. The rules of the game are same as before. White should conventionally
move first."

{% include image.html
    url="contests/2021-10-01/chess_beta.png"
    width="600px"
    caption="**Figure 2.** In this scenario, the rooks have been removed; the
    rest of the board is the same."
%}

**(vi) What are the configurations in which White checkmates black and vice
versa?**

**(vii) What are the configurations for stalemate induced by white on black and
black on white respectively? Are they symmetrical, or does the convention of
white going first lead to some imbalance? Can you mathematically explain either
result you obtain?**

**(viii) Show that if any one of the players vouches for Amity (and the other
wants checkmate or stalemate), then the one vouching for Amity can force the
other to accept the same.**

"This shows that the amicable one wins at the end, provided one has honourable
knights on board, right? Now that we have mostly solved the game (maybe even
completely?), we can try some random stuff with it. Sort out your solution
configurations to **(vi)**. From the starting point, we want to reach one of
those positions by only moving the two knights alternately, starting with
white. Forget everything about the rules of check, checkmate and stalemate. We
only wish to reach that configuration using the mentioned knight moves.
Further, each knight is equipped with a randomizer that moves it. If a knight
has one legal move (you cannot capture a king), then it goes to that square
100% of the time (have you noted that the knights can never capture one
another?). If it has two legal moves, then it can move to either one of them
with uniform probability $p = 0.5$."

**(ix) Suppose white moves first, and we want to reach the configuration where
white knight checkmates the black king (as in (vi)) using the randomized knight
movements discussed above. What is the expected number of turns (1 turn equals
one move by both white and black) for that configuration to be reached for the
very first time?**

**(x) Do the same for when black knight checkmates the white king. Note that
white still goes first.**

While working on the last couple of problems, you have consciously or
subconsciously assumed a very important property. Remember that every legal
move made by a player depends only on the position of pieces on the boards
_right before_ they make it. In fact, even in normal chess, the evaluation of a
position or the best response 10 moves deep into the game only depends on the
position, and not how the board looked beforehand. This property is called
**memorylessness**.

Given that both players play completely random legal moves, if the state of the
board after every turn is denoted by $x_n$ and the random variables storing these
positions be denoted by $X_n$, then we get

$$ P(X_{n + 1} = x | X_n = x_n, X_{n - 1} = x_{n - 1}, \dots, X_0 = x_0) = P(X_{n + 1} = x_{n + 1} | X_n = x_n), $$

where $x$ is the position of the board after turn $n + 1$ and $x_0$ is the
initial position. However, as chess is played by two players, each $x_n$ would
store information about the position after each of white and black play their
moves in the $n$th turn. Such a sequence of states all satisfying the
memorylessness property form a **Discrete Time Markov Chain**. Not only that,
there are even more properties satisfied by a chess game!

Suppose you see both players repeating moves after turn $m$. So for every $n > m$
(to as long as the game continues without ending), $x_n$ will be the same. Now
given two identical positions, it is impossible to differentiate which has a smaller
value of $n$. Such a Markov Chain is called a **Time Homogeneous Markov Chain**
and is represented by

$$ P(X_{k + 1} = x | X_k = y) = P(X_{l + 1} = x | X_l = y) $$

for all $k, l$. This means that given any two times that the board reaches an
identical position, the probability that it reaches a fixed position after one
turn is exactly the same!

**(x) Can you verify these properties for at least one position from the
King-Knight configuration we discussed in Figure 2?**

"One you're done," Pura grinned, "I hope you can truly appreciate how symmetric
chess is as a stochastic process. Yet when the strongest professionals sit down
to play a game, they feel more intimidating than ever before. With that, say
_chesse_!"


## Submitting

Send in your solutions at
[maths.club@iiserkol.ac.in](mailto:maths.club@iiserkol.ac.in), with the subject
_Monthly Contest: October_.
