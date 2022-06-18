---
aliases:
creation date: 2022-05-16 22:28
date updated: Monday, May 16th 2022, 10:43 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 8. Rectangular PA = LU and Ax = b]]
[[18.06  Linear Algebra Strang]]

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

This is not a subspace! Because of that first column, can't have the origin in it. In fact, it's the null space, shifted by the solution $x_\text{particular}$. 

So, to solve $Ax = b$:
- find a particular solution: get $U$, set free variables to $0$, back substitute. 
- Find the null space
- combine them. 

### Rank and Solvability
#### Column Rank
Suppose an $m \times n$ matrix $A$ of rank $r$. 

```ad-note
title:
Note: $r$ must be less than or equal to $n$ and $m$ both
```

If $r = n$ we say the matrix has <font color=gree>full column rank</font>. In this case, the column space $C(A)$ is $\mathbb{R}^n$. The null space is the origin/the zero vector. $Ax=b$ has exactly one solution, which is $x_\text{particular}$ if it exists, or else none. 

Example with $r = n < m$.

$$A = \begin{bmatrix} 1 & 3 \\2 & 1 \\ 6 & 1 \\ 5 & 1\end{bmatrix}$$
This matrix clearly has two pivots. Let's eliminate to be sure:
$$\begin{bmatrix} 1 & 3 \\0 & -5 \\ 0 & -17 \\ 0 & -14\end{bmatrix}$$
$$R = \begin{bmatrix} \cellcolor{#9999}1 & 0 \\0 & \cellcolor{#9999}1\\ 0 & 0 \\ 0 & 0\end{bmatrix}$$

So it has full column rank. The last two rows are combos of the first two. Solutions to $Ax = b$ exist iff $b$ is in the col-space. 



#### Row Rank

What about row rank? Full row rank means $r = m$. (with $m \leq n$). How many pivots? $m$. Every row has a pivot. 

Solvability: Can solve $Ax = b$ for every $b$ - no zero rows means no requirements (in other words, column space is equal to $\mathbb{R}^m$; and $b$ has $m$ elements. 

Example where $r = m < n$

$$A = \begin{bmatrix} 1 & 2 & 6 & 5 \\ 
3 & 1 & 1 & 1\end{bmatrix} $$
$$R = \begin{bmatrix} 1\cellcolor{#9999} & 0 & ? & ? \\ 
0 & \cellcolor{#9999}1 & ? & ?\end{bmatrix} $$
Right part over there is $F$ from finding the null space. Infinitely many solutions: more (independent) unknowns than (independent) equations


#### Square Matrix

Matrix with $r = m = n$. This is just <font color=gree>full rank</font>. It's square. It's invertible. RREF is $I$. 
Null space is the zero vector. 
All $b$ have unique solutions, since they are all in the column space. 


| Type                                      | Equation    | Solvability                                           |
| ----------------------------------------- | ----------- | ----------------------------------------------------- |
| Less than full row rank                   | $r < m$     | No solutions for some $b$                             |
| Full row rank, less than full column rank | $r = m < n$ | Infinite solutions                                    |
| Full column rank, less than full row rank | $r = n < m$ | one solution for some $b$ (colspace), none for others |
| Square/Full Rank/Invertible               | $r = m = n$ | One solution for each $b$                                                      |
