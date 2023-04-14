---
aliases:
- 'First Price Auction'
- 'Second Price Auction' 
- 'Revenue Equivalence'
creation date: Saturday, April 8th 2023, 12:47 pm
date updated: Sunday, April 9th 2023, 9:59 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Mechanism Design 501 III - Auctions]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Setup

An auction is a profile of functions $(q, t_1, \ldots, t_n)$. $q: \R^n \to \Delta$ is the probability of winning conditional on the bids, $q(b_1, \ldots, b_n)$. $t$ is the payments required of each player. 



```ad-important
Definitions: Auctions

A <font color=gree>first price auction</font> has the winner being the highest bid, and paying his bid; others pay nothing. In the notation above: 
$$\hspace{10pt} $$
$$ q(b_1, \ldots, b_n) = \mathbb 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

$$ t_i = b_i \mathbb 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

A <font color=gree>second price auction</font>
$$\hspace{10pt} $$

$$ q(b_1, \ldots, b_n) = \mathbb 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

$$ t_i =  max_{j \neq i} \{ b_j \}\mathbb 1(b_i > \max_{j \neq i} \{ b_j \})  $$
$$\hspace{10pt} $$

```

The auction rules induce an incomplete-information game between the players. In this game, a strategy $\beta_i: \Theta_i \to \R_+$ defines bids; and the expected payoff is $U_i(b_i, \beta_{-i}(\theta_{-i})|\theta_i) = E[\theta_i q_i(b_i, \beta_{-i}(\theta_{-i}) - t_i(\ldots)]$; or, using linearity, $\theta_i E[q_i(b_i, \beta_{-i}(\theta_{-i}) - t_i(\ldots)]$. Here we're integrating only over other agents' types (assuming utility is linear in type. 

As a shorthand notation, we can write: 
$$ U_i(b_i, \beta_{-i}(\theta_{-i})|\theta_i) \equiv Q_i(b_i, \beta_{-i}) - T_i(b_i, \beta_{-i})$$
Then $\beta^*$ is a BNE if (familiarly): 

$$ \forall i\; \forall \theta_i\; \beta^*_i \in \arg\max_{b_i \in \R_+} U_i(b_i, \beta_{-i}|\theta_i)$$
## Solving Auction Problems

### Envelope Approach

1) Restrict search for a candidate equilibrium $\beta^* = \beta^*_1, \ldots, \beta^*_n$. For convenience, in a symmetric setting we can look for symmetric equilibria, with $\beta_i^* = \sigma$. We can also focus on monotone solutions with $\sigma(\theta)$ increasing in $\theta$. We can also specify a $0$ payoff to the lowest bid in the 1PA/2PA setting. 
2) Using the rules, write down the expected payoff for an agent, $U^*(\beta^*(\theta_i), \beta^*(\theta_{-i}|\theta_i)$ as a function of $\beta^*$.
3) Use the [[Mechanism Design 501 I - Motivation, Screening Problem#Lemma and Envelope Formula|Envelope Formula]] to find an alternative formulation of the auction payoff. 
4) Equate the expressions and solve for $\beta^*$. 
5) Check that it fulfils the conditions of symmetry, monotonicity, $0$ payoff to the lowest. 

Very often, the expected payoff $U_i$ is quasilinear $\theta_i Q_i (\ldots) - T_i(\ldots)$. The $q$ function is frequently 'highest bidder wins', as in the first and second price auctions above. In that case, $Q_i = E[\mathbb 1\{ b_i(\theta_i) \geq \max_{i \neq j}\{\beta_j^*(\theta_j)\}]$

By symmetry then we can say $Q_i = E[\mathbb 1\{ b_i(\theta_i) \geq \max_{i \neq j}\{\sigma(\theta_j)\}$; and with monotonicity reduce it further to $E[\mathbb 1\{\theta_i \geq \max_{i \neq j} \theta_j\}$, or $Pr(\theta_i \geq \max_{i \neq j} \theta_j)$; is my type the biggest? 

Write this as $H(\max_{j \neq i} \theta_j)$; if $\theta_j$ are iid, then this is $F^{n-1}(\theta)$.

```ad-example
title: Example: Symmetric First-Price Auction

In this case: 
$$\begin{align}
Q_i &= H(\theta_i)\\
T_i &= \sigma(\theta_i)H(\theta_i)\\
U_i(\beta^*(\theta_i), \beta^*_{-i}) &= \theta_i H(\theta_i) - \sigma(\theta_i)H(\theta_i)\\
\end{align}$$

```

## Revenue Maximization 

### First-Price Auction

Augment the format. Winner pays own bid, but you can't win unes