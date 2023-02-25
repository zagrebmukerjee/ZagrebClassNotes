---
aliases:
creation date: Monday, February 20th 2023, 9:58 am
date updated: Saturday, February 25th 2023, 6:34 pm

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

One way to solve a game, or at least to narrow a search space, is to delete dominated strategies. Looking at each player, remove any rows/columns corresponding to a dominated strategy. Upon doing so, more strategies might become dominated, so this process can be iterated.  A game that's solvable by iterated deletion of dominated strategies is called <font color=gree>dominant solvable</font>. 

There's a definite temptation to iteratively delete weakly dominated strategies But this doesn't necessarily work; in particular, iteratively deleting dominated strategies can produce different solutions depending on the order in which you do it  <font color=#F7B801>why - proof?</font>

Backward induction is a specific form of iterated deletion of weakly dominated strategies, but using the fact that the extensive form imposes ordering on the game. 

Iterative deletion algorithm can be written down formally but it's not that interesting to do so. One wrinkle there is that one should consider mixed strategies as being dominators. But eliminating pure strategies first is fine. A mixed strategy that has positive probability on a strictly dominated pure strategy will also be dominated. 

## Best Response/Reply

A strategy $\sigma_i$ is a <font color=gree>best response</font>  to $\sigma_{-i}$ if $\sigma_i \in \arg\max u_i(\sigma_i, \sigma_{-i})$. 

Introduce here a notion of <font color=gree>rationalizability</font>. 