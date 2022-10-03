---
aliases:
creation date: Friday, September 23rd 2022, 10:21 am
date updated: Monday, October 3rd 2022, 3:23 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
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
Note that I've already maximized this, i.e. $x_1, x_2, \lambda$ are such that the FOCs hold. That makes these identities. So I can differentiate them all with respect to $p_1$ (say). 

$$\begin{align}
 - \lambda &= u_{11}\frac{dx_1}{dp_1} + u_{12}\frac{dx_2}{dp_1} + p_1 \frac{d\lambda}{dp_1} \\
0 &= u_{21}\frac{dx_1}{dp_1} + u_{22}\frac{dx_2}{dp_1} + p_2\frac{d\lambda}{dp_1} \\
-x_1 &= p_1\frac{dx_1}{dp_1} + p_2\frac{dx_2}{dp_1} \\
\end{align}$$
We can write this in matrix form: 
$$
\begin{bmatrix} 
u_{11} & u_{12} & p_1 \\ 
u_{21} & u_{22} & p_2 \\ 
p_1 & p_2 & 0 \\
\end{bmatrix}
\begin{bmatrix} dx_1/dp_1\\dx_2/dp_1\\ d\lambda/dp_1\end{bmatrix} = \begin{bmatrix} 
-\lambda \\ 0 \\ -x_1
\end{bmatrix}
$$

This allows for a Cramer's Rule setup - i.e., for the $i\th$ variable, take a ratio of determinants: the det. of the coefficient matrix with the $i\th$ column replaced by the constants divided by the determinant of the coefficients matrix. 
$$
\frac{dx_1}{dp_1} = \frac{
	\left| \begin{matrix}-\lambda & u_{12} & p_1 \\ 0 & u_{22} & p_2 \\ -x_1 & p_2 & 0 \end{matrix}\right|
}{
	\left| \begin{matrix} u_{11} & u_{12} & p_1 \\ 
u_{21} & u_{22} & p_2 \\ 
p_1 & p_2 & 0 \\\end{matrix}\right|
}
$$
The bottom matrix is sometimes called the Bordered Hessian. We can say it is $\geq 0$ from the first-order conditions. 
The top has determinant $\lambda p_2^2 - x_1(p_2u_{12} - p_1u_{22})$. 

This first term $\lambda p_2^2$ is negative: we defined $\lambda \leq 0$, and the square is positive. 

We can then talk about our derivatives purely in terms of the signs of the second derivatives of $u$. 

The cross derivatives: 

$$
\frac{dx_2}{dp_1} = \frac{
	\left| \begin{matrix}u_{11} & -\lambda & p_1 \\ 
u_{21} & 0 & p_2 \\ 
p_1 & -x_1 & 0 \\\end{matrix}\right|
}{
	\left| \begin{matrix} u_{11} & u_{12} & p_1 \\ 
u_{21} & u_{22} & p_2 \\ 
p_1 & p_2 & 0 \\\end{matrix}\right|
} = (1/|H|)\left[ \lambda p_1p_2 - x_1 (p_1u_{12} -p_2u_{11})\right]
$$

$$
\frac{dx_1}{dp_2} = \frac{
	\left| \begin{matrix}0 & u_{12} & p_1 \\ 
-\lambda & u_{22} & p_2 \\ 
-x_2 & p_2 & 0\\\end{matrix}\right|
}{
	\left| \begin{matrix} u_{11} & u_{12} & p_1 \\ 
u_{21} & u_{22} & p_2 \\ 
p_1 & p_2 & 0 \\\end{matrix}\right|
} = (1/|H|)\left[ \lambda p_1p_2 - x_2 (p_1u_{22} -p_2u_{12})\right]
$$
Then we have this symmetric term $\lambda p_1p_2$ which is negative. 

### Implicit Function Theorem

