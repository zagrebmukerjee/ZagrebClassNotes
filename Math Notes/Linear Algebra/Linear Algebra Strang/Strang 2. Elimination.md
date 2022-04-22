---
date updated: 2022-03-21 13:23

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 2. Elimination]]

How to solve systems of equations? Turn it into an augmented matrix and eliminate.  

Want to do elementary row operations until you have an upper-triangular matrix. Then can 'back-substitute'.
Elementary row operations:
- Add $c$ times a row to another row
- Switch rows

Recall ex. from last lecture: 

$$\begin{aligned}
2x - y   &= 0 \\
-x + 2y  -z &= -1 \\
 - 3y  -4z &= 4 \\
\end{aligned}$$
In augmented matrix form, this is:

$$
\begin{bmatrix}
2 & -1 & 0 &|& 0 \\
-1 & 2 & -1 &|& -1 \\
0 & -3 & -4 &|& 4 \\
\end{bmatrix}
$$
Add half the first row to the second; then add twice the new second row to the third. 
$$
\begin{bmatrix}
2 & -1 & 0 &|& 0 \\
0 & 3/2 & -1 &|& -1 \\
0 & 0 & -6 &|& 2 \\
\end{bmatrix}
$$
Let's call this upper triangular matrix $U$. 

Think of what we did in terms of the full system of equations again. We added the equations to each other until we get: 

$$\begin{aligned}
2x - y   &= 0 \\
3y/2  -z &= -1 \\
   -6z &= 2 \\
\end{aligned}$$
This is the same sort of thing we would try to do if solving in the old-fashioned way: isolate a variable, then substitute into the other equations.

The diagonal elements of the reduced matrix are 'pivots'. Determinants are product of pivots.

The pivots can't be zero. If they are forced to be, and you can't fix it through exchanging or adding rows, then system is unsolvable $\iff$ matrix is singular <font color=red>Why is this the same as linearly dependent columns</font>

Suppose $A$ is a matrix and $U$ is the upper-triangular matrix resulting from elimination. Before, we wrote linear combinations of the columns of a matrix as $Ax$. Now we can write a linear combination of the rows as $xA$. 

Let $R_1, R_2, R_3$ be the rows of $A$. Imagine I wanted the output of our first elimination step: the second row plus half the first. That's easy:
$$ xA = R_2 + (1/2)R_1 = \begin{bmatrix} 0 & 3/2 & -1\end{bmatrix}$$
$$ x = \begin{bmatrix}1/2 & 1 & 0\end{bmatrix} $$
But I don't just want the new $R_2'$; I want a matrix that's the same as $A$, except for replacing its second row. So I will add to $x$ some rows that say "keep $R_1$ and $R_3$ the same". 

$$ E_1A = \begin{bmatrix} R_1 \\ R_2 + (1/2)R_1 \\ R_3 \end{bmatrix} = \begin{bmatrix}
2 & -1 & 0 \\
0 & 3/2 & -1 \\
0 & 0 & -6 \\
\end{bmatrix}$$

$$ E_1 = \begin{bmatrix}
1 & 0 & 0 \\
1/2 & 1 & 0  \\
0 & 0 & 1 \\
\end{bmatrix} $$


$E_1$ is the matrix that represents the first step of elimination - i.e., if elimination has $n$ steps, $E_n E_{n-1} \ldots E_2 E_1 A = u$. 

$E$ is the product of those elimination matrices. 


In the above example, we first added half the first row to the second.

$$E_1 = \begin{bmatrix}
1 & 0 & 0\\
1/2 & 1 & 0 \\
0 & 0 & 1 \\
\end{bmatrix}$$
Then we add twice the new second row to the third:

$$E_2 = \begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0 \\
0 & 2 & 1 \\
\end{bmatrix}$$

So to get the full $E$, we can say:

$$E = E_2 E_1 = \begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0 \\
0 & 2 & 1 \\
\end{bmatrix}\begin{bmatrix}
1 & 0 & 0\\
1/2 & 1 & 0 \\
0 & 0 & 1 \\
\end{bmatrix} = \begin{bmatrix}
1 & 0 & 0\\
1/2 & 1 & 0 \\
1 & 2 & 1 \\
\end{bmatrix}$$

We can see the way in which $E$ combines our operations. We did $R_2' = R_2 + (1/2) R_1$ and then $R_3' = R_3 + 2 R_2' = R_3 + 2R_2 + R_1$. 
