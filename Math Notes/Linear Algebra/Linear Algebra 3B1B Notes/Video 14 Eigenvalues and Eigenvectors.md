---
date updated: 2021-06-14 22:48

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/math/linalg'
---

#### [[Video 14 Eigenvalues and Eigenvectors]]

##### Introduction

Consider a linear transformation $T$. Applied to a vector $\mathbf{v}$, what does it do to the span of $\mathbf{v}$ (the set of vectors parallel or antiparallel to $\mathbf{v}$)?

Most vectors are "knocked off their span" - $\mathbf{v}$ and $T\mathbf{v}$ have different span. But some vectors are not. These are the _eigenvectors._ $T$ just squishes or stretches these vectors as if it were a scalar multiplication. 

$$T = \begin{bmatrix} 3 & 1 \\ 0 & 2 \end{bmatrix}$$

This transformation does not move $\mathbf{\hat{i}}$ off of its span (the x-axis).

$$T\mathbf{\hat{i}} = \begin{bmatrix} 3 & 1 \\ 0 & 2 \end{bmatrix}\begin{bmatrix} 1 \\ 0\end{bmatrix} = \begin{bmatrix} 3 \\ 0\end{bmatrix}$$

However, it does scale $\mathbf{\hat{i}}$ to $3\mathbf{\hat{i}}$.  The $3$ here is called an _eigenvalue_. Each eigenvector has a eigenvalue, and each eigenvalue has at least one eigenvector.

##### Computing eigenstuffs

Given a transformation $A$ and unknown eigenvector $\mathbf{v}$ and eigenvalue $\lambda$, we write

$$ A\mathbf{v} = \lambda \mathbf{v}$$
$$ A\mathbf{v} = \lambda I \mathbf{v}$$
$$ (A - \lambda I)\mathbf{v} = 0$$

From this we can see that 0 is always an eigenvector with eigenvalue 0. But that is not very interesting. To find better eigenvectors we have to solve for $\mathbf{v}$ and $\lambda$. 

We know that if $T\mathbf{v} = 0$ then det$(T) = 0$. So we can isolate $\lambda$: 

$$ \text{det}(A - \lambda I) = 0$$

Example: consider

$$A = \begin{bmatrix} 2 & 2 \\ 1 & 3\end{bmatrix}$$

$$ \text{det}(A - \lambda I ) = \begin{bmatrix} 2- \lambda & 2 \\ 1 & 3 - \lambda\end{bmatrix} = 0$$

$$ (\lambda-2)(\lambda-3) - 2 = 0$$
$$ \lambda^2 -5\lambda + 4 = 0$$
$$ (\lambda-4)(\lambda-1) = 0$$

This quadratic (called the _characteristic polynomial_ has roots $\lambda = 4$ and $\lambda = 1$, our eigenvalues. 

Now we can use the eigenvalues to solve for the eigenvectors. Take $\lambda = 4$:

$$ (A - \lambda I)\mathbf{v} = \begin{bmatrix} 2-4 & 2 \\ 1 & 3-4\end{bmatrix}\mathbf{v}= \begin{bmatrix} -2 & 2 \\ 1 & -1\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}= 0$$