For this purpose we can think of the [[Implicit Function Theorem]] as: 
- a bunch of equations $f_1, \ldots f_n = 0$, with arguments $(x,t)$ 
	- here $x$ is endogeenous variables and $t$ is exogeneous. 
	- One equation for each $x$ (endogeneous variable). 
	- Suppose you can define $x(t)$ st. $f_1(x(t),t) = 0$; then I can start differentiating. 

But how do I know that's allowed?

The IFT tells me when I can do that: specifically, if $|H|$ is nonzero, then there is some $x(t)$ that makes this work in the neighborhood of $t$. 

There are a number of conditions required for the IFT, but it's still very handy, and frequently used. Works well when all exogeneous variables are in the constraint. 



## Monotone Comparative Statics

MCS is a more generalized method with a different set of conditions. Notably, it requires no differentiability. 

Let $f(X \times T) \to \R$. Once more, we can think of $X$ as endogeneous variables and $T$ as exogeneous; we are ultimately interested in how the $X$ change when $T$ changes. 


### Increasing Differences

Choose $x' > x$ and $t' > t$. Then $f$ exhibits <font color=gree>increasing differences</font> if: 

$$\begin{align}
f(x', t') - f(x, t') \geq f(x', t) - f(x, t)\\
f(x', t') - f(x', t) \geq f(x, t') - f(x,t)\\
\end{align}$$
This is simply a discrete version of a criterion that $d^2f/dxdt \geq 0$: when $t$ is higher, an increase in $x$ has a greater effect on $f$. <font color=gree>Strictly increasing differences</font> means that the above inequalities are strict. 


Then we have a useful result:

#### Theorem

Let $f$ exhibit strictly increasing differences; let $t' > t$, $x' \in \arg \max f(\cdot, t')$ and $x \in \arg \max f(\cdot, t)$. Then $x' \geq x$. 

In other words: if $x'$ maximizes under $t'$ and $x$ maximizes under $t$, then $t' > t \implies x' \geq x$. 
We can't quite get to $x'>x$; for instance, suppose $x \in \{0,1\}$ (e.g. loan approval decision). 

This is a very easy method! It involves no calculations and no structure. Why is it so powerful? The increasing differences criterion has more information in it than the $IFT$, which only used $|H| \geq 0$. 

It's simple to have a multidimensional $t$; just do this for every $t$. For multi dimensional $X$ it's more complex. Let $X$ be the Cartesian product of $X_i$, and $T$ of $T_j$, with $X_i$ and $T_j$ in $\R$. Then, if $f$ has SID in each pair $x_i, t_j$, and ID in each $x_i, x_j$ $t' > t \implies x(t') \geq x(t)$. 


### Single Crossing

We may prefer an ordinal property, i.e. one that doesn't care about specific values of $f$. For instance, when we work with utility functions, all that matters is the order. Then we have the <font color=gree>single crossing</font> criterion: For $x' > x$, $t' > t$, 
$$[f(x', t) \geq f(x, t)] \implies [f(x', t') \geq f(x, t')]$$

Intuitively, this means 'signs are preserved': the difference of $x$ moves iwth the difference of $t$. Same generalization as above. 


### Supermodularity

A further generalization of our results: suppose $X$ is a lattice (ie. each pair has a $\sup$ and $\inf$), $T$ a partially ordered set. Let $P$ be the ordering (eg $xPy$ meaning $x$ comes before $y$).  
Define $x \land y$ as the least upper bound of $(x,y)$; define $x \lor y$ as the greatest lower bound, meaning:
- $(x \land y)Px$, $(x\land y)Py$, and $zPx$, $zPy$ means $zP(x\land y)$. 


Then, $f$ is supermodular in $x$ if: 

$$ f(x \lor y ) + f(x \land y) \geq f(x) + f(y) $$
Quasi supermodularity is an ordinal condition: 
$$ f(x) \geq f(x \land y) \implies f(x \lor y) \geq f(y)$$


If $X$ and $T$ are $\R^j, \R^k$, and $f$ is twice-differentiable, then we can say $x \land y$ is the elementwise maximum, and this maps to $f_{xy} \geq 0$ for all $x,y$. So we can see we have an even stronger condition. 
