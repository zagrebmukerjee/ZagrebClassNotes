---
aliases:
creation date: 2022-05-23 12:10
date updated: Monday, May 23rd 2022, 8:33 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 9. Independence, Basis, Dimension]]

## Callback
Look at $Ax = 0$, where  $A$ is $m \times n$ and $m < n$. More unknowns than equations. So there must be nonzero members of the null space, since there are only $n$ pivots at most - there will be free variables. 

## Independence
Vectors $x_1, \ldots, x_n$ are (linearly) <font color=gree>independent</font> if no combination of them gives the zero vector (save for all coefficients = 0). 

Note: $0$ and $x$ are always dependent
$2$ vectors in $\R^2$ are independent iff they are not parallel

A set of three independent vectors in $\R^2$ - it follows that one of them is dependent on the others. If the three vectors were columns of a matrix, then the matrix must be less-than-full-rank. So there exists a null space (linear dependence -> some combination of the columns makes zero - that combination is an $x$ in the null space)

Linear independence of the columns <-> full column rank 

## Spanning a Space
The columns of $A$ <font color=gree>span</font> $C(A)$ 

More generally, $v_1, \ldots, v_n$ <font color=gree>span</font> space $S$ if 

$$S = \{ c_1 v_1 + \ldots + c_n v_n\}\quad \forall c \in \R^n $$

In other words the span is the smallest set that contains all possible linear combinations of these vectors. 


## Basis

The <font color=gree>basis</font> for a vector space $S$ is $v_1, \ldots, v_n$ if $v_i \indep v_j \; \forall i,j$ and the span of $v_1, \ldots v_n$ is $S$. 

Example: $3 \times 3$ identity matrix -> columns span $\R^3$. The null space has only zero in it. 

Another basis: 

$$ \begin{bmatrix} 1 \\ 1 \\ 2\end{bmatrix}, \begin{bmatrix} 2 \\2 \\5\end{bmatrix}, \begin{bmatrix}3 \\3 \\ 8\end{bmatrix}$$


```ad-info
title: Gram-Schmidt Aside
collapse:true

Aside - using Gram-Schmidt process from [[🚧Strang 17. Gram-Schmidt and A = QR|later]] to create orthonormal basis from any basis $y_1, \ldots, y_n$

Create a projection operator: the projection of $v$ onto the line spanned by $u$. 
$$\text{proj}_u (v) = \frac{\langle u, v \rangle}{\langle u, u \rangle} u$$ 
Elements of the basis: $e_1 = \frac{y_1}{||y_1||}$. Very nice. Then 

$$e_2 = \frac{y_2 - \text{proj}_{e_1}y_2}{||y_2 - \text{proj}_{e_1}y_2||}$$
$$e_3 = \frac{y_3 - \text{proj}_{e_1}y_3 - \text{proj}_{e_2}y_3}{||y_3 - \text{proj}_{e_1}y_3 - \text{proj}_{e_2}y_3||}$$
```

Test: make the $n$ vectors the columns of an ($n \times n$) matrix. If that matrix is invertible and/or has full column rank, they are a basis of $\R^n$

Note: elementary row operations don't change the span.

Bases are not unique. But all bases have the same number of vectors. That number is the <font color=gree>dimension</font>.

```ad-example
title:Example 

Space is $C(A)$ where
$$A = \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1& 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \\\end{bmatrix}$$
Find the dimension of the space; find a basis. 

Evident that cols 3 and 4 are in the span of cols 1 and 2
so dimension is 2. and cols 1 and 2 are a basis

What is that space: it's all linear combinations of cols $1$ and $2$

$$x_1\begin{bmatrix} 1 \\1\\ 1 \end{bmatrix} + x_2\begin{bmatrix} 2\\1\\2\end{bmatrix} = \begin{bmatrix} b_1 \\ b_2 \\ b_3\end{bmatrix}$$
$$\begin{align}
x_1 + 2x_2 &= b_1 \\ 
x_1 + x_2 &= b_2 \\
x_1 + 2x_2 &= b_3 \\
\end{align}$$
This is the plane $x = z$. 
```

From the above it follows that: 

$$\dim C(A) = \text{column rank}(A)$$
$$\dim N(A) = n - \text{column rank}(A)$$
the null space being the span of the special solutions. 
