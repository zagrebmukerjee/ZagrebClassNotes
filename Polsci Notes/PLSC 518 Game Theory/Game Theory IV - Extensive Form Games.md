---
aliases:
creation date: Tuesday, October 25th 2022, 3:42 pm
date updated: Tuesday, November 1st 2022, 4:26 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory IV - Extensive Form Games]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Raw Notes

We have normal form game: $<N,S,U>$. 

Now we allow for sequenced play. Create the extensive form game.

Example

![[Game Theory III - Bayesian Games 2022-10-18 17.10.03.excalidraw|300]]

two players make choices in sequence, and the choice set depends on prior choices of self/others. The end states are called 'terminal history'


New game: 

![[Game Theory III - Bayesian Games 2022-10-18 17.13.17.excalidraw|300]]

children fighting in sandbox - a nice toy. do i take it? Will the toy's owner fight me? fighting is strictly dominated, conditional on my taking the toy? so I should take it. this is a normal formization type of result
but another NE result is: don't take (player 1 believes player 2 will fight, so doesn't take)


Need another criterion to rule that out: don't include anticipation of non credible actions. this gets rid of (take, fight) as a strategy. 

Two related concepts:
- backwards induction
- subgame perfect equilibria


A strategy in this game is how you would play in each node you would possibly get to. 
so an equilibrium is the entire backward induction. 

### Formalization
Components:
- $N$ players
- $H$ is a set of terminal and non-terminal histories. $H$ is every node; terminal notes have no out-edges. 
- At each $t \in T$ terminal histor I need a utility function $u_i: T \to \R$. 
- $p: NT \to N$: whose turn is it? 
- Ordering on $H$
- I want to represent that the next player in the sequence may not know where they are in the tree (don't know the history)
	- so I can group the nodes I might be in, call it an "information set" 


ways of solving these problems:
- Backwards Induction
- Subgame Perfection

two ways of saying the same thing. Backwards induction. What will I choose, thinking about how the person/people after me will react to the choice: start at the bottom, and then construct conditional terminal histories

Subgame perfection is conceptually deeper, but coincides with BI when latter is well defined. subgame - original game is a choice across subgames - each fork creates one

subgame perfect NE require that strategies call for NE behavior in every subgame. So, in fight/nofight game, can't count on player 2 fighting given take, b/c that doesn't meet NE criterion for the (1 player) subgame. 

### Theorem.
- Every finite game (finite number of nodes, of players, of choices) has at least 1 SGPNE. 
- If information sets are singletons, $\exists$ a pure SGPNE

Generically uniqueness? Need some things to be the same for multiple equilibria - idea is that exactly same is vanishingly unlikely for real valued stuff


Single Deviation Principle. How do I show that a certain set $H$ is not an SGPNE: I just need to find a place where a player wants to deviate. that invalidates one subgame. 


can have a continuous node. Ultimatum game. Phase 1: player 1 offers $s_1 \in [0,1]$; player 2 accepts for $1 - s_1$ or rejects for $0$. This isn't finite for our theorem. 

To find SGPNE:
Candidate: 
1) $S_2(s_1)$ is: yes if $1-s_1 >= 0$, no otherwise. With $S_1 = 1$ then this is an SGPE
2) $S_2(s_1)$ is: yes if $1-s_1 > 0$, no otherwise. Then there's no NE. because the best response for $s_1$ is the minimum of an open set. 

oh no... we need a 'tiebreaker' criterion, what does player 2 do when indifferent. 


Is $S_2(s_1) =$ yes if $1 - s_1 > k$, creating an NE? Then $S_1 = 1-k$. But player 2's strategy is not subgme perfect. 


Theorem. - a status quo game. No agreement: p1 get q and p2 get 1-q. $S_2(s_1) =$ accept if $1-s_1 \geq 1-q$, reject otherwise. Then $S_1 = q$. 
$S_2(s_1) =$ accept if $1-s_1 \geq 1-q$, reject otherwise. Then $S_1 = k > q$. - this is also an equilbrium. I ask for more but then get nothing 

