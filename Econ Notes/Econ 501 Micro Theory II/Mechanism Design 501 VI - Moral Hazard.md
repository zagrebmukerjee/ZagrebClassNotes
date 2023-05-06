---
aliases:
creation date: Thursday, May 4th 2023, 6:53 pm
date updated: Saturday, May 6th 2023, 10:27 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 VI - Moral Hazard]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Problem

In previous problems we've considered the idea that agents' types are unobservable. We now consider the idea that agents' effort is unobservable - the asymmetric information in this sort of problem arises from agents who choose effort that has a noisy effect on outcomes, and principals who only observe the outcomes. 

The worker chooses effort $e$ and has payoff $v(w) - ce$ with $v$ increasing and concave (risk averse). The wage $w$ is in $\R$. For simplicity $e \in \{0, 1\}.$ Effort leads to a stochastic output $\pi \in \{ \pi_0, \ldots, \pi_n\} \subset \R$ with $\pi_{i +1} > \pi_i$. The distribution is dicated by PMF $P(\pi|e)$ with support $\{\pi_0, \ldots \}$. 

Assume that the workers' effort makes good outcomes more likely. Specifically, $P(\cdot|1)$ <font color=gree>first-order stochastically dominates</font> $P(\cdot|0)$. which means that $\forall k$, 

$$ \sum_{i=0}^k P(\pi_i|0) \geq \sum_{i=0}^k P(\pi_i|1)$$
and strict for some $k$. In other words, at every value of $\pi$, it's more likely that a draw from $P(\cdot |0)$ underperforms that than one from $P(\cdot|1)$. 

The employer payoff is the realization of $\pi - w$. They are risk neutral. Both have outside option $0$.

Timing of the game:
1) Principal makes a contract, $w:\{\pi_i\} \to \R$.
2) Agents accepts or not.
3) If accepted, agent chooses effort level.
4) If accepted, the profits and wage realize. 

The problem is, for the principal, how do I design a contract to motivate my desired level of effort?

## Observable Actions

Start with the case in which effort is observable. Here, the contract enforces $e$. The principal problem has two parts: 
1) Find the $w$ that motivates each level of effort and 
2) choose the highest profit effort level. 


The principal's optimization problem is 

$$ \max_{w(\cdot)} \sum_{i=0}^n P(\pi_i |e(w))(\pi_i - w)$$
subject to the participation constraint on the agent, 
$$ \sum_{i=0}^n P(\pi_i|e(w))v(w(\pi)) - ce(w) \geq 0$$
The latter constraint will bind at optimum.  

The agent is paid a constant wage. To see this, note that the agent is risk-averse and the principal is not: so any nonconstant wage leaves something on the table, since the agent would give up some expected value for less variance while the principal is indifferent. 

The optimum constant wage constitutes "full insurance", by the same logic - ie. the agent is protected against the variance in $\pi$. 

The constant optimum wage can be backed out of the participation constraint with $v(\bar w) = ce$. Then the principal can just compare $e=0$ payoff to $e=1$: 


$$e^* = 1 \iff \sum P(\pi|1) - P(\pi|0) > v\inv (c) - v\inv(0)$$
## Unobservable Action

Now the principal only sees $\pi$ and so has a function $w(\pi)$. The principal problem has three parts: 
1) Determine the set of implementable efforts/actions;
2) Find the $w$ that motivates each level of effort and 
3) choose the highest profit effort level. 


It's useful to think of the principal as minimizing wage expenditure to attain a given effort $e$. 

