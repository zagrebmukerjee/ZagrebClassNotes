---
aliases:
creation date: Monday, February 20th 2023, 9:58 am
date updated: Monday, February 27th 2023, 6:13 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Game Theory 501 II - Solution Fundamentals]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Dominance

The concept of dominance is best understood in the normal form of a game. Colloquially, it's a strategy that's just always worse than some other choice. 

$\sigma_i$ is <font color=gree>strictly dominated</font> if $\exists \, \sigma'_i$ such that $\forall s_{-i}$, $u(\sigma_i, s_{-i}) < u(\sigma_i', s_{-i})$. 

Note here that it's sufficient to check pure strategies of other players: if $\sigma'$ dominates for pure strategies it will dominate also for mixtures (ie linear combinations of pure strategy outcomes). But your dominating/dominated strategies can be pure or mixed. 

|     | L   | R   |
| --- | --- | --- |
| T   | -2   | 1  |
| M   | 0   | 0   |
| B   | 1   | -2  | 

Only payoffs for Player $1$ are listed - Player 2's are irrelevant for this 

The strategy of playing top with probability $1/2$ and bottom with probability $1/2$ has expected value $-1/2$ for each of P2's moves, which makes it dominated by $M$. 

This gives us some ideas for solving games: to say that players won't play strictly dominated strategies. For some games we can talk about undominated strategies, or strictly dominant. 

There are also <font color=gree>weakly dominated</font> strategies where the inequality above is weak - a strategy is weakly dominant over another if it's at least as good everywhere and better somewhere. 

### Iterated Deletion

One way to solve a game, or at least to narrow a search space, is to delete dominated strategies. Looking at each player, remove any rows/columns corresponding to a dominated strategy. Upon doing so, more strategies might become dominated, so this process can be iterated. A game that's solvable by iterated deletion of dominated strategies is called <font color=gree>dominant solvable</font>. 

There's a definite temptation to iteratively delete weakly dominated strategies But this doesn't necessarily work; in particular, iteratively deleting dominated strategies can produce different solutions depending on the order in which you do it <font color=#F7B801>why - proof?</font>

Backward induction is a specific form of iterated deletion of weakly dominated strategies, but using the fact that the extensive form imposes ordering on the game. 

Iterative deletion algorithm can be written down formally but it's not that interesting to do so. One wrinkle there is that one should consider mixed strategies as being dominators. But eliminating pure strategies first is fine. A mixed strategy that has positive probability on a strictly dominated pure strategy will also be dominated. 

## Best Response/Reply

A strategy $\sigma_i$ is a <font color=gree>best response</font> to $\sigma_{-i}$ if $\sigma_i \in \arg\max u_i(\sigma_i, \sigma_{-i})$. 

Introduce here a notion of <font color=gree>rationalizability</font>. Rationalizable strategies are found as follows: Start with a game. Remove all strategies that are never best responses and then iterate. 

The idea here is that we're requiring players to operate rationally, and think of others likewise - i.e. we're not allowing for me to form a strategy based on the idea that you're crazy. But I don't have to form a strategy based on you optimizing necessarily. 

Every best response is undominated (it can't be a best response otherwise). So BR is a subset of undominated. 

For $2$ players, any undominated pure strategy is a best response; doesn't generalize. 


## Nash Equilibrium

We're in a Nash Equilibrium if every player is best-responding to every other player. Specifically, the NE is the strategy profile such that that is occurring (not the outcomes).

Existence of NE comes from [[Brouwer Fixed Point Theorem]] or [[Fixed Point Theorems - Brouwer and Kakutani|Kakutani's Fixed Point Theorem]] - the 'best response to others' best response to my strategy' correspondence has a fixed point. Existence only guarantees mixed NE exists. 

### Finding NE
#### Pure

There are several approaches to NE finding.  

Start with removing strictly dominated strategies; an NE will never involve one of these.

The simplest case is when the game is a straightforward normal form 'box'; then In each row, mark the best payoff for column player; in every column, mark the best payoff for row player. These are the best responses. If two mark coincide, the corresponding strategy profile is an NE.

More generally, a PSNE is the coincidence of pure-strategy (ie no-randomization) best responses. So if a strategy can be characterized by a best-response correspondence - e.g the entry decision of one firm with respect to the production decision of another - then we can look for a fixed point, where both players are best-responding to each other. 

#### Mixed

The core intuition is that mixing requires indifference. I'll only be willing to randomize across my options if I have the same expected utility for each of them. So this defines/restricts the probabilities being used by the other players. Solving these probabilities one player at a time allows one to characterize mixed NEs. 


```ad-example 
title: Battle of the Sexes

|     | P   | G   |
| --- | --- | --- |
| P   | 2,1 | 0,0 |
| G   | 0,0 | 1,2 |



First strategy: mark BRs, the bolded cells. 



|     | P   | G   |
| --- | --- | --- |
| P   | **2,1** | 0,0 |
| G   | 0,0 | **1,2** |

This lets us find two pure-strategy NEs: P,P and G,G. 
For an MSNE, we need both players to be indifferent between P and G. With symmetry it suffices to look at Player 1 only. 
$$\begin{align}
E[u_1(P)] &= E[u_1(G)] \\
E[u_1(P)|s_2 = P]Pr(s_2= P)+  E[u_1(P)|s_2 = G]Pr(s_2= G) &= E[u_1(G)|s_2 = P] Pr(s_2= P) + E[u_1(G)|s_2 = G] Pr(s_2= G)\\
2p  &= 1(1-p)\\
p &= 1/3\\
\end{align}$$

So in order for Player $1$ to be willing to randomize, Player $2$ needs to play $P$ with probability $1/3$ and $G$ with probability $2/3$. The opposite calculation will give probabilities of $1/3 G$, $2/3P$. These randomization plans are a mixed strategy NE. 

In this NE, PP is played with probability 2/9, PG with probability 1/9, GP with probability 4/9, and GG with probability $2/9$. So the expected utility of some player is $5/9$. 

```

