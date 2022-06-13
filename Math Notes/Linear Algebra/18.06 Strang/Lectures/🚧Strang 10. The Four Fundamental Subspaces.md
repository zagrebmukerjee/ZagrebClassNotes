---
aliases:
creation date: 2022-06-13 19:40
date updated: Monday, June 13th 2022, 7:49 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
- '#status/🚧'
---

# [[🚧Strang 10. The Four Fundamental Subspaces]]
[[18.06 Strang]]

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
So the special solutions are $[-1, -1,