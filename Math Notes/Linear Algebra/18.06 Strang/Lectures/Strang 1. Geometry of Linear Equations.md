---
date updated: 2022-03-08 20:20

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 1. Geometry of Linear Equations]]
[[18.06 Strang]]
The fundamental goal of linear algebra - solve systems of linear equations. 

Suppose you have a system of $n$ equations and $n$ unknowns. 

There are a few ways to represent the system. 

##### Row picture

We can start with the 'row' picture. This is what we're used to. Two equations of variables.  

$$
\begin{aligned}2x - y &= 0\\
-x + 2y &= 3\\
\end{aligned}
$$
We can think of each row as a line in $\mathbb{R}^2$. What are all the points that satisfy $2x -y = 0$? What about $-x + 2y =3$? 

Where do these lines meet? $1,2$. This solves both equations. 
Two lines can either meet in one place, overlap, or be parallel. It follows that this system of equations - and indeed any such system - has either one solution, no solutions, or infinitely many. 

##### Column Picture

Suppose the coefficients on $x$ are one vector - $(2,-1)$ - and those on $y$ another - $(-1,2)$. What linear combination of these vectors gets us the result $(0,3)$? 

If the vectors are parallel, and $b$ lies off their line, then we're doomed. Otherwise we are OK.

$$x \left[\begin{matrix}
2 \\ -1
\end{matrix}\right] + 
y \left[\begin{matrix}
-1 \\ 2
\end{matrix}\right]
 = 
\left[\begin{matrix}
0 \\ 3	
\end{matrix}\right]
$$


Draw col 1 and col 2 as vectors. 

![[Pasted image 20220308203534.png]]

If I took all the possible $x$ and $y$ values, I could get any RHS - I could reach anywhere in $\mathbb{R}^2$.


##### Matrix 

The matrix representation is a useful shorthand. Conversely, problems like this in matrix land can be thought of in either the row picture or the column picture. 

$$
\left[
\begin{matrix}
2 & -1 \\
-1 & 2 \\
\end{matrix}
\right]
\left[
\begin{matrix} x \\ y \end{matrix}
\right]
= \left[\begin{matrix} 0 \\ 3 \end{matrix}\right]
$$


##### 3-D Case

Now we can think of a system with 3 unknowns and 3 equations. 

$$\begin{aligned}
2x - y   &= 0 \\
-x + 2y  -z &= -1 \\
 - 3y  -4z &= 4 \\
\end{aligned}$$
Each row defines a plane. There is a unique solution if : two of the planes intersect at a line and the third plane intersects at a point.

If any of the two planes overlap, there are infinite solutions; if they are parallel, none <font color=red>what about if they form a triangular prism?? What's the general form of that case</font>

The column picture: see above. The LHS is a linear combination of 3 vectors, each a 3d vector. 

$$x \left[\begin{matrix}
2 \\ -1 \\ 0 \\ 
\end{matrix}\right] + 
y \left[\begin{matrix}
-1 \\ 2 \\ -3 \\
\end{matrix}\right] + 
z \left[\begin{matrix}
0 \\ -1 \\ 4 \\
\end{matrix}\right]
 = 
\left[\begin{matrix}
0 \\ -1 \\ 4 \\
\end{matrix}\right]
$$


But take a different RHS - eg $[1 \; 1 \; 3]$, eg take 1 of first, one of second, none of third

Now think about all $b$; all possible RHS. Can I solve $Ax = b$ for every $b$? Do the linear combinations of the columns fill 3-D space? 

For the example $A$ above, ans. is yes. It fails if all 3 columns lie in the same plane. eg if col 3 is sum of col 2 and col 1

More generally, problem if any col is linear combo of any of the others. This makes a matrix *singular*.

