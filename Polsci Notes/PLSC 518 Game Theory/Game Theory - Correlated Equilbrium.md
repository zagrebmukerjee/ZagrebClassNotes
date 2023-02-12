---
aliases:
creation date: Saturday, February 11th 2023, 1:18 pm
date updated: Saturday, February 11th 2023, 2:41 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/game_theory'
- '#status/🚧'
---

# [[Game Theory - Correlated Equilbrium]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

[[Game-Theoretic Solution Concepts]]


Correlated equilbrium is a solution concept developed to capture the probability that players may communicate in particular kinds of ways that create 'self-enforcing' equilibria above and beyond any Nash equilibrium. 

## Example: Chicken

Consider the game of Chicken.

### Nash

| Player 1 | Player 2 |          |
| -------- | -------- | -------- |
|          | Swerve   | Continue |
| Swerve   | 2,2      | 3,0      |
| Continue | 0,3      | -1,-1    |

The game has two PSNEs: $S_1C_2$ and $C_1 S_2$. A mixed-strategy NE can be found with the indifference conditions: 

$$\begin{align}
E[u_1(Swerve_1)] &= p \times u_1(Swerve_1, Swerve_2) + (1-p) \times u_1(Swerve_1, Continue_2)\\
&= 2p + 0\\
E[u_1(Continue_1)] &= 3p -(1-p) \\
2p &= 4p - 1 \\
p &= 1/2\\
\end{align}$$
Symmetrically: both players swerve or continue with equal probability. Each square obtains with equal probability; the expected payoff for a player is $2/4 + 3/4 + 0/4 -1/4 = 1$. 

### Correlated
Now, suppose the players acquire a computer program that rolls a die ($d= 1-6$ with equal probability) and communicates to the players *privately* as follows: 

1) Tell Player 1: Swerve if $d \leq 4$, continue otherwise; and 
2) Tell Player 2: Swerve if $d \geq 2$, continue otherwise. 

So if Player 1 hears "Swerve", they know the die says $1,2,3$ or $4$; which means P2 hears $S$ or $C$ with equal probability. Suppose P2 complies: then, 
$$\begin{align}
E[u_1(S_1)| \text{"Swerve"}_1] &= 1/2 \times E[u_1(S_1, S_2)] + 1/2 \times E[u_1(S_1, C_2)]\\
&= (1/2)(1) + (1/2) (0) = 1/2\\
E[u_1(C_1)| \text{"Swerve"}_1] &= 1/2 \times E[u_1(C_1, S_2)] + 1/2 \times E[u_1(C_1, C_2)]\\
&=  (1/2)(3) -(1/2)(1) = 1/2
\end{align}$$
Then Player 1 might as well comply. Similar logic gets us what happens if Player 1 hears "Continue" : then I know Player 2 has heard "Swerve". 
$$\begin{align}
E[u_1(C_1)| \text{"Continue"}_1] &= 3\\ 
E[u_1(S_1)| \text{"Continue"}_1] &= 2\\
\end{align}$$
So I prefer compliance.


In this case, the expected utility of Player 1 from this whole scheme is: 
$$\begin{align}
E[u_1] &= E[u_1| \text{"Swerve"}_1]P(\text{"Swerve"}_1) + E[u_1| \text{"Continue"}_1] P(\text{"Continue"}_1)\\
&= (2/3)(1/2) + (1/3)(3) = 4/3\\
\end{align}$$
So we're better off than before. 



## General Form

### Complex Definition

A correlated equilibrium requires a 'correlating structure': 
- Some outcome space $\Omega$;  and a probability measure $p$:
- A set of partitions of $\Omega$, $P = \{P_i\}$  representing what each player can't distinguish.

So in the above case, the probabilities are 

| Probability | Event           |
 | ----------- | --------------- |
| $1/3$       | $d \in \{3,4\}$ |
| $1/3$       | $d \in \{1,2\}$  |
|$1/3$       |          $d \in \{ 5,6\}$ |
| 0           |               $\emptyset$  |

It's easy to see how we ended up 'better off' than the mixed Nash; this strategy precluded the worst outcome of a crash. 

The partitions are: 

| Player | Can Distinguish Between |
| ------ | --------- |
| Player 1       | $d \in \{1,2, 3,4\}$ or $d \in \{5,6\}$ |
| Player 2       | $d \in \{1,2\}$ or $d \in \{3, 4,5, 6\}$

