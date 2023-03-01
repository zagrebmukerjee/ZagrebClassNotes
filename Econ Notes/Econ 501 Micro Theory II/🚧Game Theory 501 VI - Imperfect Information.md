---
aliases:
creation date: Sunday, February 26th 2023, 12:57 pm
date updated: Sunday, February 26th 2023, 3:29 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[🚧Game Theory 501 VI - Imperfect Information]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Representing Uncertainty

### Incomplete Information

The representation of games with incomplete information can be challenging. Suppose the following transformation of the Battle of the Sexes: 

|     | P               | G     |
| --- | --------------- | ----- |
| P   | $2 + \theta_1, 1$ | $0,0$ |
| G   | $0,0$           | $1, 2 + \theta_2$      |


Here, instead of static preferences, we've said each player has some degree of preference for $P$ vs $G$ that's unknown to the other player. So in order to make a decision, Player $1$ needs to consider their own preference. But they also need to form some belief about Player 2's preference. For instance, if they know $\theta_1 = 1$ but believe $\theta_2 = 5$ then they will think it much more likely that Player $2$ will choose $G$.

But to turn this into a strategy, Player $1$ also needs to think about Player $2$'s expectations about Player $1$'s preference; even if $\theta_2 = 5$, if Player $2$ thinks $\theta_1 = 10$ then they will believe it more likely that Player $1$ will play $P$; by ignoring that possibility, Player $1$ would forgo a potential gain. 

But then Player $1$ needs to understand that Player $2$ understands the above; and so Player $2$ will incorporate some guess about Player $1$'s guess about Player $2$'s guess about Player $1$. We can very quickly enter some sort of problem of infinite regress.

### Imperfect Information

A framework to analyze such games was developed by Harsanyi (with no particular basis in fact, but an eye to tractability). One may suppose that the game has a specific type of incomplete information: Nature draws $\theta_1, \theta_2$ from a commonly known distribution. So players have *common priors* and then can anchor their guesses about others' strategies in those priors. 

Suppose $\theta_i$ is drawn from $\text{Unif}(0, \epsilon_i)$, and both players know that. Player $1$ doesn't know what Player $2$ will do, but knows that it will be increasing in $\theta_2$. Therefore, Player $2$'s choice can be represented as a cutoff: if $\theta_2 > c_2$, $s_2 = G$.  

Then we can reason about Player $1$'s choice by the same monotonicity logic, ie. finding $c_1$ such that $\theta_1 > c_1 \implies s_1 = P$. It follows that for $\theta_1 = c_1$, Player $1$ is indifferent between $P$ and $G$.

$$\begin{align}
E[u_1(P)] &= E[u_1(G)]\\
(2 + \theta_1) P( \theta_2 < c_2) &= (1)P(\theta_2 > c_2)\\
(2 + \theta_1) \frac{c_2}{\epsilon_2} &= 1 - \frac{c_2}{\epsilon_2}\\
(2 + \theta_1) c_2 &= \epsilon_2 - c_2\\
3c_2 + c_1c_2  &= \epsilon_2 \\
c_1(c_2) &= \epsilon_2/c_2 - 3\\
c_1^* &=  \epsilon_2/c_2(c_1^*) - 3\\
&=  \epsilon_2/(\epsilon_1/c_1 -3) - 3\\
c_1 + 3 &= \frac{\epsilon_2c_1}{\epsilon_1 -3c_1} \\
0&=(c_1 + 3)(\epsilon_1 - 3c_1) - \epsilon_2 c_1 \\
&=c_1 \epsilon_1  + 3\epsilon_1 - 3c_1^2 - 9c_1 - \epsilon_2 c_1 \\
&= -3c_1^2 + c_1(\epsilon_1 - \epsilon_2 - 9) + 3 \epsilon_1\\
&= 3c_1^2 - c_1(\epsilon_1 - \epsilon_2 - 9) - 3 \epsilon_1\\
\end{align}$$

For simplicity, solve for the special case where $\epsilon_1 = \epsilon_2$. Then use the quadratic formula: 

$$\begin{align}
c_1 &= \frac{3 + \sqrt{9 +4 \epsilon}}{2}
\end{align}$$

### Public Goods Provision

Two players simultaneously decide whether to pay for a public good. If at least one pays, both accrue a benefit of $1$. If none do, $0$. Cost of contributing is $c_i$. $c$ is drawn fro continuous and strictly increasing cdf $F$ on $[\underline c, \overline c]$. 

A strategy, then, is a map from $\text{supp} \; c$ into $\{0,1\}$. Player $i$ maximizes utility: 

$$ u_i = \max_j s_j - c_i s_i$$
A best response is a function that, for any $c_i$, maximizes $E[u_(c_i|s_{-i})]$ . So a BNE has each player playing $s_i^*$ that maximizes $E[u(s_i, s_{-i}^*, c_i]$. $c_j$ doesn't directly matter for this maximization problem, but it'll enter into others' calculations. 

Suppose I am player $i$. Then there's an equilibrium probability $z_j$ that $j$ contributes. So I will contribute if $c_i < 1- z_j$; ie if it's worth it to me to insure against the other guy not contributing. In other words, there's another cutoff strategy: Player $i$ contributes if $c_i \in [\underline c, c^*_i]$. 

So Player $1$ knows that $z_j = F(c_j^*)$; the probability another will contribute is the probability that their cost is low enough. Then I can solve the above in the two player case, again using the idea that at $c_i^*$ I am indifferent:

$$\begin{align}
E[u(s_i = 0, c_i^*)] &= E[u(s_i = 1, c_i^*)]\\
1 - c_i &= z_j\\
&= F(c_j)\\
&= F(1 - F(c_i))\\
F\inv(1 - c_i) &= 1 - F(c_i)\\
\end{align}$$

This dictates a symmetry to the problem: $c_i = c_j = 1 - F(c_j)$. 
