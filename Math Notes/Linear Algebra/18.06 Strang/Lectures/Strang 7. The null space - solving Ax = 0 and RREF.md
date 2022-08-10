---
aliases:
creation date: 2022-05-15 19:15
date updated: Monday, May 16th 2022, 10:45 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 7. The null space - solving Ax = 0 and RREF]]

3b1b: [[Video 7 Inverse, Null Space, Column Space, Rank]]
[[18.06 Linear Algebra Strang]]

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

## Pivot and Free Variables; Special Solutions

So we have two <font color=gree>pivot variables</font> and two <font color=gree>free variables</font>. In other words: $Ax$ describes relations between $4$ variables. The constraint $Ax = 0$ determines two variables $x_1, x_3$, but leaves the other two $x_2,x_4$ to take whatever values they want. 

Let's say that $x_2 = 1, x_4 = 0$. Then what do we know? From the second equation we know that $2x_3 + 4x_4 = 0$, so $x_3 = 0$; from the first, we know that $x_1 + 2x_2 + 2x_3 + 2x_4 = 0$, so $x_1 +2 = 0$. So we have a vector of $x$ values $\begin{bmatrix} -2 & 1 & 0 & 0 \end{bmatrix}'$ that is in the null space. 

We can call this a 
<font color=#F7B801>special solution</font>. Note - this reiterates the fact that the second column is twice the first.

Now, we can try $x_2 = 0$ and $x_4 = 1$. So $2x_3 + 4 = 0$ and $x_3 = -2$. $x_1 -4 + 2 = 0; x_1 = 2$. Then another vector: $\begin{bmatrix} 2 & 0 & -2 & 1\end{bmatrix}'$ 

Obviously any linear combination of these vectors is in the null space. This covers all possible values of the free variables then. So we have the null space: 

$$N(A) = c_1 \begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_2 \begin{bmatrix} 2 \\ 0 \\ -2 \\ 1\end{bmatrix}$$
There will be one special solution per free variable. The number of free variables is the number of cols - number of rank. So an $m \times n$ matrix of rank $r$ has $n - r$ special solutions. 

## Reduced Row-Echelon Form

Work on $U$ some more to make sure it's zeros above AND below the pivots, and divide until they are $1$. So let's go back to the example
ace. 

$$
U = \begin{bmatrix} 1 & 2 & 2 & 2 \\
0 & 0 & 2 & 4 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}$$
That last row appeared because row 3 is a linear combination of rows 1 and 2, which we discovered through elimination. 

$$
R = \begin{bmatrix} \cellcolor{#9999}1 & 2 & \cellcolor{#9999}0 & -2 \\
\cellcolor{#9999}0 & 0 & \cellcolor{#9999}1 & 2 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}$$
This has information. It tells us the pivot rows and columns. We've also found an identity matrix hidden in the pivots. what do we do with that? 

Here's the simplified system of equations:

$$\begin{aligned}
x_1 + 2x_2 -2x_4 &= 0 \\
x_3 + 2 x_4 &= 0 \\
\end{aligned}$$
Note that we've tacitly written the pivots in terms of the free variables! This is the same as getting us the special solutions. 
We can rearrange the variables to get 

$$R = \begin{bmatrix} \cellcolor{#9999}1 & \cellcolor{#9999}0 & 2& -2 \\
\cellcolor{#9999}0 & \cellcolor{#9999}1 &0 & 2 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}$$
just don't forget you've done this. Then we have a block matrix

$$ R = \begin{bmatrix} I & F \\ 0 & 0 \end{bmatrix} $$
We find $N$ such that $RN = 0$; then the columns of $N$ are the special solutions, which implies that 

$$ S = \begin{bmatrix} -F \\ I \end{bmatrix}$$
because 

$$RS = \begin{bmatrix} I & F \\ 0 & 0 \end{bmatrix} \begin{bmatrix} -F \\ I\end{bmatrix} = F - F = 0$$

Alternatively, 


$$ \begin{aligned}
0 &= \begin{bmatrix} I & F \\ 0 & 0 \end{bmatrix}\begin{bmatrix} x_\text{pivot} \\ x_\text{free}\end{bmatrix} \\
0 & = Ix_\text{pivot} + F x_{free} \\
-Fx_\text{free} &= Ix_\text{pivot}
\end{aligned}
$$
We can plug in $I$ for $x_\text{free}$ to get the special solutions. 

Example: 

$$ \begin{bmatrix} 
1 & 2 & 3 \\ 2& 4 & 6 \\ 2 & 6 & 8 \\ 2& 8 & 10
\end{bmatrix}$$

Elimination

$$ \begin{bmatrix} 
1 & 2 & 3 \\ 0& 0 & 0 \\ 0 & 2 & 2 \\ 0& 4 & 4
\end{bmatrix}$$
$$ \begin{bmatrix} 
\cellcolor{#9999}1 & \cellcolor{#9999}0 & 1 \\ \cellcolor{#9999}0 & \cellcolor{#9999}1 & 1 \\ 0& 0 & 0 \\ 0& 0 & 0
\end{bmatrix}$$
So there is one free variable. Either $x_1 = x_3$ or $x_2 = x_3$. We stack:

$$ S = \begin{bmatrix} -1 \\-1\\1\end{bmatrix}$$
We shrink $I$ depending on the number of free variables in this matrix.
