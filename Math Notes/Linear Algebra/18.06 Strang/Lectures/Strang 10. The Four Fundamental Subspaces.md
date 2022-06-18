---
aliases:
creation date: 2022-06-13 19:40
date updated: Monday, June 13th 2022, 8:15 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 10. The Four Fundamental Subspaces]]
[[18.06  Linear Algebra Strang]]

The four fundamental subspaces of a matrix? It's not that hard to guess many of them:

1) The column space
2) The null space
3) The row space, or the column space of $A'$
4) The left null space (the set of $x$ such that $xA = 0$)

If $A$ is $m \times n$ then the column space is in $\R^m$, the null space is in $\R^n$, the row space is in $\R^n$, and the left null space is in $\R^m$. 

The column space $C(A)$ is dimension $r$; the pivot columns are a basis.
The row space, or $C(A')$, is dimension $r$;
The null space $N(A)$ is dimension $n - r$, with the special solutions as a basis;
and the left null space $N(A')$ is dimension $m - r$. 

Is there a way to find $C(A')$ and $N(A')$ without having to do row reduction on $A'$? Turns out there is.

$$A = \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1& 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \\\end{bmatrix}$$
Do row operations:
$$\begin{bmatrix} 1 & 2 & 3 & 1 \\ 0& -1 & -1 & 0 \\ 0 & 0 & 0 & 0 \\\end{bmatrix}$$

$$\begin{bmatrix} 1 & 0 & 1 & 1 \\ 0& 1 & 1 & 0 \\ 0 & 0 & 0 & 0 \\\end{bmatrix}$$
So the special solutions are $[-1, -1, 1, 0]'$ and $[-1,0,0,1$] which form a basis for $N(A)$. 

```ad-warning
$C(A)$ is not the same as $C(R)$! Row operations do not preserve the column space.
```

The basis for the row space is the first $r$ rows of $R$. It's not guaranteed that that's the case for $A$.... 

So the basis for $C(A')$ is $[1,0,1,1]'$ and $[0,1,1,0]'$. 


Now... How can I get to $N(A')$ from what I have done so far? 

Suppose I write $\begin{bmatrix} A & I\end{bmatrix}$ as with Gauss-Jordan. Then I do row reduction. So I end up with $\begin{bmatrix} R & E\end{bmatrix}$. This $E$ matrix encodes the row operations that get from $A$ to $R$ - $EA = R$. 

So what it is: 

$$ \begin{bmatrix} A & I\end{bmatrix}= \begin{bmatrix} 1 & 2 & 3 & 1 &|& 1 & 0 & 0 \\ 1& 1 & 2 & 1 &|& 0 & 1 & 0\\ 1 & 2 & 3 & 1 &|& 0 & 0 & 1\\ \end{bmatrix}$$
$$ \begin{bmatrix} 1 & 2 & 3 & 1 &|& 1 & 0 & 0 \\ 0& 1 & 1 & 0 &|& 1 & -1 & 0\\ 0 & 0 & 0 & 0 &|& \cellcolor{#912}-1 &\cellcolor{#912} 0 & \cellcolor{#912}1\\ \end{bmatrix}$$
But wait! That last column describes row operations done to get a zero row; in other words, the linear combination of rows of $A$ that gives zero!
That means that it's a basis for the left null space! 
$$xA = \begin{bmatrix} -1 & 0 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 3 & 1 \\ 1& 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \\\end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\\end{bmatrix}$$

Voila!



$C(A) \cup N(A')$ forms $\R^m$, and $C(A') \cup N(A)$ is $\R^n$. 
