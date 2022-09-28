---
aliases:
creation date: Wednesday, September 28th 2022, 10:10 am
date updated: Wednesday, September 28th 2022, 10:29 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Micro Theory VI - Theory of the Firm]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>



## Live Notes

Production set common type: 
$y \in \R^L: F(y) \leq 0$

Inputs? outputs? Well - that's all in F. but no need to impose unnecessary structure on the production set?

Production set properties: 
- nonempty
- closed
- $y \cap R_+ = {0}$ = no free lunch, possiblity of ination
- $y \in Y, y' \leq y \implies y' \in Y$ (free disposal)

we also have convexity of the production set. 


popular, optional properties
- Returns to scale decreasing: $y \in y \implies \alpha y \in Y\; \forall \alpha\; \in [0,1]$
	- increasing $y \in y \implies \alpha y \in Y\; \forall \alpha\; \geq 1$
	- constant $y \in y \implies \alpha y \in Y\; \forall \alpha \geq 0$

These are also convex combinations? 

Convexity implies non-increasing returns to scale. Almost by definition. But converse does not hold. To see why, consider production set that's lower contour set of 
$$ F(x) = \begin{cases} \log(-x) & x \leq 0\end{cases}$$
but create a little bump in it. a small enough bump preserves decreasing returns but doesn't keep convexity. 


## Profit Maximization

### Intro

Profit maximization: $\max_{y \in Y} py$. Let $\pi(p) = \max_{y \in Y} py$ - the maximized profit. Called the profit function. $y(p)$ is a supply curve, $\arg \max_{y \in Y} py$. 

Frequently you will know about outputs and inputs, so can write $p_q q - D_z z$ with $q \subseteq \delta(z)$. Rev - costs


- Function is continuous. But not on a compact set. So question is open. We can't just have the Weierstrass theorem
- Increasing returns: no maximum.
- Decreasing returns? Not necess maximum. 
	- Constant returns is a special case of decreasing returns. So .... no. 
	- What about strictly decreasing returns? Once more go back to $\log -x$. 


We will look at the problems where the maximum exists. But this is a more demanding requirement than it was for utility maximization, which really only required continuity <font color=#F7B801>is that true</font>



### Solving the problem
$$\max_{y \in \R: F(y \leq 0} py$$
OK so just do your FOC thing to get $p_\l = \lambda \frac{dF}{d\l}$. or if you write it $pf(z) - wz$ then $pf'_\l(z) = w_\l$. Each factor gets paid their marginal product. 


Assume that $Y$ is as above: nonempty, closed, no free lunch, free disposal; assume PMP solvable. 

Then what's up with $\pi(p)$ and $y(p)$?
- $\pi$ is homogeneous of degree $1$. Think of it as expenditure function: changing prices doesn't change relative prices and so isoprofit lines have the same slope. So tangency doesn't change (only the height and steepness of the surface)
- $\pi$ is convex
- $y(p)$ is homogeneous of degree $0$ in $p$.
	- Convex production set means convex supply function. Strictly convex production set is $y(p)$ singleton. 