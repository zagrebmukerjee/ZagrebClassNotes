What is the sandwich??

let k = 3, N= 5

$$
X'\Sigma X = 
\begin{bmatrix}
x_{1,1} & x_{2,1} & x_{3,1} & x_{4,1} & x_{5,1} \\
x_{1,2} & x_{2,2} & x_{3,2} & x_{4,2} & x_{5,2} \\
x_{1,3} & x_{2,3} & x_{3,3} & x_{4,3} & x_{5,3} \\
\end{bmatrix}
\begin{bmatrix}
\sigma_{1,1} & 0 & 0 & 0 & 0 \\
0 &  \sigma_{2,2} &0 &0 & 0 \\
&& \vdots && \\
0 &0 & 0 & 0  & \sigma_{5,5}\\
\end{bmatrix}X
$$
$$ = 
\begin{bmatrix}
x_{1,1}\sigma_{1,1} & x_{2,1}\sigma_{2,2} \ldots & x_{N,1} \sigma{N,N} \\
\vdots & & \vdots \\
x_{1,k}\sigma_{1,1} & \ldots & x_{N,k}\sigma_{N,N}\\
\end{bmatrix}
\begin{bmatrix}
x_{1,1} & x_{1,2} & x_{1,3} \\
x_{2,1} & x_{2,2} & x_{2,3} \\
x_{3,1} & x_{3,2} & x_{3,3} \\
x_{4,1} & x_{4,2} & x_{4,3} \\
x_{5,1} & x_{5,2} & x_{5,3} \\
\end{bmatrix} = 
$$
$$
\begin{bmatrix}
\sum^N x_{i,1}^2 \sigma_{i,i} &
\sum^N x_{i,1}x_{i,2} \sigma_{i,i} &
\sum^N x_{i,1}x_{i,3} \sigma_{i,i} \\
& \vdots & \\
\sum^N x_{i,3}x_{i,1} \sigma_{i,i} &
\sum^N x_{i,3}x_{i,2} \sigma_{i,i} &
\sum^N x_{i,3}^2 \sigma_{i,i} \\
\end{bmatrix}
$$