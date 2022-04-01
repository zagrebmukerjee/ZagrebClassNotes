---
date updated: 2022-03-08 20:20

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
---

# [[Strang 1. Geometry of Linear Equations]]
Part of [[@Review of Linear Algebra Index]]

Fundamental goal of linear algebra - solve systems of linear equations. 

Suppose a system of $n$ equations and $n$ unknowns. 

Start with the 'row' picture. 1 equation at a time
Then the 'column' picture. new, but important.

Combine those into the 'matrix' form using matrix A

### Linear Equations

##### Row picture

2x - y = 0
-x + 2y = 3

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

The 'row' picture. What are points in xy plane that solve the first row equation? e.g. 0,0; 1,2; and a straight line through them

Second eqn: -3,0; -1,1 then a line. 

Where do these lines meet? 1,2. Solves both equations. Necessarily a unique solution - unless parallel

##### Column Picture

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

Combine these two vectors in the right amount to get the result. i.e. we want to find the right linear combination of the columns that creates the RHS

So draw col 1 and col 2 as vectors. 

![[Pasted image 20220308203534.png]]

If I took all the possible $x$ and $y$ values - you can get any RHS. we will return to this


##### 3 dimensional 



Columns: 
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


The row picture: we have 3 equations, that makes 3 planes. A unique soln. Unless two are parallel ? or constituent lines of the planes are parallel?

The column picture: see above. The LHS is a linear combination of 3 vectors, each a 3d vector. 


But take a different RHS - eg $[1 \; 1 \; 3]$, eg take 1 of first, one of second, none of third


Now think about all $b$; all possible RHS. Can I solve $Ax = b$ for every $b$? Do the linear combinations of the columns fill 3-D space? 

For the example $A$ above, ans. is yes. It fails if all 3 columns lie in the same plane. eg if col 3 is sum of col 2 and col 1

More generally, problem if any col is linear combo of any of the others. These are _singular_ matrices