now I have another parameter $\delta \in (0,1)$. A deflator: if no agreement, p1 gets $\delta q$ and p2 gets $\delta(1-q)$. SO now player 2 can have a strategy that is $1 - s_1 \geq \delta(1 - q)$. Then p1 is best off offering $1 - s_1 = \delta(1-q)$. player 1 can still do some looting by holding hostage the future income. 

New game: 

![[Game Theory IV - Extensive Form Games 2022-10-25 16.56.50.excalidraw]]
now we have two rounds of bidding - ie. offer and counteroffer. Inefficiency cost of counteroffering

1 accepts iff $d x_2 \geq d^2q$. so 2 offers $x_2 = d q$. So when does 2 want to not counteroffer: when $1 - x_1 \geq d(1 - d q)$; so 1 keeps $x_1 = 1 - d + d^2 q$



### Bargaining with Outside Options

This was dividing a pie. Now: divide a pie, and if we disagree we fight a war
![[Game Theory IV - Extensive Form Games 2022-10-25 17.10.48.excalidraw]]

we can say war involves paying a cost and some probability of winning. say 1 pays k for war, and 2 pays c. probability that 1 wins is p. 

Player 2 accespts if $1-x \geq 1 - p - c$ the expected utility of war. So $x = p + c$; in other words, the better player 1's odds of winning, or the more player 2 pays a cost to make war, the more surplus player 1 can extract. 


suppose p, k are known mutually. But only 2 knows c. There is some probability distribution: $\underline c$ with probability $q$ and $\overline c$ with probability $(1-q)$. 
What's optimal for low-c player 2: threshold lower thna for high-c 

player 1 has a non-smooth utility: no reason to play anything in $(\underline c, \overline c)$. Bidding $p + \underline c$ is certain peace. So I want to know if $p + \underline c > (p + \overline c)(1-q) + (p-k)q$. 


#### Smooth Model


War $\implies$ $U_1 = p-k$ and $U_2 = 1-p-c$ where $c \in [0, 1-p]$ with some distribution. The realization (not the distribution) is unknown to Player 2

Suppose Player 2 accepts when $1-x \geq 1 -p -c$ or $x \leq p+ c$ or $x-p \leq c$. So reject if $c \leq x-p$. If it costs less for me to fight than proposed division of peace winnings. 

Then Player 1 has the problem: 
$$\max_x F(x-p)(p-k) + [1-F(x-p)]x$$
So I make an offer that's weighing probability of war, my gains from war, and the benefit of the offer. But this is now a smooth function rather than the discontinuous one from last formulation. The more aggressive your offer, the greater the share you'd get of the gains from peace, but the lower the probability of peace. 

Note: Monopoly pricing problem has the same intensive-extensive margin question


Now with this sort of generic question: write specific models, develop intuition, and only then try to develop general form of result with implicit function theorem etc. So let's say $F$ is the uniform CDF over $0, 1-p$. and then given demand $x$ the probability of war is $(x-p)/(1-p)$. check with intuition... if I demand $1$, I get certainty of war. if I demand the least, $p-k$ then I get probability of war $k/1-p$. 


So I want to solve

$$ \max_x \left(\frac{x-p}{1-p}\right)(p-k) + \left(1 - \frac{x-p}{1-p}\right)x$$
Solution: $x^* = (1 + p-k)/2$ 

If $p = 1/2$ and $k=0$ then $x^* = 3/4$. So because fighting still gets you $1/2$ you leave it on the table. 

probability of war is 

$\frac{x^*-p}{1-p}$
In this case, $1/2 - k/[2(1-p)]$. What if $k = 1/4$? Then $x^* = \frac{5}{8}$. There's still some first mover advantage. 


#### Implicit Function Theorem Approach


Now we have : 

$$(p-k)f(x-p) + [1-F(x-p)] - x f(x-p) = 0$$
Write some function $g(x) = x^* - p + k - \frac{1 - F(x^*-p)}{f(x^*-p)}$. Then I have equilibrium condition is that this be $0$; player $1$ is maximizing. 
If $x^*$ solves $g(x, b) = 0$ then 

$$ \frac{dx(b)}{db} = -\frac{dg/db}{dg/dx}$$
I can say I have $dg/db = 0$ since I am on my level curve: then lock $dg/db$ a total change at $0$ and then say as I move $b$, $x$ needs to move some amount to cancel that out. 