---
aliases:
creation date: Friday, September 23rd 2022, 10:21 am
date updated: Friday, September 23rd 2022, 10:22 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Micro Theory IV - Comparative Statics]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Comparative statics are representations of how endogeneous variables respond to exogeneous ones. For instance, I might be interested in $\frac{dh_i}{dp_i}$, the substitution effect. I happen to know the sign of this, since the expenditure function is concave. But other comparative statics are harder to sign: for instance, I don't know $dh_i/dp_j$ or $dx_i/dp_j$. I need some techniques for signing comparative statics. 

In general I have three approaches:
1) Make an explicit functional form. Then we can solve for $x_i$, $h_i$ etc and differentiate. This is nice when feasible. But sometimes we may have a functional form that can't be solved, or we may not want to pick one at all. 
2) The implicit function theorem
3) Techniques of "Monotone Comparative Statics"

## Implicit Function Theorem Comparative Statics

We're maximizing $u(x_1, x_2)$ subject to $w = p_1 x_1 + p_2 x_2$. 

We have some FOCs: 

$$\begin{align}
u_1(x_1(p,w), x_2(p,w)) + \lambda (p,w)p_1 &= 0 \\
u_2(x_1(p,w), x_2(p,w)) + \lambda (p,w)p_2 &= 0 \\
p_1x_1(p,w) + p_2 x_2(p,w) - w &= 0
\end{align}$$
Note that I've already maximized this, i.e. $x_1

