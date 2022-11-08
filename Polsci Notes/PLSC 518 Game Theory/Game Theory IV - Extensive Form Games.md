---
aliases:
creation date: Tuesday, October 25th 2022, 3:42 pm
date updated: Tuesday, November 8th 2022, 5:05 pm

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

Can apply the IFT here to figure out how equilibrium conditions change with parameters



## Infinite Horizon Extensive Form

OK so now logical extension: infinite rounds of offers, take turns offering/accepting. Each player has their own discount rate $\delta_i$. 

where do we start? 

Pick a value. $V_i$ is the value to player $i$ from being at a history in which they are the proposer. Now suppose I am Player 1. The best offer that you could have accepted is $\delta_2V_2$. So I want to demand $1-\delta_2 V_2$. 
But $V_2 = 1- \delta_1 V_1$. Then we have some good stuff:

Conjecture that I have an equilibrium. Then both best responses hold here. So $V_1 = 1 - \delta_2(1- \delta_1 V_1)$, meaning $V_1 = \frac{1-\delta_2}{1-\delta_1\delta_2}$. So what does this imply? It means that $1$ demands the least player $2$ will accept, and $2$ accepts? But is it better for me to make an offer that's accepted, or to pass the buck? If player 1 punts, they get player 2's offer: $\delta_1V_1$ which is the same as the value of passing on that offer. So that's $\delta_1^2 V_1$ both ways. Best offer $2$ accepts is $1-\delta_2 V_2$. For me to wait - a <font color=gree>continuation payoff</font>:
$$\begin{align}
\delta^2V_1 &< 1 - \delta_2V_2\\
&< 1 - \delta_2\left(\frac{1 - \delta_1}{1 - \delta_1 \delta_2}\right) \\
&< \frac{1 - \delta_1 \delta_2}{1 - \delta_1 \delta_2} - \left(\frac{\delta_2 - \delta_2\delta_1}{1 - \delta_1 \delta_2}\right) \\
&< \frac{1 - \delta_2}{1 - \delta_1 \delta_2}\\ 
&< V_1
\end{align}$$

An issue, here. So I won't want to wait. 



This is called the <font color=gree>Rubinstein Model</font> - a workhorse of bilateral negotiation papers. 


### Uniqueness

Interestingly we can show that this is the only equilibrium for this game.
Conjecture that there are different equilibria with different payoffs. There is a nice argument based on there being a biggest and smallest payoff


## Multi-Player Game

$n$ players dividing some resource (Ferejohn). 
dividing it is the $n-1$ dimensional simplex $(x_1, \ldots, x_n)$ such that $x_i \in [0,1]$ and $\sumn{i} x_i = 1$ (for 3 people this would be a triangle)

$$U_i = \delta^{t-1} x_i$$

Randomly chosen person makes an offer every period. So then $\rho_i$ is probabilty $i$ proposes with $\sum \rho_i = 1$. Majority rule on acceptance


this model can speak to a handful of different hings. 

coalitions
efficiency
equity

Example: pork acquisition. 

Want an SGPNE. Need another equilibrium concept: stationarity. Stationary $\subseteq$ SGPNE $\subseteq$ nash equilibria. 

### Stationarity
I require my voting behavior to be purely a function of the offer, and the offer I make is the same. Not the history of proposing or voting behavior. Thus - no punishments etc. 

If we don't add this assumption to this model, then really anything is describable as an equilibrium. There is some degree of substantive justification, eg stationary strategies are simplest. 

How to solve? Guess: we want all players to be best responding. have a $V_i$ as before which is value of being in a period where I propose. Then your choice is between either: accept the offer on the table, or get EV of waiting. EV is $1/n V_i + (1/n)(1/n) V_i$ etc. Offerer will offer each their EV of waiting. But we don't get a lot of milage from using the payoff conditional on being a proposer, because that is random

Suppose $\rho_i = 1/n$

Then $V_i$ is the continuation payoff of a point before the next offer is generated. ie. the payoff of the whole game. 
- so what is my voting rule. suppose I am pivotal. I will say, I vote policies that I like. 
- so I like offers that are $\geq \delta V_i$ (let $\delta_i = \delta$ for now)
- offerer $j$ has to offer to the cheapest bunch of people to appease, ie the ones with lowest continuation payoffs. The <font color=gree>minimum winning coalition</font>.
- but I want in equilibrium all $V_i$ to be the same. 

In equilibrium, offerer keeps $1 - (n-1)\delta V/2$ for herself , gives randomly $(n-1)/2$ people their reservation value, and everyone else gets nothing. This isn't quite enough yet. I need to think a bit about $V$. 

What is my expected value: with probability $1/n$ I am recognized and get $1 - (n-1)\delta V/2$. With probability $(n-1)/n$ I am not the proposer. then I have probability $1/2$ of being one of the winning coalition so I get $\delta V$, and probability $1/2$ I get $0$. 

So I need to have that equal to my offer for me to offer smth that will be accepted. 

$$ 
\begin{align}
V &= \frac{1}{n}\left(1 - \frac{n-1}{2}\delta V \right) + \left[ \frac{n-1}{n} \right] \left(\frac{1}{2}\delta V\right)\\
&= \frac{1}{n} - \frac{1}{n}\frac{n-1}{2}\delta V + \frac{n-1}{n} \frac{1}{2}\delta V\\
&= \frac{1}{n}\\
\end{align}
$$


does proposer want the rents:

$$
\begin{align}
1- (n-1)/2(\delta/n) \;&> \; \delta/n\\
n- (\delta n-\delta)/2 \;&> \; \delta\\
n\;&> \; \delta/2(1-\delta)\\
\end{align}
$$

#### Efficiency

This game is efficient: suppose the game ends at some point with $\delta \times p_i$ for everyone: then we can get $p_i$ by agreeing on that to start with, and divvy up the surplus to pay people.

This efficiency notion might be a starting point to uncover theoretical puzzles. why don't people just come to the agreement that they predictably will come to? There are three sorts of model features you can add to explain why there is 'inefficiency'
- incomplete information. eg. do I know if I will win the war. 
- lack of commitment
- contract space coarse


#### Extension with Different Recognition Probability

Keep $\delta$ the same. but have different $\rho$. Then what are the equilibria. We now need to have different $V_i$. 

Suppose $\rho_1 < \rho_2 < \rho_3$. Then player $1$ will be in every MWC because they're the cheapest? But there is a general equilibrium effect. Player 1, knowing this, will now demand more from anyone, because they have a better reservation value. 

For a finite horizon game you can construct $V_1 > V_2$. For infinite horizons, you cannot. 



## Spatial Policy Model

Romer and Rosenthal model. Bargaining with a proposer and a status quo. 

primitives of the game: players have ideal points along a spectrum of policy. 
school board or someone is a proposer. they also have an ideal point. 

there is a status quo. Propose something, if rejected get $q$. Intuitively: the higher the $q$, the higher the realized value. If proposer I will propose the median voter if closer to my ideal pt than status quo. 

The counterintuitive thing: low status quos actually make the median voters willing to accept relatively higher ones - I care only about distance, not direction. 

![[Game Theory IV - Extensive Form Games 2022-11-08 17.00.33.excalidraw|300]]

so your empirical observation depends on which subset of this population are looking at. If you have a lot to the left of the median voter, and you haven't thought about that, you will incorrectly conclude that there's a negative relationship. Theory can tell me to think about a nonlinear specification.


Upwards sloping part of the line is gridlock region. Preferences + rules preclude change. 



