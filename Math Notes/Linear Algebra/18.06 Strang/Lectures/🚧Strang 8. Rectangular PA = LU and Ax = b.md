---
aliases:
creation date: 2022-05-16 22:28
date updated: Monday, May 16th 2022, 10:43 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
- '#status/🚧'
---

# [[🚧Strang 8. Rectangular PA = LU and Ax = b]]
[[18.06 Strang]]

Solve $Ax = b$!

Here is a system of equations:

$$\begin{aligned}
x_1 + 2 x_2 + 2x_3 +2 x_4 &= b_1\\
2x_1 + 4x_2 + 6x_3 + 8x_4 &= b_2\\
3x_1 + 6x_2 + 8x_3 + 10x_4 &= b_3\\
\end{aligned}$$
It's clear that eqn 1 + eqn 2 = eqn 3. So the same must be true of the RHS. For most $b_1, b_2$ there is only a solution if $b_1 + b_2 = b_3$. 

Elimination discovers this. Create an 
<font color=gree>augmented matrix</font>

$$
\begin{bmatrix} 
1 & 2 & 2 & 2 &|& b_1 \\
2 & 4 & 6 & 8 &|& b_2 \\
3 & 6 & 8 & 10&|& b_3 \\
\end{bmatrix}
$$
$$
\begin{bmatrix} 
1 & 2 & 2 & 2 &|& b_1 \\
0 & 0 & 2 & 4 &|& b_2 - 2b_1 \\
0 & 0 & 2 & 4&|& b_3 -3b_1\\
\end{bmatrix}
$$
$$
\begin{bmatrix} 
\cellcolor{#9999}1 & 2 & 2 & 2 &|& b_1 \\
0 & 0 & \cellcolor{#9999}2 & 4 &|& b_2 - 2b_1 \\
0 & 0 & 0 & 0&|& b_3 -b_2 - b_1\\
\end{bmatrix}
$$
The latter tells us that $0 = b_3 - b_2 - b_1$. This is a condition for solving $Ax = b$.

$Ax =b$ is solvable when $b$ is in the column space of $A$. if a combination of columns of $A$ creates zero rows, then some combination of $b$s must be zero. <font color=#F7B801>why?? to be discussed</font>


### Particular Solution
To find the complete solution to $Ax = b$, first find a particular solution that works. E.g. set all free variables to zero. In this case, $x_2 = x_4 = 0$. Then we have (from the echelon form): 

$$
\begin{aligned}
x_1 +  2x_3 &= b_1\\
2x_3 &= b_2 - 2b_1\\
\end{aligned}
$$

So it follows that $x_3 = b_2/2 - b_1$ and $x_1 = 3b_1 - b_2$. 

Suppose $b_1 = 1$ and $b_2= 5$. Then we can create an $x_\text{particular}$: $\begin{bmatrix} -2 & 0 & 3/2 & 0\end{bmatrix}'$

### Complete Solution
So what other $x$ works? Well, we can add any $x_n$ from the null space $Ax_n = 0$:

$$A[x_p + x_n] = Ax_p + Ax_n = Ax_p$$
So then we can create the space $x_\text{complete}:$

$$x_\text{complete} = \begin{bmatrix} -2 \\ 0 \\3/2 \\0 \end{bmatrix} + c_1 \begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_2 \begin{bmatrix} 2 \\0 \\-2\\1\end{bmatrix}
$$
where the last two are the special solutions. 

```ad-warning
title:
Note: there is no constant on the first term! 
```

This is not a subspace! can't have the origin in it (see, no coefficient on first column). It's the null space, shifted by the solution $x_\text{particular}$. 

So, to solve $Ax = b$:
- find a particular solution: get $U$, set free variables to $0$, back substitute. 
- Find the null space
- combine them. 