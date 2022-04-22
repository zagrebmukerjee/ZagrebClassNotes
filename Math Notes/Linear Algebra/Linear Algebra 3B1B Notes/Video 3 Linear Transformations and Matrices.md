---
date updated: 2021-06-11 13:23

notetype: "Math Class Note"
cssclass: math-class-note

tags:
  - '#types/classes'
---

#### [[Video 3 Linear Transformations and Matrices]]

- [[#How to Do Transformations|How to Do Transformations]]
- [[#Some general transformations:|Some general transformations:]]
- [[#NOTE: Linear Dependence|NOTE: Linear Dependence]]
- [[#3D Case (Video 5)|3D Case (Video 5)]]


A matrix is a function $L(\mathbf{v})$. It's basically moving a vector around; rotating it, squishing it, etc. 
The transformation $L$ can be thought of as transforming all of space (when applied to every vector). 

Linear transformations have two properties:
- All lines must remain straight
- The origin must stay where it is. 

A transformation can be wholly represented by its effects on $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$ (the basis of $\mathbb{R}^2$, see [[Video 2 Linear Combinations, Span, and Basis Vectors|Video 2]]). We can use the linearity assumption:

$$ L(\mathbf{v}) = v_1 \, L(\mathbf{\hat{i}}) + v_2 \, L(\mathbf{\hat{j}})$$

If we know where the basis vectors land, we can reconstruct any vector. 

##### How to Do Transformations

Suppose $\mathbf{\hat{i}}$ lands at $\begin{bmatrix}  1\\ -2 \end{bmatrix}$and $\mathbf{\hat{j}}$ lands at $\begin{bmatrix}  3\\ 0 \end{bmatrix}$. Then we can write:
$$ L(\mathbf{v}) = v_1 \begin{bmatrix}  1\\ -2 \end{bmatrix} + v_2 \begin{bmatrix}  3\\ 0 \end{bmatrix}$$
$$ L(\mathbf{v}) = \begin{bmatrix}1v_1 +3v_2 \\ -2v_1 + 0v+_2\end{bmatrix}$$

We only need these 4 numbers. We can encode them in a matrix, thus: 
$$ L = \begin{bmatrix} 1 & 3 \\ -2 & 0\end{bmatrix}$$
The columns here are the new basis we're using. 

More generally, 
$$ L = \begin{bmatrix} a & b \\ c & d\end{bmatrix}$$
$$ L(\mathbf{v}) = \begin{bmatrix}a \\ c\end{bmatrix}v_1 + \begin{bmatrix}b \\ d\end{bmatrix}v_2$$
$$ L(\mathbf{v}) = \begin{bmatrix}av_1 + bv_2 \\ cv_1 + dv_2\end{bmatrix}$$

This is matrix multiplication.


##### Some general transformations: 
90-degree rotation:
$$ L = \begin{bmatrix} 0 & -1 \\ 1 & 0\end{bmatrix}$$
Shear
$$ L = \begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix}$$

##### NOTE: Linear Dependence 
if the new $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$  are linearly dependent, then $L$ squishes 2D space into a line. See [[Video 7 Inverse, Null Space, Column Space, Rank#Rank]]

##### 3D Case (Video 5)

Same applies, except we now need to know where $\mathbf{\hat{i}}$,  $\mathbf{\hat{j}}$, and $\mathbf{\hat{k}}$ land.



