---
aliases:
creation date: 2022-06-16 13:57
date updated: Thursday, June 16th 2022, 2:16 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 12. Graphs and Networks]]
Applications of linear algebra: circuits. 

Consider the general form of a graph: 
![[Strang 12. Graphs and Networks 2022-06-16 13.58.16.excalidraw]]

This is simply a list of nodes and edges with labels. 

We can write this as an 'Incidence matrix', where the rows are edges, the columns are nodes, and sign indicates direction. In the above case, then, we have: 
$$A = \begin{bmatrix} -1 & 1 & 0 & 0 \\
0 & -1 & 1 & 0 \\ 
-1 & 0 & 1 & 0 \\
-1 & 0 & 0 & 1\\
0 & 0 & -1 & 1 \\
\end{bmatrix} $$
This problem lends a good deal of structure to our matrices. Most of the entries in this sort of adjacency graph will be zero - in fact, you have at most $2$ points for each edge. <font color=#F7B801>Given n nodes, the maximum number of edges is n(n-1), then the maximum matrix size is n^2(n-1), the maximum nonzero entries are 2n(n-1), and so (n-2)/n of the entries will be zero. </font>

Note that the first 3 rows are not linearly independent, signifying that they are a loop in the graph.
This is a rank 3 matrix: for instance, col 1 + col 2 + col 4 = -col 3. First three columns are a basis for the colspace. 

What is the null space? We can write down a system of equations: 
$$\begin{align}x_2 - x_1 &= 0 \\
x_3 - x_2 &= 0\\
x_3 - x_1 &= 0\\
x_4 - x_1 &= 0\\
x_4 - x_3 &= 0\\
\end{align}$$

This clearly solves out to demonstrate that the nullspace is when everything is the same, $c\begin{bmatrix} 1 & 1 & 1 & 1  \end{bmatrix}'$. In other words, there is no difference between the nodes. If this is a circuit, then it demonstrates that you can only determine potentials to a constant given the equilibrium condition of no potential difference. This is Ohm's law: current = 1/resistance $* \Delta$ potential. 

Now we can look at $A'y= 0$, the left nullspace. It has dimension $m-r$, which is $2$. In this case we have the equations
$$\begin{align}
-y_1 -y_3 -y_4 &= 0 \\
y_1 - y_2 &= 0 \\
y_2 + y_3 - y_5 &= 0 \\
y_4 + y_5 &= 0 \\
\end{align}$$

These are currents. The constant $c$ connects currents to potential differences. This is Krichoff's current law - current in = current out.

Basis for the null space is $\begin{bmatrix} 1 & 1 & -1 & 0 & 0 \end{bmatrix}'$, $\begin{bmatrix} 0 & 0 & 1 & -1 & 1 \end{bmatrix}'$; in other words, sending current around the three loops. 

The graph of the three pivot columns of $A'$ makes a tree, or a graph with no loops. The dimension of $N(A')$ is the number of loops. Given that $m =$ # of edges, $n =$ # of nodes, then we have # of loops = # of edges - (#nodes - 1). This is <font color=gree>Euler's Formula</font>.
