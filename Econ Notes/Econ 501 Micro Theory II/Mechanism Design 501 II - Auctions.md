---
aliases:
- 'First Price Auction'
- 'Second Price Auction' 
- 'Revenue Equivalence'
creation date: Saturday, April 8th 2023, 12:47 pm
date updated: Friday, April 14th 2023, 1:16 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Mechanism Design 501 II - Auctions]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

We can think of auctions as an extension of the screening problem. Given a set of auction rules I want to understand how the players will behave (using the BNE solution concept) and then maximize seller revenue given that response. 

## Setup

An auction is a profile of functions $(q, t_1, \ldots, t_n)$. $q: \R^n \to \Delta$ is the probability of winning conditional on the bids, $q(b_1, \ldots, b_n)$. $t$ is the payments required of each player. 



```ad-important
title:Definitions: Auctions

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

## Example: First-Price Auction

Augment the format. Winner pays own bid, but you can't win unless your bid exceeds a reservation price $r$ which the deisgner chooses. Have $n$ buyers with type $\theta_i$ i.i.d with CDF $F$ having support $[\underline \theta, \overline \theta]$. Buyer utility is $\theta_i - b_i$. Ties broken uniformly at random (not that important). Then, what is revenue maximizing?

Write a bidder's strategy as some function $b: \Theta \to \R$. Conjecture that we can find a BNE with $b_i$ identical, increasing, with $\theta = r \implies b(\theta) = r$. Then we'll try to find this BNE, i.e. derive $b$. 

If $\theta < r$ then $b_i < r$ is optimal (I don't want to win). If $\theta_i \in (r, \overline \theta]$ then 
$$b_i \in \arg \max_{\theta_i \in (r, \overline \theta]} \{ (\theta_i - b_i)Pr(b_i > \max_{i \neq j} b(\theta_j))\}$$ in other words, $b_i$ maximizes the expected value of winning, a tradeoff between the value of winning and the probability of winning. As above let $H$ be the distribution of $\max_{i \neq j} \theta_j$. Then use the monotonicity assumption:
$$ Pr(b_i > \max_{i \neq j} b(\theta_j)) = Pr(b\inv(b_i) > \max_{i \neq j} \theta_j) = H(b\inv(b_i))$$ Here, $H$ can be calculated exactly as $F^{n-1}(b\inv(b_i))$ given the i.i.d. assumption. 

To find the FOC of the buyer's problem, note that the derivative of $f\inv(x)$ is $\dfrac{1}{f'(f\inv(x))}$. Then differentiate both sides of the problem.
$$\begin{align}
\frac{d}{db_i}(\theta_i - b_i)Pr(b_i > \max_{i \neq j} b(\theta_j)) &= \frac{d}{db_i}(\theta_i - b_i)H(b\inv(b_i))\\
&= -H(b\inv(b_i)) + (\theta_i - b_i)\left[ \frac{d}{dx} H(b\inv(b_i))\right]\\
H(b\inv(b_i)) &= (\theta_i - b_i) h(b\inv(b_i)) \left[ \frac{d}{dx} b\inv(b_i) \right]\\
&= \frac{(\theta_i - b_i) h(b\inv(b_i)) }{b'(b\inv(b_i))} \\
\end{align}$$

Now conjecture that $b_i = b(\theta)$. 

$$\begin{align}
H(\theta) &= \frac{(\theta_i - b(\theta))h(\theta)}{b'(\theta)} \\
b'(\theta)H(\theta)&= \theta_i h(\theta) - b(\theta)h(\theta)\\
\theta_i \frac{h(\theta)}{H(\theta)} = b'(\theta) + b(\theta)\frac{h(\theta)}{H(\theta)}
\end{align}$$

This is a linear differential equation. 

But can also approach by writing as 

$$\begin{align}
b'(\theta)H(\theta) + b(\theta)h(\theta) &= \theta_i h(\theta)\\
\frac{d}{d\theta} b(\theta)H(\theta) &= \theta_i h(\theta)\\
b(\theta)&= \frac{1}{ H(\theta)}\int_{r}^{\overline \theta} xh(x) dx\\
\end{align}$$

Now use integration by parts to simplify RHS:

$$\begin{align}
u &= x\\
dv &= h(x)dx\\
v &= H(x) + c \\
\int u(x)dv(x) &= u(a)v(a) - u(b)v(b) - \int_a^b v(x)du(x)\\
&= \theta_iH(\theta_i) - 0(H(r)) - \int_r^{\theta_i} H(x) \\
\end{align}$$

So: 

$$b(\theta_i) = \theta_i - \int_r^{\theta_i} \frac{H(x)}{ H(\theta)} dx$$

Do our assumptions hold? If $\theta = r$, then 

$$\begin{align}
b(r) &= r - \int_{r}^{r}H(x)/H(r)dx\\
&= r - \frac{1}{H(r)}\int_{r}^{r}H(x)dx\\
&= r - \frac{rH(r)}{H(r)}\int_{r}^{r}H(x)dx\\
&= 0
\end{align}$$

And $b$ is increasing in $\theta$ - to see this, interpret as the expected value of the next highest bid.

$$\begin{align}
b(\theta_i) &= \theta_i - \int_r^{\theta_i} \frac{H(x)}{ H(\theta)} dx\\
&=\frac{\theta_iH(\theta_i) - \int_r^{\theta_i} H(x)}{H(\theta_i)}\\
&= \frac{\int_{\underline \theta}^{\theta_i}  H(x)dx + \int_{\underline \theta}^{\theta_i}  xh(x)dx  - \int_r^{\theta_i} H(x)}{H(\theta_i)}\\
&= \frac{\int_{\underline \theta}^{r}  H(x)dx + E[\theta|\theta < \theta_i]}{H(\theta_i)}\\
\end{align}$$

The first term is constant, the latter is increasing; so this is increasing in $\theta$. 

### Different Approach

By the revelation principle, if there's an IC mechanism induced by FP auction there is an IC direct mechanism $q,t$. We can deduce $q$ and $t$: 

$$ q = \begin{cases} 1 &\text{ if } \theta_i \geq \max\{\max_{j \neq i} \theta_j, r\} \\ 0 &\text{ otherwise } \end{cases} $$

$$ t = \begin{cases} b_i &\text{ if } \theta_i \geq  \max\{\max_{j \neq i} \theta_j, r\} \\ 0 &\text{ otherwise } \end{cases} $$

In BNE, 

$$ U(\theta_i) =
\begin{cases} 0 & \text{ if } \theta_i < r \\
(\theta_i - b_i)H(\theta_i) &\text{ if } \theta_i \geq r
\end{cases}$$

By applying the [[Mechanism Design 501 I - Motivation, Screening Problem#Lemma and Envelope Formula|Myerson 1981 lemma]], incentive compatibility requires $q$ nondecreasing, and $U(\theta_i) = U(\underline \theta) + \int_{\underline \theta}^\theta q(x) dx$. $U(\underline \theta)$ is $0$, as is $U(\theta$) for $\theta < r$. Otherwise $U(\theta_i) = \int_r^{\theta_i} q(x) dx$. But since $q$ is simply $H$ (from the interim perspective of the agent), $U(\theta_i) = \int_r^{\theta_i} H(x)dx$. 


The Envelope formulation and this formulation should be equal.
$$\begin{align}
(\theta_i - b_i)H(\theta_i) &= \int_r^{\theta_i} H(x)dx\\
b_i &= \theta_i - \frac{1}{H(\theta_i)}\int_r^{\theta_i} H(x)dx 
\end{align}$$
```ad-note
title: Intuition

We've described the bid $b_i$ in the first-price auction as the expected value of the next highest bid. Note that this is the same as what you'd expect to pay for the same item, with the same type, in a second price auction. 
```

We can verify that these $b()$ form a BNE: given that others are bidding this discounted type you have no reason to bid more. And the corresponding $(q,t)$ satisfy IC because they satisfy the Myerson 1981 lemma by construction. 

## Seller Revenue 