We can solve this like any other system of equations (see [[Digressions - Eigenvectors#Finding Eigenvectors]])

There can be no eigenvectors, such as with the 90$^\circ$ rotation: 

$$A = \begin{bmatrix} 0 & -1 \\ 1 & 0\end{bmatrix}$$

The characteristic polynomial here is $\lambda^2 + 1$, which has imaginary roots - hence no (real) eigenvalues or vectors. 


##### Uses

What does an eigenvector get us? It gets us a general sense of the direction of a transformation - something like a cross-section. It is a distillation of what a transformation does. 

For example, consider a 3D rotation. The eigenvector for that rotation will be the axis of rotation for that transformation. 

One neat trick is using this to compute powers of arbitrary non-diagonal matrices. If $D$ is an $n \times n$ diagonal matrix, then $D^k$ is easy to compute: 

$$D^k = \begin{bmatrix} d_{1,1}^k & 0 & \ldots & \ldots & 0 \\
0 & d_{2,2}^k & 0 &\ldots & 0 \\
& & \ddots & & \\
0 &0 & \ldots & d_{n-1,n-1}^k & 0 \\
0 & \ldots & \ldots & 0 & d_{n,n}^k\end{bmatrix}$$

If $A$ is non-diagonal, do not despair! All we need to do is convert $A$ to a basis in which $A$ is diagonal. 

Diagonal vectors are vectors such that the eigenvectors are a basis, and vice versa. Consider a $2\times 2$  diagonal matrix with $d_1$ and $d_2$ on the diagonal. This has characteristic polynomial $(\lambda-d_1)(\lambda - d_2)$, with eigenvalues $d_1$ and $d_2$. Then:

$$ \begin{bmatrix} d_1 -d_2 & 0 \\ 0 & d_2 - d_2\end{bmatrix}\begin{bmatrix}v_1 \\ v_2\end{bmatrix} = 0 \rightarrow\begin{bmatrix} d_1-d_2 & 0 &|& 0\\ 0 & 0 &|& 0\end{bmatrix}$$

$$ \begin{bmatrix} d_1 -d_1 & 0 \\ 0 & d_2 - d_1\end{bmatrix}\begin{bmatrix}v_1 \\ v_2\end{bmatrix} = 0 \rightarrow\begin{bmatrix} 0 & 0 &|& 0\\ 0 & d_2 - d_1 &|& 0\end{bmatrix}$$


So for the first eigenvalue, $v_1 = d_1 - d_2$ and $v_2=0$, and for the second,  $v_1 = 0$ and $v_2 = d_2-d_1$ - two linear transformations of the basis vectors. The basis vectors that are eigenvectors are called an _eigenbasis_.

##### Example

So our new basis needs to have $\mathbf{b_1}, \mathbf{b_2}$ be the eigenvectors of $A$ - if those eigenvectors span $\mathbb{R}^2$. Then, in this new basis, $A$ will have eigenvectors $(1,0)$ and $(0,1)$, meaning it will be diagonal. 


Let $A = \begin{bmatrix} 3 & 1 \\ 0 & 2\end{bmatrix}$. What is $A^4$? In this case, using Wolfram Alpha, it's $\begin{bmatrix} 81 & 65 \\ 0 & 16\end{bmatrix}$. Imagine computing that by hand. Disgusting. 

Let's figure out the basis to use instead. The characteristic polynomial here is $(\lambda-3)(\lambda-2)$; the eigenvalues are $3$ and $2$. 
 
 The eigenvector for $3$ is 
 
 $$(A - 3 I)\mathbf{v} = 0$$
  $$\begin{bmatrix} 0 & 1 \\ 0 & -1\end{bmatrix}\begin{bmatrix}v_1 \\ v_2\end{bmatrix} = 0$$
  
  So one basis vector is $\mathbf{\hat{i}}$, as we found before. The other is:
  
  
 $$(A - 2 I)\mathbf{v} = 0$$
  $$\begin{bmatrix} 1 & 1 \\ 0 & 0 \end{bmatrix}\begin{bmatrix}v_1 \\ v_2\end{bmatrix} = 0$$
  
  The other basis vector is $(-1,1)$ - or vice versa. 
  
  So let's try it out:
  
  $$B =  \begin{bmatrix} 1 & -1 \\ 0 & 1\end{bmatrix}$$
  
  $$ B^{-1} \rightarrow \begin{bmatrix} 1 & -1 &| & 1 & 0\\ 0 & 1 &| & 0 & 1\end{bmatrix}$$
  
  $$\begin{bmatrix} 1 & 0 &| & 1 & 1\\ 0 & 1 &| & 0 & 1\end{bmatrix}$$
  
  $$AB =  \begin{bmatrix} 3 & 1 \\ 0 & 2\end{bmatrix}\begin{bmatrix} 1 & -1 \\ 0 & 1\end{bmatrix} = \begin{bmatrix} 3 & -2 \\ 0 & 2\end{bmatrix}$$
  
  $$A_b =B^{-1}AB = \begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix}\begin{bmatrix} 3 & -2 \\ 0 & 2\end{bmatrix} = \begin{bmatrix} 3 & 0 \\ 0 & -2\end{bmatrix}$$
  
  Voila!
  
  So  $A_b^4$ is simple(r) to calculate: $\begin{bmatrix} 81 & 0 \\ 0 & 16\end{bmatrix}$. But we now need to bring it back to our basis:
  
  
 $$ A^4 = B(A_b^4)B^{-1} = \begin{bmatrix} 1 & -1 \\ 0 & 1\end{bmatrix}\begin{bmatrix} 81 & 0 \\ 0 & 16\end{bmatrix}\begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix} $$
 
 
 $$ A^4  = \begin{bmatrix} 81 & -16 \\ 0 & 16\end{bmatrix}\begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix} $$
 
  $$ A^4  = \begin{bmatrix} 81 & 65 \\ 0 & 16\end{bmatrix}$$
  
  Hooray!
  
  For another case, see [[Digressions - Eigenvectors#Change of Basis Adventures]].