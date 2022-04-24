---
date updated: 2021-06-10 22:43

notetype: "Math Class Note"
cssclass: math-class-note

tags:
- '#types/classes/math/linalg'
---

#### [[Digression - Gauss-Jordan Elimination and Computing Inverses]]
[[Misc Linear Algebra]]
- [[#Solving Linear Systems of Equations|Solving Linear Systems of Equations]]
- [[#Finding Inverses with the power of Gauss|Finding Inverses with the power of Gauss]]

##### Solving Linear Systems of Equations

Gauss-Jordan elimination is a technique for turning a matrix into _reduced row-echelon form_, such that $R_{i,j} = 1$ if $i=j$ and $0$ otherwise. This can be applied to matrices of any shape. 

It turns out that this offers a very fast way to solve linear systems of equations. Consider 

$$\begin{array}{lccl} 
x &-& 3y & = -3 \\   
2x &+& y & = 8 \\  
\end{array}$$

We can represent this as an _augmented matrix_, with 
$$\begin{bmatrix}
1 & -3 &|& -3 \\   
2 & 1  &|&   8 \\  
\end{bmatrix}$$

The process of Gauss-Jordan elimination consists of manipulating  the augmented matrix with three elementary row operations: 
- Interchanging rows
- Multiply a row by a scalar
- Add or subtract one row from another

This might be familiar - it is a simplified form of solving systems of equations by isolating variables and substituting them into other equations. 

Practice with the above:

$$\begin{bmatrix}
1 & -3 &|& -3 \\   
2 & 1  &|&   8 \\  
\end{bmatrix}$$

Subtract  the first row twice from the second (to get a value for $y$):

$$\begin{bmatrix}
1 & -3 &|& -3 \\   
2-2(1) & 1-2(-3)  &|&   8 -2(-3) \\  
\end{bmatrix}$$

$$\begin{bmatrix}
1 & -3 &|& -3 \\   
0 & 7  &|&   14 \\  
\end{bmatrix}$$

Divide the last row by $7$. Then add it $3$ times to first row to clear up that annoying $-3$:

$$\begin{bmatrix}
1 & -3 &|& -3 \\   
0 & 1  &|&   2 \\  
\end{bmatrix}$$

$$\begin{bmatrix}
1 & -3 + 3(1) &|& -3+ 3(2) \\   
0 & 1  &|&   2 \\  
\end{bmatrix}$$


$$\begin{bmatrix}
1 & 0 &|& 3 \\   
0 & 1  &|&   2 \\  
\end{bmatrix}$$

Thus, $x = 3$ and $y = 2$. We can test with the original system:

$$\begin{array}{lccl} 
3 &-& 3(2) & = -3 \\   
2(3) &+& 2 & = 8 \\  
\end{array}$$

Perfect!

Now with a system of 3 equations in 3 variables:

$$\begin{array}{lccccl} 
x &+& y &+& 2z& = 2 \\   
3x &-& 2y &+& z& = 1 \\   
0x &+& y &-& z& = 3 \\   
\end{array}$$

Matrix: 

$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
3 & -2 & 1 &|& 1 \\   
0 & 1 & -1 &|& 3 \\   
\end{bmatrix}$$

We'll start by subtracting the first row thrice from the second:


$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
3 - 3(1) & -2 - 3(1) & 1 - 3(2) &|& 1 -3(2) \\   
0 & 1 & -1 &|& 3 \\   
\end{bmatrix}$$


$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
0 & -5 & -5 &|& -5 \\   
0 & 1 & -1 &|& 3 \\   
\end{bmatrix}$$

We can divide row 2 by $-5$ and then subtract it from row 3

$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
0 & 1 & 1 &|& 1 \\   
0 & 1 & -1 &|& 3 \\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
0 & 1 & 1 &|& 1 \\   
0 & 1-1 & -1-1 &|& 3-1 \\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
0 & 1 & 1 &|& 1 \\   
0 & 0 & -2 &|& 2 \\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 1 & 2 &|& 2 \\   
0 & 1 & 1 &|& 1 \\   
0 & 0 & 1 &|& -1 \\   
\end{bmatrix}$$

Then we subtract row 3 from row 2, and twice from row 1


$$\begin{bmatrix}
1 & 1 & 0 &|& 4 \\   
0 & 1 & 0 &|& 2 \\   
0 & 0 & 1 &|& -1 \\   
\end{bmatrix}$$

and subtract row 2 from 1:

$$\begin{bmatrix}
1 & 0 & 0 &|& 2 \\   
0 & 1 & 0 &|& 2 \\   
0 & 0 & 1 &|& -1 \\   
\end{bmatrix}$$

Finished: $x = y = 2$ and $z = -1$. 

$$\begin{array}{lccccl} 
2 &+& 2 &-& 2& = 2 \\   
6 &-& 4 &-& 1& = 1 \\   
0 &+& 2 &+& 1& = 3 \\   
\end{array}$$

##### Finding Inverses with the power of Gauss

For matrix $A$, if $B$ is its inverse, then we know 

$$AB = BA = I$$

If $BA = I$, then solving for B is solving $n$ linear systems where each column of $B$ is solved for a column in $I$. 

Let $A$ be a 3x3 matrix. 


$$AB = I$$

This creates three systems of equations:
$$A \begin{bmatrix}b_{1,1}\\b_{2,1}\\b_{3,1}\end{bmatrix}= \begin{bmatrix}1\\0\\0\end{bmatrix}$$
$$A \begin{bmatrix}b_{1,2}\\b_{2,2}\\b_{3,2}\end{bmatrix}= \begin{bmatrix}0\\1\\0\end{bmatrix}$$
$$A \begin{bmatrix}b_{1,3}\\b_{2,3}\\b_{3,3}\end{bmatrix}= \begin{bmatrix}0\\0\\1\end{bmatrix}$$

We can solve all of these at once,  as follows. 

Let $A$ be this matrix:


$$\begin{bmatrix}
3 & 0 & 2 \\   
2 & 0 & -2\\   
0 & 1 & 1  \\   
\end{bmatrix}$$

We can create an "augmented matrix" by appending the identity matrix


$$\begin{bmatrix}
3 & 0 & 2 &|& 1 & 0 & 0 \\   
2 & 0 & -2&|& 0 & 1 & 0\\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
\end{bmatrix}$$

Now, we can do Gauss-Jordan elimination to get the left side into RREF. 

$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
2 & 0 & -2&|& 0 & 1 & 0\\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
2-2(1) & 0 & -2 - 2(\frac{2}{3})&|& -2(\frac{1}{3}) & 1 & 0\\   
\end{bmatrix}$$


$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
0 & 0 & -\frac{10}{3}&|& -\frac{2}{3} & 1 & 0\\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
0 & 0 & -\frac{10}{3}( -\frac{3}{10})&|& -\frac{2}{3} (-\frac{3}{10}) & 1(-\frac{3}{10}) & 0\\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 1 &|& 0 & 0 & 1\\   
0 & 0 & 1&|& \frac{2}{10} & -\frac{3}{10} & 0\\   
\end{bmatrix}$$


$$\begin{bmatrix}
1 & 0 & \frac{2}{3} &|& \frac{1}{3} & 0 & 0 \\   
0 & 1 & 0 &|& -\frac{2}{10} & \frac{3}{10} & 1\\   
0 & 0 & 1&|& \frac{2}{10} & -\frac{3}{10} & 0\\   
\end{bmatrix}$$

$$\begin{bmatrix}
1 & 0 & \frac{2}{3}-\frac{2}{3} &|& \frac{1}{3}-(\frac{2}{3})(\frac{2}{10}) & -(\frac{2}{3})(-\frac{3}{10}) & 0 \\   
0 & 1 & 0 &|& -\frac{2}{10} & \frac{3}{10} & 1\\   
0 & 0 & 1&|& \frac{2}{10} & -\frac{3}{10} & 0\\   
\end{bmatrix}$$


$$\begin{bmatrix}
1 & 0 & 0 &|& \frac{2}{10} & \frac{2}{10} & 0 \\   
0 & 1 & 0 &|& -\frac{2}{10} & \frac{3}{10} & 1\\   
0 & 0 & 1&|& \frac{2}{10} & -\frac{3}{10} & 0\\   
\end{bmatrix}$$

Now we check:


$$\begin{bmatrix}
\frac{2}{10} & \frac{2}{10} & 0 \\   
-\frac{2}{10} & \frac{3}{10} & 1\\   
\frac{2}{10} & -\frac{3}{10} & 0\\   
\end{bmatrix}\begin{bmatrix}
3 & 0 & 2 \\   
2 & 0 & -2\\   
0 & 1 & 1  \\   
\end{bmatrix} \: = \: \begin{bmatrix}
1 & 0 & 0 \\   
0 & 1 & 0\\   
0 & 0 & 1  \\   
\end{bmatrix}$$
