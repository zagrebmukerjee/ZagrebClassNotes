---
aliases:
creation date: Wednesday, September 28th 2022, 10:10 am
date updated: Monday, October 3rd 2022, 4:10 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Micro Theory VI - Theory of the Firm]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Production

We can represent possible production decisions as a production set, some set in the commodity space. Common example: $y\in \R^L$ with $F(y) \leq 0$ for some $F$. The $F$ contains the information about what is an input and what's an output - we don't yet need to impose that structure. 

When we do we will write $Y = \{ (q, -z): q \leq f(z)\}$ as a neat way of ordering our signs reasonably. 

We will assume some properties:
- $Y$ nonempty. 
- $Y$ closed. 
- $Y \cap \R_+ = \emptyset$. In other words, you can't make a production decision that has positive quantities of all outputs. No free lunch/possibility of inaction.
- $y \in Y$ means that $y' \leq y$ is also in $Y$. This is 'free disposal'. If I can produce $x_2$ with $x_1$ at $(-1,3)$ then I could also buy and throw out $2$ units of $x_1$ with $-3,3$. 
- Convexity

There are some popular properties, but these are optional: 
- Returns to scale decreasing: $y \in y \implies \alpha y \in Y\; \forall \alpha\; \in [0,1]$
- increasing $y \in y \implies \alpha y \in Y\; \forall \alpha\; \geq 1$
- constant $y \in y \implies \alpha y \in Y\; \forall \alpha \geq 0$

note that in this setup, constant returns are a special case of decreasing returns. 


Convexity implies non-increasing returns to scale. Almost by definition. But converse does not hold. To see why, consider production set that's lower contour set of 
$$ F(x) = \begin{cases} \log(-x) & x \leq 0\end{cases}$$
but create a little bump in it. A small enough bump preserves decreasing returns but doesn't keep convexity. 


## The Firm Problem

### Profit and Supply Functions

The firm wants to maximize profits. This maximization gives us two functions: profit $\pi$ and input/output $y$. Define:

$$ \pi(p) = \max_{y \in Y} py $$
$$ y(p) = \arg \max_{y \in Y} py $$
We don't get a maximum for free, like we did with utility maximization and the Weierstrass Extreme Value theorem. The utility 'production set' is the budget set, which is closed and bounded hence compact. In contrast, the production set exhibits free disposal which means it's not bounded below \[if $y_1, y_2, \ldots$ is a possible production relation, so is $y_1 - a_1, \ldots$; recall that $Y$ is $(q,-z)$, which means that 'free disposal' is buying too much of some input and tossing it, or producing less than you could (up to buying instead of selling, I guess\].

Increasing returns are sufficient for no solution. Decreasing returns are insufficient for a solution. 

We can add a bit more structure: 

$$ \pi = \max_{F(y) \leq 0} py$$
This harkens back to the definition of the production set as the lower contour set of some production function (normalized as $f(z)-q$). 
Writing it this way gets us FOC $p_i = \lambda (dF/dy)$; if we go further and say the PMP is $\max_{z \in Y} pf(z) - wz$ that gives us the familiar FOC $p (df/dz_i) = w_i$, each factor is paid its marginal product. 

#### Properties
Suppose $Y$ is no free lunch, free disposal, nonempty and closed: suppose PMP solvable. Then
- $\pi$ is homogeneous of degree $1$ in $p$
	- $\pi(p) = \max_{y \in Y} py$. But this is the same as $\max_{y \in Y} \lambda p y$ for $\lambda > 0$. 
- $\pi$ is convex in $p$
	- Suppose $\pi(p)$, $\pi(p')$; let $p' = \lambda p + (1-\lambda)p'$. Let $y'' = \arg \max_{y \in Y} \pi(p'')$. 
	Then:
	$$
	\begin{align*}
	    \pi(p'') &= p''y'' \\
	    &= \lambda p y'' + (1-\lambda) p' y''\\
	    &\leq \lambda \pi(p) + (1-\lambda)\pi(p')
	\end{align*}
	$$
	The last line follows from homogeneity (part 1) and from the fact that $\pi(p)$ is the max of $py$ for $y \in Y$; so if $y'' \in Y$ then $py'' \leq \pi(p)$
- $y(p)$ is homogeneous of degree $0$ in $p$
	- $y(p)$ is $\arg \max_{y \in Y} py$. Then $y(\lambda p)$ is $\arg \max_{y \in Y} \lambda py$, but for $\lambda > 0$ this is the same as $y$. 
- If $Y$ is [[Micro Theory IIIa - Concave, Convex, Quasi|convex]], $y(p)$ is convex. If $Y$ is strictly convex, $y(p)$ is a singleton.
	- $y(p)$ is $\arg \max_{y \in Y} py$. First suppose $Y$ convex. Then let $y, y'$ be in $y(p)$. Define $y'' = \lambda y + (1-\lambda)y'$. Then $py'' = \lambda p y + (1-\lambda) py'$. But $py = py' = \pi(p)$, and so $py'' = py$, and $y'' \in y(p)$. 
	- Now suppose $Y$ strictly convex. Then as above have $y'' = \lambda y + (1-\lambda)y'$. But by strict convexity there is a ball $B_r$ of radius $r$ around $y''$ such that $B_r \subseteq Y$. In that ball there is some point $\hat y \in Y, \hat y >> y''$; and so $p\hat y >p y''$. But then $p \hat y > \lambda p y + (1-\lambda)py'$ and so $p \hat y > \pi(p)$; a contradiction. 






## Cost Minimization 


## Duality or Integrability 

Suppose I can observe a profit function $\pi$. Then can I say something about the technology - i.e. the relation embodied in $Y$? This might be nice because profit functions and cost functions are much more observable. 