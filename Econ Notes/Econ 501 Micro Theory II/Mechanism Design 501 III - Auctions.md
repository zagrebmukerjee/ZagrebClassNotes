---
aliases:
- 'First Price Auction'
- 'Second Price Auction' 
- 'Revenue Equivalence'
creation date: Saturday, April 8th 2023, 12:47 pm
date updated: Sunday, April 9th 2023, 9:43 am

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
$$ q(b_1, \ldots, b_n) = \mathbf 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

$$ t_i = b_i \mathbf 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

A <font color=gree>second price auction</font>
$$\hspace{10pt} $$

$$ q(b_1, \ldots, b_n) = \mathbf 1(b_i > \max_{j \neq i} \{ b_j \}) $$
$$\hspace{10pt} $$

$$ t_i =  max_{j \neq i} \{ b_j \}\mathbf 1(b_i > \max_{j \neq i} \{ b_j \})  $$
$$\hspace{10pt} $$

```

The auction rules induce an incomplete-information game between the players. In this game, a strategy $\beta_i: \Theta_i \to \R$ defines bids; and the expected payoff is $U_i(b_i, \beta_{-i}(\theta_{-i})|\theta_i) = E[\theta_i q_i(b_i, \beta_{-i}(\theta_{-i}) - t_i(\ldots)]$; or, using linearity, $\theta_i E[q_i(b_i, \beta_{-i}(\theta_{-i}) - t_i(\ldots)]$. Here we're integrating only over other agents' types (assuming utility is linear in type. 

As a shorthand notation, we can write: 
$$ U_i(b_i, \beta_{-i}(\theta_{-i})|\theta_i) \equiv Q_i(b_i, \beta_{-i}) - T_i(b_i, \beta_{-i})$$
