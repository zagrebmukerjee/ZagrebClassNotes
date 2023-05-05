---
aliases:
creation date: Thursday, May 4th 2023, 6:53 pm
date updated: Friday, May 5th 2023, 10:36 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 VI - Moral Hazard]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

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

Start with the case in which effort is observable. Here, the contract enforces $e$. The principal's optimization problem is 

$$ \max_{w(\cdot)} \sum_{i=0}^n P(\pi_i |e(w))(\pi_i - w)$$
subject to the participation constraint on the agent, 
$$ \sum_{i=0}^n P(\pi_i|e(w))v(w(\pi)) - ce(w) \geq 0$$
The latter constraint will bind at optimum.  

The agent is paid a constant wage. To see this, note that the agent is risk-averse and the principal is not: so any nonconstant wage leaves something on the table, since the agent would give up some expected value for less variance while the principal is indifferent. 

The optimum constant wage constitutes "full insurance", by the same logic - ie. the agent is protected against the variance in $\pi$. 

The constant optimum wage can be backed out of the participation constraint with $v(\bar w) = ce$. Then the principal can just compare $e=0$ payoff to $e=1$: 


$$e^* = 1 \iff \sum P(\pi|1) - P(\pi|0) > v\inv (c) - v\inv(0)$$
