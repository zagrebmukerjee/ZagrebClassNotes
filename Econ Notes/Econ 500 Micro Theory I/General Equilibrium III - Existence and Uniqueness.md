---
aliases:
creation date: Saturday, November 26th 2022, 3:32 pm
date updated: Saturday, November 26th 2022, 4:29 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium III - Existence and Uniqueness]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

We want to be able to understand the conditions under which a Walrasian Equilibrium exists and is unique. 

## Existence

### Setup

First, recall the definition: 

![[General Equilibrium II - Formal Presentation and Welfare Theorems#Walrasian Equilibrium]]

The overall approach will be:
- describing the WE as the solution of a system of equations;
- establishing properties of equilibria based on this description, and;
- using [[Fixed Point Theorems - Brouwer and Kakutani|fixed point results]] to establish the existence of equilibria. 

### Excess Demand

First suppose the simple case of a pure exchange economy: $J = 1$, $y_1 = -\R_+^L$ (there is only one firm and all it does is free disposal).

Restrict the consumption sets $X_i$ to $\R^L_+$ and assume preferences are continuous, [[Micro Theory IIIa - Concave, Convex, Quasi|convex (econ)]], and locally nonsatiated. Assume that $\sum_i \omega_i >>0$; that is, there's some of every good. 

Then we can rewrite the WE conditions as: 
1) $y_1^* \leq 0$, $p y_i^* = 0$, and $p \geq 0$. 
	1) The first follows from the free disposal firm; the third, from market clearance (which rules out infinite disposal of something); and the second from maximization conditional on $p \geq 0$. 
2) $x_i^* = x_i(p, p\omega_i)$ for all $i$ (restating equilibrium consumption as [[Micro Theory II - Utility Maximization|Marshallian demand]])
3) $\sum_i x_i^* - \sum_i \omega_i = y_1^*$

This lets us establish a new condition for WE:

In a pure exchange economy, $p \geq 0$ is a WE price vector if and only if: 

$$ \sum_i (x_i(p, p\omega_i) - \omega_i) \leq 0$$

Intuitively, this means that no more can be consumed than is endowed. It follows from the WE conditions. In the other direction: suppose the statement is true, and let $y_1^*$ be $\sum_i (x_i(p, p\omega_i) - \omega_i)$, and $x_i^* = x(p, p\omega_i)$, Then condition 2) is met by definition, as is condition 3. Condition 1 follows from the assumptions. 

Note:
$$\begin{align}
py_1^* &= p\left[ \sum_i (x_i(p, p\omega_i) - \omega_i)\right]\\
&=\sum_i \left[px_i(p, p\omega_i) - p\omega_i\right]\\
&= 0
\end{align}$$
which follows from LNS/Walras' Law. 


We can call $x_i(p, p\omega_i) - \omega_i$ the <font color=gree>excess demand</font> of consumer $i$, written $z_i(p)$; the aggregate excess demand is an $l-$ vector, $z(p)$.

Now we can state the above condition more simply: $p \geq 0$ is a WE price vector if and only if $z(p) \leq 0$. 

### Properties of Excess Demand

Now, suppose preferences are strongly monotone.  Then: 
1) $z(p)$ is continuous. 
2) $z(p)$ is homogeneous of deg 0. 
3) $pz(p) = 0$ for any $p$ (Walras' Law)
4) For any $p$, there is an $s > 0$ such that $z_\l(p) > -s$ for all $\l$ 
	1) Since demand
5) 