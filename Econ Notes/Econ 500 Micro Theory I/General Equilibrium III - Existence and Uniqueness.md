---
aliases:
creation date: 2022-11-26 15:35
date updated: 2022-11-26 15:35

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
-  describing the WE as the solution of a system of equations;
-  establishing properties of equilibria based on this description, and;
-  using [[Fixed Point Theorems - Brouwer and Kakutani|fixed point results]] to establish the existence of equilibria. 

### Excess Demand 

First suppose the simple case of a pure exchange economy: $J = 1$, $y_1 = -\R_+^L$ (there is only one firm and all it does is free disposal).

Restrict the consumption sets $X_i$ to $\R^L_+$ and assume preferences are continuous, [[Micro Theory IIIa - Concave, Convex, Quasi|convex (econ)]], and locally nonsatiated. Assume that $\sum_i \omega_i >>0$; that is, there's some of every good. 

Then we can rewrite the WE conditions as: 
1) $y_1^* \leq 0$, $p y_i^* = 0$, and $p \geq 0$. 
2) $x_i^* = x_i(p, p\omega_i)$ for all $i$ (restating equilibrium consumption as Marshallian demands)