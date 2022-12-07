---
aliases:
creation date: Monday, November 28th 2022, 2:51 pm
date updated: Monday, November 28th 2022, 2:59 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium IIIa - Generalized Existence]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

In [[General Equilibrium III - Existence]] a specific case is discussed with restrictions on the economy <font color=#F7B801>what</font>

This argument gives a more general treatment. 

## Setup

### Quasiequilibrium
Recall Walrasian Equilibrium definition: 
![[General Equilibrium II - Formal Presentation and Welfare Theorems#Walrasian Equilibrium]]

Now introduce a weaker idea: an allocation $x_i^*, y_j^*$ and prices $p \neq 0$ are a Walrasian Quasi-Equilibrium (WQE) if:
1) For all $j$, $y_j \in Y_j \implies py_j^* \geq py_j$ - profit maximization
2) For all $i$, $p x_i^* \leq p \omega_i + \sum_j \theta_{ij} py_j^*$ (the budget constraint), and if $x_i \succ x_i^*$ then $px_i \geq p\omega_i + \sum_j \theta_{ij} py^*_j$. 
	1) Exactly like the previous quasiequilibrium concept. There's no strictly preferred bundle that is cheaper (though they might be the same price).
3) $\sum_i x_i^* = \sum_i \omega_i + \sum_j y_j^*$ - markets clear. 

With LNS, condition 2 tells us that, given $p$, $x^*$ minimizes expenditure over the set $\{ x\in X_i: x \succsim x_i^*\}$: there is nothing cheaper that is better. 




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