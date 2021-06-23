---
date updated: 2021-06-11 13:21

notetype: "Math Class Note"
cssclass: math-class-note

tags:
  - '#classNotes'
---

#### [[Video 9 Dot Product and Duality]]
Part of [[@Review of Linear Algebra Index]]

##### Geometric interpretation of Dot Product

The dot product of $\mathbf{w}$ and $\mathbf{v}$ has a geometric interpretation, but it gets a little complicated. 

Project $\mathbf{w}$ onto the line that is parallel to $\mathbf{v}$ (i.e., find the component of $\mathbf{w}$ that is parallel to $\mathbf{v}$). The length of projection times the length of $\mathbf{v}$ is the dot product. 

Implication - _ceteris paribus_ the smaller the angle between $\mathbf{w}$ and $\mathbf{v}$, the greater the dot product. If they are perpendicular, dot  product is zero. If antiparallel, negative. 

##### Commutativity of Dot Product

So why is it commutative? 

Case 1: the length of $\mathbf{w}$ and $\mathbf{v}$ are the same. Then we can see it easily by symmetry. 

Then for any $c\mathbf{v}$ we can split it into symmetric case and a scalar of the whole dot product, and so on. 


##### Dot Product as Projection on Line; Duality

A linear transformation from $\mathbb{R}^2$ to $\mathbb{R}^1$ - i.e. from $xy$ plane to the number line - can be a 2x1 matrix (see [[Video 7 Inverse, Null Space, Column Space, Rank#Video 8 Nonsquare matrices|Video 8]]). This linear transformation has the property that a line of dots evenly spaced  in $\mathbb{R}^2$ will still be evenly spaced on $\mathbb{R}^1$.

Here $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$ land on numbers on the line.  Example where $\mathbf{\hat{i}}$ goes to $1$ and $\mathbf{\hat{j}}$ goes to $-2$. 

$$ L = \begin{bmatrix}1 & -2\end{bmatrix} \qquad \mathbf{v} = \begin{bmatrix}4 \\ 3\end{bmatrix}  \qquad L(\mathbf{v}) =  1(4) - 2(3) = -2$$

This is basically a dot product - 2D vectors are transposed 1x2 matrices. In other words, each 2D vector encodes a transformation from $\mathbb{R}^2$ to $\mathbb{R}^1$. This is called _duality_: vectors are dual to transformations onto the line. 

Why is this the same?

The dot product of $\mathbf{w}$ and $\mathbf{v}$ is basically using $\mathbf{v}$ as a linear transformation to map $\mathbf{w}$ onto the '$\mathbf{v}$-line' and vice versa. 

This projection is the same as the 2D transormation based on the unit length basis that is parallel to $\mathbf{v}$.

