---
date updated: 2022-04-09 18:00

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Matrix Calculus]]

There are probably geometric interpretations of matrix calculus, but I'm not going to think about those for the moment.

## Differentiation
#### Product of two vectors
Let's build up from simple cases. Let $x$ be a vector, $[x_1, \ldots, x_p]$; and let $a$ be $[a_1, \ldots, a_p]$. Then consider $x'a$. This will map to a scalar (the dot product of the vectors): $y = x_1 a_1 + \ldots + x_2 a_2$.   

So then what is $\frac{\partial y}{\partial x}?$ By convention, we describe this as 

$$ \frac{\partial y}{\partial x} = \begin{bmatrix} \frac{\partial y}{\partial x_1} \\ \vdots \\ \frac{\partial y}{\partial x_p} \end{bmatrix}$$

Each entry of this vector describes how the scalar $y$ responds to changes in the corresponding entry of $x$. 

So now we know how to differentiate this! If $y = a_1x_1 + \ldots$, then $\frac{\partial y}{\partial x_1}$ is simply $a_1$. 

Here is our first rule: given conformable vectors $a$ and $x$, $\frac{\partial a'x}{\partial x} = \frac{\partial x'a}{ \partial x} = a$. It follows also that $\frac{\partial a'x}{\partial x'} = a'$.


#### Quadratic Form

Let $x$ be a vector, $[x_1, \ldots, x_n]$. Let $A$ be an $n \times n$ symmetric matrix:

$$
A = \begin{bmatrix} a_{11} & a_{21} &\ldots & a_{1n}\\ a_{21} & a_{22} & \ldots & a_{n2}\\
\vdots & & & \vdots \\
a_{n1}& a_{n2}& \ldots & a_{nn}
\end{bmatrix}$$
Then define a scalar-valued $Q$:

$$ 
\begin{aligned}
Q &= x' A x\\
&= [x_1 \ldots x_n ]\begin{bmatrix} a_{11} & a_{21} &\ldots & a_{1n}\\ a_{21} & a_{22} & \ldots & a_{n2}\\
\vdots & & & \vdots \\
a_{n1}& a_{n2}& \ldots & a_{nn}
\end{bmatrix}\begin{bmatrix} x_1 \\ \vdots \\ x_n \end{bmatrix} \\
&=[x_1 \ldots x_n] \begin{bmatrix} a_{11}x_1 + a_{21}x_2 + \ldots + a_{n1}x_n \\
a_{21}x_1 + a_{22}x_2 + \ldots + a_{n2}x_n \\\
\vdots \\
a_{1n}x_1 + a_{1n}x_2 + \ldots + a_{nn} x_n 
\end{bmatrix} \\
&= (a_{11}x_1^2 + a_{21}x_1x_2 + \ldots + a_{n1}x_1x_n) + \\
& \qquad (a_{21}x_1x_2 + a_{22}x_2^2 + \ldots + a_{n2}x_2x_n) + \\
& \qquad  (a_{n1}x_1x_n + a_{n2}x_2x)n + \ldots + a_{nn}x_n^2) \\
&= \sum_i a_{ii}x_i^2 + 2 \sum_{i>j}a_{ij}x_ix_j
\end{aligned}
$$
 
In other words, $A$ supplies the coefficients of a quadratic equation, and $x$ the terms. 

Now, let's think about differentiation:

$$
\begin{aligned}
\frac{\partial Q}{\partial x} &= \begin{bmatrix} \frac{\partial Q}{\partial x_1} \\ \vdots \\ \frac{\partial Q}{\partial x_n}\end{bmatrix}\\
&= \begin{bmatrix}\frac{\partial}{\partial x_1} \left( \sum_i a_{ii}x_i^2 + 2 \sum_{i>j}a_{ij}x_ix_j\right)\\ \vdots \\ 
\frac{\partial}{\partial x_n} \left( \sum_i a_{ii}x_i^2 + 2 \sum_{i>j}a_{ij}x_ix_j\right)\end{bmatrix}\\
&= \begin{bmatrix}
2a_{11}x_1 + 2a_{21}x_2 + \ldots + 2a_{n1}x_n  \\
\vdots \\
2a_{1n}x_1 + 2a_{2n}x_2 + \ldots + 2a_{nn}x_n  \\
\end{bmatrix} \\
&= 2Ax
\end{aligned}
$$


A satisfying result. 

