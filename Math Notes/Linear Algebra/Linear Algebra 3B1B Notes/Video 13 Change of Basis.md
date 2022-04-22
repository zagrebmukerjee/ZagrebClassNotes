---
date updated: 2021-06-14 22:48

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/math/linalg'
---

#### [[Video 13 Change of Basis]]

##### Overview

Vector $\mathbf{v} = (v_1, v_2)$ is also $v_1 \mathbf{\hat{i}} + v_2\mathbf{\hat{j}}$. $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$ encode assumptions about our coordinate system - $v_1$ is how far right you are, $v_2$ is how far up, distance units etc. 

We can use different bases. Another way to think of a linear transformation is a change of basis: what are the new equivalents of $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$? The origin stays constant. 

If $\mathbf{b}_1$ and $\mathbf{b}_2$ are the new basis (expressed in our basis), we can move from the $\mathbf{b}$ basis to ours with a matrix $\begin{bmatrix}\mathbf{b}_1 & \mathbf{b}_2\end{bmatrix}$.

To see this, suppose $\mathbf{b}_1 = \begin{bmatrix}b_{1,1}\\b_{2,1}\end{bmatrix}$ and $\mathbf{b}_2 = \begin{bmatrix} b_{1,2}\\ b_{2,2} \end{bmatrix}$. Another way to think of that is 

$$\mathbf{b}_1 = b_{1,1}\mathbf{\hat{i}} + b_{2,1} \mathbf{\hat{j}} \qquad \mathbf{b}_2 = b_{1,2}\mathbf{\hat{i}} + b_{2,2}\mathbf{\hat{j}}$$

If $\mathbf{v} = (v_1, v_2)$ in the $\mathbf{b}$ basis, then (expressed in our basis) we have 

$$\mathbf{v}  = (v_1, v_2) = v_1\mathbf{b}_1  + v_2\mathbf{b}_2 = $$ 
$$v_1( b_{1,1}\mathbf{\hat{i}} + b_{2,1} \mathbf{\hat{j}}) + v_2(
b_{1,2}\mathbf{\hat{i}} + b_{2,2}\mathbf{\hat{j}}) = $$

$$ v_1 b_{1,1}\mathbf{\hat{i}} + v_2
b_{1,2}\mathbf{\hat{i}} + v_1  b_{2,1} \mathbf{\hat{j}} + v_2 b_{2,2}\mathbf{\hat{j}}  = $$ 
$$ (v_1 b_{1,1} +  v_2
b_{1,2}, \quad v_1  b_{2,1} + v_2 b_{2,2} )$$

This looks pretty familiar, because it is matrix-vector multiplication:

$$ \begin{bmatrix} b_{1,1} & b_{1,1}\\ b_{2,1} & b_{2,2} \end{bmatrix}\begin{bmatrix}v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix}v_1 b_{1,2} +  v_2
b_{1,2} \\ v_1  b_{2,1} + v_2 b_{2,2} \end{bmatrix} $$

This gives us the change of basis matrix 

$$\begin{bmatrix} b_{1,1} & b_{1,1}\\ b_{2,1} & b_{2,2} \end{bmatrix} = \begin{bmatrix}\mathbf{b}_1 & \mathbf{b}_2\end{bmatrix}$$

##### Transformations

Now, what if we want to know the equivalent of a transformation $T$ in the $\mathbf{b}$ basis? 


Suppose the new basis, as above, is $\mathbf{b}_1 = \begin{bmatrix}2\\1\end{bmatrix}$ and $\mathbf{b}_2= \begin{bmatrix}-1\\1\end{bmatrix}$, and $T$ is a simple rotation: 

$$T = \begin{bmatrix} 0 & -1 \\1 & 0 \end{bmatrix}$$

What is $T( \begin{bmatrix}-1\\2\end{bmatrix})$, where $\begin{bmatrix}-1\\2\end{bmatrix}$ is expressed in the $\mathbf{b}$ basis?

First we translate it to our basis:

$$ \begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}\begin{bmatrix}-1\\2\end{bmatrix}$$

Then we rotate it - in our space


$$ \begin{bmatrix}0 & -1\\1 & 0\end{bmatrix}\begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}\begin{bmatrix}-1\\2\end{bmatrix}$$

Then, finally, we change it back to our basis. 


$$ \begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}^{-1}\begin{bmatrix}0 & -1\\1 & 0\end{bmatrix}\begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}\begin{bmatrix}-1\\2\end{bmatrix}$$

In general, expressions like $B^{-1}TB$ express a sort of mathematical empathy - a mirror between bases. 


##### Example Transformation

$$B^{-1}TB = \begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}^{-1}\begin{bmatrix}0 & -1\\1 & 0\end{bmatrix}\begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}$$

First, what is the inverse of $B$? We can use Gaussian elimination:

$$\begin{bmatrix}2 & -1 &|& 1 & 0 \\1 & 1 &|& 0 & 1\end{bmatrix}$$

Add row 2 to row 1:

$$\begin{bmatrix}3 & 0 &|& 1 & 1 \\1 & 1 &|& 0 & 1\end{bmatrix}$$

Divide row 1 by 3. Then subtract from row 2:


$$\begin{bmatrix}1 & 0 &|& \frac{1}{3} & \frac{1}{3} \\0 & 1 &|& -\frac{1}{3} & \frac{2}{3}\end{bmatrix}$$

Next, what is $TB$?

$$TB = \begin{bmatrix}0 & -1\\1 & 0\end{bmatrix}\begin{bmatrix}2 & -1\\1 & 1\end{bmatrix}$$

$$TB = \begin{bmatrix}-1 & -1\\2 & -1\end{bmatrix}$$

So, 

$$B^{-1}TB = \begin{bmatrix}\frac{1}{3} & \frac{1}{3} \\-\frac{1}{3} & \frac{2}{3}\end{bmatrix}\begin{bmatrix}-1 & -1\\2 & -1\end{bmatrix}$$

$$B^{-1}TB = \begin{bmatrix}\frac{1}{3} & -\frac{2}{3} \\\frac{5}{3} & -\frac{1}{3}\end{bmatrix}$$


