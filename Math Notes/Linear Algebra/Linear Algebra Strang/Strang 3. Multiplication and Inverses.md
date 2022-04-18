---
date updated: 2022-03-21 16:53

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/linalg'
- '#🚧'
---

# [[Strang 3. Multiplication and Inverses]]

For my next trick I will try to unlearn the effective but conceptually limiting method of matrix multiplication that I've used for ~ 15 years...

Let $A$ be a matrix: then $A_{i,*}$ is the $i^{th}$ row of $A$, and $A_{*,j}$ the $j^{th}$ column.

### Rows and Columns

Suppose matrices $A$ and $B$. $AB$ is defined if $A$ is $m \times n$ and $B$ is $n \times k$; we can say that $A$ and $B$ are 'conformable'. If they are, then let $AB = C$;

$$ C_{i,j} = \sum_{\rho = 1}^n A_{i,\rho}B_{\rho,j}$$
$$C_{i,j} = A_{i,*} \cdot B_{*,j}$$
in other words, entry $C_{ij}$ is the dot product of row $i$ of $A$ and column $j$ of $B$. 


### Columns of $A$


Another way to get $C$:

$$C = \begin{bmatrix}AB_{*,1}, AB_{*,2}, \ldots AB_{*,k}\end{bmatrix}$$
Looking at that first column, 

$$AB_{*,1} = A\begin{bmatrix} B_{1,1} \\
B_{2,1} \\
\vdots \\
B_{n,1}\end{bmatrix} = 
B_{1,1} \begin{bmatrix} A_{1,1} \\
A_{2,1} \\
\vdots \\
A_{m,1}\end{bmatrix} + 
\cdots + 
B_{n,1} \begin{bmatrix} A_{1,1} \\
A_{2,1} \\
\vdots \\
A_{m,1}\end{bmatrix} 
$$

In other words, $C$ is a linear combination of the columns of $A$. 


### Rows of $B$

A third way to get $C$: 

$$ C = \begin{bmatrix} A_{1,*}B \\
A_{2,*}B \\
\vdots \\
A_{m,*}B \\ 
\end{bmatrix}
$$

Then our first row is:

$$A_{1,*}B = \begin{bmatrix} A_{1,1} & A_{1,2} & \cdots & A_{1,n} \end{bmatrix} \;B = A_{1,1} B_{1,*} + \cdots + A_{1,n} B_{1,*}$$

So $C$ is a linear combination of the rows of $B$. 

### Columns and Rows

A fourth way: We know the entries are the  products of the rows of $A$ and the columns of $B$. What is the product of the $n$ columns of $A$ and the $n$ rows of $B$? Let's take the first one:

$$ \begin{bmatrix} A_{1,1} \\ A_{2,1} \\ \vdots \\ A_{m,1}\end{bmatrix}\begin{bmatrix} B_{1,1} & B_{1,2} & \cdots & B_{1,k}\end{bmatrix} = \begin{bmatrix}
A_{1,1}B_{1,1}  & \cdots & A_{1,1}B_{1,k} \\
A_{2,1}B_{1,1} & \cdots & A_{2,1}B_{1,k} \\
\\
A_{m,1}B_{1,1} & \cdots & A_{m,1}B_{1,k} \\
\end{bmatrix}$$
The first row of our result is $A_{1,1}B_{1,*}$; the first entry is $A_{1,1}B_{1,1}$. 

Were we to do this with the second row and column, the first row would be $A_{1,2}B_{2,*}$; the first entry would be $A_{1,2}B_{2,1}$. In other words, we can write $C$ as the sum of $m\times k$ matrices 

$$ C = \sum^n_{i=1} A_{*,i}B_{i,*}$$

### Block Multiplication

We can write block matrices: 

$$ \begin{bmatrix}
A_1 &|& A_2 \\ 
A_3 &|& A_4 
\end{bmatrix}
\begin{bmatrix}
B_1 &|& B_2 \\ 
B_3 &|& B_4 
\end{bmatrix}
= 
\begin{bmatrix}
A_1B_1 + A_2 B_3 &|& A_1B_2 + A_3 B_4 \\ 
A_3B_1 + A_4 B_3  &|& A_3 B_2 + A_4 B_4 
\end{bmatrix}
$$

Apparently not even Gauss could easily see that it worked. 