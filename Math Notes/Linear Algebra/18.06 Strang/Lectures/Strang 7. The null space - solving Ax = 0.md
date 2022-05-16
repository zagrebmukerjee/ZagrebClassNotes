---
aliases:
creation date: 2022-05-15 19:15
date updated: Sunday, May 15th 2022, 7:15 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 7. The null space - solving Ax = 0]]

3b1b: [[Video 7 Inverse, Null Space, Column Space, Rank]]
[[18.06 Strang]]

The null space of $A$ is $x$ such that $Ax = 0$. Several ways to conceptualize it. 
- Linear transformation $A$ maps vectors in the null space to $0$. That means they are not recoverable
- An invertible matrix has only the origin in its null space (it has to be just one vector - and the origin maps to 0 under all $A$)
- Part of the solution to $Ax = b$ - see the next lecture
- What values can $x$ take, under the constraint that $Ax = 0$? How can we characterize it

## Intro

Example: 

$$A = \begin{bmatrix} 1 & 2 & 2 & 2 \\
2 & 4 & 6 & 8 \\
3 & 6 & 8 & 10 \\
\end{bmatrix}$$

Now do some elimination. Elimination preserves the system of equations and its solutions. So we do not change the null space. 

$$U = \begin{bmatrix} 1 & 2 & 2 & 2 \\
0 & 0 & 2 & 4 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}$$

We can see two pivots. No pivot in column 2 - it's linearly dependent on col 1. 

This is also called 'echelon' form. It's like a staircase. 

There are two pivots. That means the <font color=gree>rank</font> is 2

## Pivot and Free Variables

So we have two <font color=gree>pivot variables</font> and two <font color=gree>free variables</font>. In other words: $Ax$ describes relations between $4$ variables. The constraint $Ax = 0$ determines two variables $x_1, x_3$, but leaves the other two $x_2,x_4$ to take whatever values they want. 

Let's say that $x_2 = 1, x_4 = 0$. Then what do we know? From the second equation we know that $2x_3 + 4x_4 = 0$, so $x_3 = 0$; from the first, we know that $x_1 + 2x_2 + 2x_3 + 2x_4 = 0$, so $x_1 +2 = 0$. So we have a vector of $x$ values $\begin{bmatrix} -2 & 1 & 0 & 0 \end{bmatrix}'$ that is in the null space. 

We can call this a *special solution*. Note - this reiterates the fact that the second column is twice the first.

Now, we can try $x_2 = 0$ and $x_4 = 1$. So $2x_3 + 4 = 0$ and $x_3 = -2$. $x_1 -4 + 2 = 0; x_1 = 2$. Then another vector: $ \begin{bmatrix} 2 & 0 & -2 & \end{bmatrix}