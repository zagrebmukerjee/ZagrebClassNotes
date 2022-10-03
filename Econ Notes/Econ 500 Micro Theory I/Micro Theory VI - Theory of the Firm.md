---
aliases:
creation date: Wednesday, September 28th 2022, 10:10 am
date updated: Monday, October 3rd 2022, 3:41 pm

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

The firm wants to maximize profits. This maximization gives us two functions: profit $\pi$ and input/output $y$. Define:

$$ \pi(p) = \max_{y \in Y} py $$
$$ y(p) = \arg \max_{y \in Y} py $$
We don't get a maximum for free, like we did with utility maximization and the Weierstrass Extreme Value theorem. The utility 'production set' is the budget set, which is closed and bounded hence compact. In contrast, the production set exhibits free disposal which means it's not bounded below \[if $y_1, y_2, \ldots$ is a possible production relation, so is $y_1 - a_1, \ldots$; recall that $Y$ is $(q,-z)$, which means that 'free disposal' is buying too much of some input and tossing it, or producing less than you could (up to buying instead of selling, I guess\].

Increasing returns are sufficient for no solution. Decreasing returns are insufficient for a solution. 

We can add a bit more structure: 

$$ \pi = \max_{F(y) \leq 0} py$$
This harkens back to the definition of the production set as the lower contour set of some production function (normalized as $f(z)-q$). 
Writing it this way gets us FOC $p_i = \lambda (dF/dy)$; if we go further and say the PMP is $\max_{z \in Y} pf(z) - wz$ that gives us the familiar FOC $p (df/dz_i) = w_i$, each factor is paid its marginal product. 






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






### Solving the Problem
$$\max_{y \in \R: F(y \leq 0} py$$
OK so just do your FOC thing to get $p_\l = \lambda \frac{dF}{d\l}$. or if you write it $pf(z) - wz$ then $pf'_\l(z) = w_\l$. Each factor gets paid their marginal product. 


Assume that $Y$ is as above: nonempty, closed, no free lunch, free disposal; assume PMP solvable. 

Then what's up with $\pi(p)$ and $y(p)$?
- $\pi$ is homogeneous of degree $1$. Think of it as expenditure function: changing prices doesn't change relative prices and so isoprofit lines have the same slope. So tangency doesn't change (only the height and steepness of the surface)
- $\pi$ is convex $p y(p)$. If all prices change then HD1; but if a single price changes then you will substitute away from that good
- $y(p)$ is homogeneous of degree $0$ in $p$.
	- Convex production set means convex supply correspondence. But not unique $y$ - imagine again our flat spots in production set frontier.  
	- Strictly convex production set is $y(p)$ singleton. 

<font color=#F7B801>we start here with rpoduction set. why didn't we start with consumption set and expenditure minimization. Or start here with cost minimization</font>

## Cost Minimization and Duality

Suppose you have some $\pi(p)$. Then you can create: $\hat Y = \{y \in \R^L : py \leq \pi(p) \forall p >> 0 \}$ - ie every price is positive. What can we say about $\hat Y$? ie. can I recover the technology from the profit function this way? But I haven't incorporated the technology...

Like integrability: we asked if we can get preferences out of expenditure function. Expenditure function is challenging b/c e(p,u) has a u.... we don't have that here. <font color=#F7B801>but isn't that just cheatiing</font>

At the least we can see that $Y \subseteq \hat Y$: if $y' \in Y$ and $py' \geq \pi(y)$ then $\pi(y') \geq py' \geq \pi(y)$ and this contradicts the profit fn definition. 
