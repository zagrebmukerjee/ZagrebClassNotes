---
date updated: 2021-06-10 19:54

notetype: "Math Class Note"
cssclass: math-class-note

tags:
- '#types/classes/math/linalg'
---

#### [[Video 6 Determinant]]

Some linear transformations "stretch" space - others "squish" it. 

How much are things stretched or squished - i.e., how does the area of a given region change? 

Consider the unit square: $(0,0); (0,1); (1,0);$ and $(1,1)$; and consider $L = \begin{bmatrix} 3 & 0 \\ 0 & 2\end{bmatrix}$ - a "rotation and stretch". Where do these coordinates go?

$(0,0)$ stays fixed. $(0,1)$ goes to $(0,2)$, $(1,0)$ to $(3,0)$, and $(1,1)$ to $(3,2)$. So width goes from $1$ to $3$, and height goes to $2$; area multiplies by a factor of 6. 

This is the _determinant_. 

This is a scalar, constant for each $L$ - since all shapes map to the unit square. If the determinant is 0, the transformation is a line - i.e. the columns are linearly dependent. 
 
A negative determinant means that you're "flipping" space - is $\mathbf{\hat{i}}$ to the right of  $\mathbf{\hat{j}}$ as usual, or is it to the left? 

In 3D, it's the change in volume of the unit cube, which can turn into a bigger cube or a parallelepiped. Determinant $0$ means that transformation maps to a plane or line. 


Formula for a 2D matrix:

$$\text{det}\begin{bmatrix} a & b \\ c & d\end{bmatrix} = ad - bc$$

Formula is intuitive if $b$ and $c$ are $0$. It can be proved geometrically. 

![[Pasted image 20210610220336.png]]