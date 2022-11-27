---
aliases:
creation date: Saturday, November 26th 2022, 3:32 pm
date updated: Saturday, November 26th 2022, 5:03 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium II - Existence]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Motivation and Setup

We want to be able to understand the conditions under which a Walrasian Equilibrium exists. Why? Well, if these conditions are totally crazy, it may tell us that we  don't have that good of an equilibrium concept. 

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

Now, suppose preferences are strongly monotone. Then: 
1) $z(p)$ is continuous. 
2) $z(p)$ is homogeneous of deg 0. 
3) $pz(p) = 0$ for any $p$ (Walras' Law)
4) For any $p$, there is an $s > 0$ such that $z_\l(p) > -s$ for all $\l$ 
	1) Since demand is nonnegative, net supply can be no greater than endowment
5) Suppose $p_n \to p$, $p \neq 0$, but for some $\l$ $p_\l = 0$. Then $\max _{\l \in L} z_\_l(p_n) \to \infty$
	1) there's some consumer with positive weatlh. Strong monotonicity means that as $p_\l$ to $0$, $z_l(p)$ for that guy goes to infinity.


```ad-note
title:
Walras' law gives us another equation in this system: that means, if all but one price satisfies our excess demand criterion, the last must also (i.e. we only have to check that all markets but one clear). 

```

This can be extended to a general production case with 'production inclusive excess demand' functions. #status/section/🚧 

## Existence 

The overall approach is to set up for using [[Fixed Point Theorems - Brouwer and Kakutani|Kakutani's Fixed Point Theorem]]. This means
1) Create a correspondence from prices into itself that - loosely - moves towards W. equilibrium
2) Demonstrate that a fixed point of this correspondence is an equilibrium
3) Show that this correspondence meets the Kakutani conditions: convex-valued and [[Micro Theory IIIb - Hemicontinuity|upper hemicontinuous]]. 
4) Use KFPT to demonstrate equilibrium. 

### Conditions

Need:
- $z(p)$ defined on all $p \in \R_+^L$
- meeting conditions above (cont, homogeneous, Walras' Law, bounded below, unbounded with $p \to 0$)
ie. $\sum_i \omega_i >> 0$, and preferences are continuous, SCX, strongly monotone.

Then for some $p$, $z(p) = 0$, meaning a WE exists.

### Setup

First create a price simplex $\Delta$ denoting all relative levels of prices. For convenience we can make this the unit simplex: 

$$ \Delta = \bigg\{ p \in \R^L_+: \sum_\l p = 1 \bigg\}$$

So in $\R^2$ this is a line segment with ends $(0,1)$ and $(1,0)$. 

We'll want to separately consider the interior of the simplex 