---
date updated: 2021-06-10 19:20

notetype: "Math Class Note"
cssclass: math-class-note

tags:
- '#classes/math/linalg'
---

#### [[Video 7 Inverse, Null Space, Column Space, Rank]]

- [[#Linear Systems of Equations|Linear Systems of Equations]]
- [[#Singular Matrices|Singular Matrices]]
- [[#Matrix Inverses|Matrix Inverses]]
- [[#Rank, Column Space, Null Space|Rank, Column Space, Null Space]]
- [[#Video 8: Nonsquare matrices|Video 8: Nonsquare matrices]]



##### Linear Systems of Equations

A _linear system of equations_ is $n$ equations in $n$ variables, that are linear in each variable. These can be represented as matrix products. 

$$\begin{array}{lccccl} 
2x &+& 5y &+& 3z& = -3 \\   
4x &+& 0y &+& 8z& = 0 \\   
1x &+& 3y &+& 0z& = 2 \\   
\end{array}$$

$$ 
\begin{bmatrix} 
2 & 5 & 3 \\
4 & 0 & 8 \\
1 & 3 & 0 \\
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z\end{bmatrix} 
= 
\begin{bmatrix}-3 \\ 0 \\ 2 \end{bmatrix}
$$

By representing this as a matrix, we can see that it's also a linear transformation question. What vector $(x,y,z)$, under the transformation above, becomes $(-3, 0, 2)$? In the general form, 

$$A(\mathbf{x}) = \mathbf{v}$$

##### Singular Matrices 

If $A$ squishes space into a line (or a plane in 3D, and so on), then there is no way to solve this problem - because more than one  vector $\mathbf{x}$ is mapped to $\mathbf{v}$. 

We can figure this out using the determinant from [[Video 6 Determinant|Video 6]]. If the determinant is 0, then there is no solution. 

Intuitively, that means that the system above effectively has 2 variables, not 3, and thus is not soluble. 

This sort of matrix is called _singular_ - or _noninvertible_, for reasons shortly to be discovered.

##### Matrix Inverses

The concept of a _matrix inverse_ lets us solve the problem of $A(\mathbf{x}) = \mathbf{v}$. Let the inverse of $A$, $A^{-1}$, be the matrix such that 
$$ A^{-1}(A(\mathbf{v})) = \mathbf{v}$$ 

As an example, consider the following $A$ and $A^{-1}$, where $A$ is a 90$^\circ$ rotation counterclockwise, and $A^{-1}$ is a 90$^\circ$ rotation clockwise:

$$A = \begin{bmatrix} 0 & -1 \\ 1 & 0   \end{bmatrix}
\qquad \qquad A^{-1} = \begin{bmatrix} 0 & 1 \\ -1 & 0   \end{bmatrix} $$

Generally,
$$ A^{-1}A = I$$ 
where $I$ is the identity matrix. The identity matrix maps space to itself: it is the matrix such that $I_{i,j} = 1$ if $i=j$ and $0$ otherwise (in other words, a matrix with $1$ on the diagonal and $0$ everywhere else).

So - to return to the system of equations - 

$$A\mathbf{x} = \mathbf{v} \qquad \qquad A^{-1}A\mathbf{x} = A^{-1}\mathbf{v} \qquad \qquad \mathbf{x} = A^{-1}\mathbf{v}  $$

Same applies for higher dimensions. 

$A^{-1}$ exists if and only if det$(A) \neq 0$ - this means $A$ is _invertible_ or _nonsingular_.

A formula for the 2D inverse: 

$$ A = \begin{bmatrix} a & b \\ c & d   \end{bmatrix} \qquad \qquad A^{-1} = \frac{1}{\text{det}(A)} \begin{bmatrix} d & -b \\ -c & a   \end{bmatrix} $$

For a general way to find inverses or solve systems of equations, see [[Digression - Gauss-Jordan Elimination and Computing Inverses]]

##### Rank, Column Space, Null Space

There are sub-cases of linear dependence of columns, or det$(A) = 0$; in 3D, this might mean that $A$ maps $\mathbb{R}^3$ to $\mathbb{R}^2$, $\mathbb{R}^1$, or $\mathbb{R}^0$. 

The set $\{\forall \mathbf{v}: A \mathbf{v}  \}$ is the _column space_ of the matrix, or the span of its columns. The origin is always in the column space.

The dimensionality of the column space is called the _rank_. If $A$ maps to $\mathbb{R}^n$, it has rank $n$. It follows that, if $A$ is $m \times m$, then rank$(A) \leq m$. If rank$(A) = m$ then $A$ has _full rank_. 

The _null space_ of a matrix is all vectors $\mathbf{v}$ such that $A \mathbf{v}$ is the origin.

##### Video 8: Nonsquare matrices

Nonsquare matrices of $m \times n$ transform from $\mathbb{R}^m$ to $\mathbb{R}^n$. 