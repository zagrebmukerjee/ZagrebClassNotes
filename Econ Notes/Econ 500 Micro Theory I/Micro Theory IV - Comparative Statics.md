---
aliases:
creation date: Friday, September 23rd 2022, 10:21 am
date updated: Saturday, September 24th 2022, 1:30 pm

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
} = (1/|H|)\left[ \lambda p_1p_2 - x_1 (p_2u_{11} \right]
$$
