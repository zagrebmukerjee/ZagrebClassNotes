---
aliases:
creation date: 2022-05-16 22:28
date updated: 2022-05-16 22:28

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

To find the complete solution to $Ax = b$: First, find a particular solution that works. E.g. set all free variables to zero. In this case, $x_2 = x_4 = 0$. Then we have (from the echelon form): 

$$
\begin{aligned}
x_1 +  2x_3 &= b_1\\
2x_3 &= b_2 - 2b_1\\
\end{aligned}
$$

So it follows that $x_3 = b_2/2 - b_1$ and $x_1 = 3b_1 - b_2$. 

Suppose $b_1 = 1