$$ \min_{w()} \sum P(\pi|e) w(\pi) \text{ subject to } \sum P(\pi|e)v(w(\pi) - ce \geq 0$$

But there is a new constraint, the incentive compatibility. The principal needs to get the worker not to choose $e' \neq e$. So
$$ \sum P(\pi|e)v(w(\pi)) - ce \geq \sum P(\pi|e')v(w(\pi)) - ce'$$

It's easy to imlement $e= 0$, by setting constant wage $\bar w = v\inv(0)$. In this case the worker does nothing and has no utility. IC is trivially respected, since work is monotonically bad. The principal's payoff is the same in the observable action case. 

The principal might choose this if they think that, observable or not, an agent's effort is unrelated to the profits. 

### Incentive to Work

It's when I'd want to implement $e=1$ that things get fun. Now IC is going to matter. The constant wage is incompatible with the IC constraint, which means that the outcome involves the principal putting risk onto the agent - 'inefficient'. 

The cost minimization dictates that both IC and participation constraint are going to bind. Our employer will pay no more than they have to but will also have to incentivize effort. 

Can qualitatively describe the loss for the principal. From the PC get:
$$ \sum P(\pi|1) v(w^*(\pi)) = c $$
From [[Jensen's inequality]], since $v$ is concave:
$$ v\left(E[w(\pi)\right]) > E[v(w(\pi))]$$
so, since $\bar w = v \inv(c)$
$$ v\left( \sum P(\pi|1)w^*(\pi) \right) > c$$
$$  \sum P(\pi|1)w^*(\pi)  > \bar w$$
 <font color=#F7B801>hide your effort, kids!</font>


### Optimal Contract

So far we have made observations about efficiency purely from the constraint, without actually finding optimal contract. What is the optimum? Suppose we want to incentivize effort $e = 1$. Then we can describe the cheapest way to do so: 

$$ \min_{w(\cdot)} \sum P(\pi|1)w(\pi) \text{ subject to } \sum P(\pi|1)v(w(\pi)) -c \geq 0$$
with also the IC constraint, 
$$ \sum P(\pi|1) v(w(\pi)) - c \geq \sum P(\pi|0)v(w(\pi))$$
We can do a chance of variables $u( \pi) \equiv v(w(\pi))$ whcih makes the problem 
$$\max - \sum p(\pi|1) v\inv [u(\pi)] \text{ subject to } \sum P(\pi|1) u(\pi) - c = 0$$
$$ \sum P(\pi|1)u(\pi) - c \geq \sum P(\pi|0)$$
The objective function is concave: $v$ is concave, so $v\inv$ is convex, so $-v\inv$ is concave again. So Kuhn Tucker conditions can be used and solving this reparametrized problem will solve the main one.

The KT conditions take the form

$$ - P(\pi|1) (v\inv)' (u(\pi)) + \lambda  P(\pi|1) + \mu[ P(\pi|1) - P(\pi|0)] =0 $$
so this is linear in $u$. Here, $\lambda$ is the multiplier on the participation constraint and $\mu$ the multiplier on the IC constraint. Using the [[Derivative Rules|Derivative of an Inverse]] we have 

$$(v\inv)' (u(\pi)) = v'[v\inv(u(\pi))]\inv = v'(w^*(\pi))\inv $$
where the latter holds at equilibrium. Then some algebra on the condtiions: 

$$\begin{align}
0 &=  - P(\pi|1) (v\inv)' (u(\pi)) + \lambda  P(\pi|1) + \mu[ P(\pi|1) - P(\pi|0)] \\
&=  - \frac{P(\pi|1)}{ v'(w^*(\pi))}+ \lambda  P(\pi|1) + \mu[ P(\pi|1) - P(\pi|0)] \\
&= -\frac{1}{v'(w^*(\pi))} + \lambda + \mu\left[1 - \frac{P(\pi|0)}{P(\pi|1)}\right]\\
\frac{1}{v'(w^*(\pi))}  &= \lambda + \mu\left[1 - \frac{P(\pi|0)}{P(\pi|1)}\right]\\
\end{align}$$
There is no general closed form solution to find this - after all we must describe it at all $\pi$ - but this form allows for some descriptions of the optimal contract. 

We know from this that the PC binds: 
- $v'()> 0$
- For some $\pi$ it must be the case that $P(\pi|0)\geq P(\pi|1)$
- so  $1- \frac{P(\pi|0) }{P(\pi|1) }$ is nonpositive somewhere. 
- This necessitates that $\lambda$ is positive. 

Therefore the participation constraint binds. 


We also know that $\mu$ is positive. If $\mu = 0$ the wage is constant, which is incompatible with the IC constraint/equilibrium <font color=#F7B801> why can't mu be negative</font>. So the IC constraint also binds at optimum. 

We can also see that $w^*$ is larger whereever if $P(\pi|0)/P(\pi|1)$ is smaller. So the agent should be rewarded at those points where their effort makes mroe of a difference in the outcomes. 

This condition is called the Monotone Likelikhood Ratio Condition/Property MLRP. It's stronger than first-order stochastic dominance. 


### Risk Neutral Agent

Observable action case has any $w^*$ optimal where the participation constraint binds.  But in the unobservable case the principal is not worse off. They can simply set $w(\pi) = \pi - \alpha$ where $\alpha$ causes the participation constraint to bind again. 


## Limited Liability

We might be interested in the scenario in which wages cannot be negative. Then we have three constraints on the principal problem. 


## Continuous Effort