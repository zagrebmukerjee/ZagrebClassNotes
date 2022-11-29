---
aliases:
creation date: Monday, November 28th 2022, 2:51 pm
date updated: Monday, November 28th 2022, 2:52 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium IIa - Generalized Existence]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

In [[General Equilibrium II - Existence]] a specific case is discussed with restrictions on the economy <font color=#F7B801>what</font>

This argument gives a more general treatment. 

## Setup

### Quasiequilibrium 
Reference: definition 
Now  introduce a notion of Walrasian Quasiequilibrium. 


==== waiting for sync ====


Suppose a WQE $x^*, y^*, p$; suppose convex consumption sets and continuous preferences. Then any consumer for whom $\exists x_i \in X_i: px_i < w_i$, ie some bundle cheaper than their budget set, is preference maximizing. If all consumers have some such $x_i$ then the WQE is a WE. 

Proof:
Fix $i$. Suppose WQE and the cheaper bundle but not maximizing. If so, there exists $x'$ such that $x' \succ x^*$ and $px' = w_i$. Let $x$ be a cheaper bundle. Define a sequence $\lambda_n$ such that $\lambda_1 = 0$ and $\lambda_n \to 1$. Then the convex combination  $x_n = \lambda_n x' + (1-\lambda_n) x$  has $px' < w_i$ for all $n$. But since $x' \succ x^*$ there is some ball of radius $r > 0$ around $x'$, with $x'' \in B \implies x'' \succ x^*$. But since $x_n \to x'$, there is some $N$ such that $n > N \implies x_n \in B$. So those $x_n$ are preferable to $x^*$ but cheaper - a contradiction of WQE condition. 


## Existence

Suppose an economy with $I$ consumers, $J$ firms, $I, J > 0$, with these properties; 
1) For each $i$, 
	1) $X_i \subset \R^L$, and $X_i$ closed and convex
	2) $\succsim_i$ is rational, continuous, LNS, convex on $X_i$
	3) $\omega_i \geq \hat x_i$for some $x_i \in X_i$
2) $Y_j \subset \R^L$, is closed, convex, has free disposal, includes $0$. 
3) The set of feasible allocations $A$ is compact, where 
$$A = \{ x, y\in \R^{LI + LJ}: \forall \;i, x\in X_i;\; \forall \, j, y \in Y_j; \; \sum_i x_i \leq \sum_i \omega_i + \sum_j y_j\}$$
Then a WQE exists. 

### Proof

First, define a Free Disposal Quasiequilibrium. $x^*, y^*, p$ are an FDQE if: 
1) profit max
2) quasiequilibrium 'maximization'
3) $\sum x_i^* \leq \sum \omega_i + \sum y_j^*$, $p(\sum x_i - \sum \omega_i - \sum y_j^*) = 0$. 

The last condition implies that excess supply of goods is allowed only if they are free. 