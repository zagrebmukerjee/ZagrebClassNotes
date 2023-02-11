---
aliases:
creation date: Saturday, February 11th 2023, 1:18 pm
date updated: Saturday, February 11th 2023, 2:03 pm

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

| Strategy Profile | Probability | Event           |
| ---------------- | ----------- | --------------- |
| $S_1, S_2$       | $1/3$       | $d \in \{3,4\}$ |
| $S_1, C_2$       | $1/3$       | $d \in \{1,2\}$  |
| $C_1, S_2$       | $1/3$       |          $d \in \{ 5,6\}$ |
| $C_1, C_2$       | 0           |               $\emptyset$  |

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

Instead of thinking about the correlation st