This defines some posterior probabilities, $q(\omega)$; for the game of Chicken they're described by the conditioning above. 

Then, a strategy is a function $\sigma_i: \Omega \to A_i$, with the restriction that $\forall \, p \in P_i, \;\omega_1, \omega_2 \in p \implies \sigma_i(\omega_1) = \sigma_i(\omega_2)$; this represents that a player will act based on the message they receive and can't know more than that. 

A correlated equilibrium, then, is a correlating structure and a set of strategies $\sigma_i$ such that, 

$$  \forall i, \forall \sigma_i' \in S_i,  \sum q(\omega)u(\sigma_i(\omega), \sigma_{-i}(\omega)) \geq \sum q(\omega)u(\sigma_i'(\omega), \sigma_{-i}(\omega))$$
### Better Definition

Instead of thinking about the correlating structure and whatever device (cards, coins, RNGs, whatever) we can just realize that any such device creates a distribution over possible actions of players/ terminal nodes. Then ditch the die and make the simpler table:

| Messages Sent | Probability | 
| ---------------- | ----------- | 
| $S_1, S_2$       | $1/3$       | 
| $S_1, C_2$       | $1/3$       | 
| $C_1, S_2$       | $1/3$       | 
| $C_1, C_2$       | 0           |

We still have a partition: in this case, Player 1 can't distinguish $S_1, S_2$ from $S_1, C_2$, and $C_1, S_2$ from $C_1, C_2$ 

Then there's a correspondingly simpler equilbrium definition: given that you're told $\sigma_i$, and presuming everyone else is doing what they are told, you don't want to deviate: 

$$ \sum p(s_{-i}|s_i) u(s_i, s_{-i}) \geq  \sum p(s_{-i}|s_i) u(s_i', s_{-i}) $$



## Finding Correlated Equilibria


Example: this game 

|   | L   | M   | R   |
| -------- | --- | --- | --- |
| U        | 0,0 | 5,4 | 4,5 |
| M        | 4,5 | 0,0 | 5,4 |
| D        | 5,4 | 4,5 | 0,0    |

There is no PSNE, but there's an MSNE of mixing equally across every strategy. So then my expected utility is $4/3 + 5/3 + 0 = 3$. 

To find a correlated equilibrium, we need to find probabilities across the $9$ boxes: call them $p_1, \ldots, p_9$. We want these such that every player doesn't want to deviate from what they are told to do, which will give us a linear system of requirements. 

We want player 1 to play $U$ if told $'U'$. So it needs to be better than both $M$ and $D$. Take the first requirement:  

$$\begin{align}
E[u(U|'U') &\geq E[u(M_1|'U')\\
P('U') &= p_1 + p_2 + p_3\\ 
E[u(U|'U') &= \sum_{S_{-i}} P('s_{-i}'|'U')u_1(U, s_{-i})\\
&= (0)P(L|'U') + (5)P(M|'U') + (4)P(R|'U')\\
(0)P(L|'U') + (5)P(M|'U') + (4)P(R|'U') &> (4)P(L|'U') + (0)P(M|'U') + (5)P(R|'U')\\
\end{align}$$

Observe that the conditioning event's the same on both sides, and recall the definition. 

$$P('L'|'U') = P('U' \cap 'L')/P('U')$$

Now suppose $P('U') > 0$; then we can just replace the conditional probabilities above with unconditional joint probabilities.  Doing the same across all the possible messages for Player 1 gets us the following system: 
$$\begin{align}
5p_2 + 4p_3 &\geq 4p_1+ 5 p_3 \\
&\geq 5p_1 + 4p_2  \\
4p_4 + 5p_6 &\geq 5p_5 + 4p_6 \\
&\geq 5p_4 + 4 p_5\\
5p_7 + 4 p_8 &\geq 5p_8 + r p_9\\
& \geq 4 p_7 + 5p_9 \\
p_1 + \ldots + p_9 &= 1\\
p_1, \ldots p_9 &\geq 0
\end{align}$$

These equations define a polytope in $\R^8$ of feasible probabilities. Using the payoffs we can project this polytope down into $\R^2$, 'payoff space', to determine what payoffs the players can obtain through coordination.