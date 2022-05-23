---
aliases:
creation date: 2022-05-23 12:10
date updated: 2022-05-23 12:10

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

The <font color=gree>basis</font>
