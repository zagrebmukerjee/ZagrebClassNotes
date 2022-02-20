---
date updated: 2021-06-22 21:09

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
---

### [[Video 3 Derivative Formulas Through Geometry]]
Part of [[@Review of Calculus Index]]


#### Geometric Derivatives of Polynomials

Let's say $x^2$ is a square with side length $x$. We are interested in the change in the area $dA$ if we change the side-length by a small amount $dx$. 
![[Pasted image 20210622222457.png]]

We're interested in the cumulative area of the yellow shapes. We can write:

$$\begin{array}{cl}
dA &=& xdx + xdx + dx^2 \to 2xdx \\
\frac{dA}{dx} &=& 2x \\
\frac{d}{dx}x^2 &=& 2x
\end{array}$$

We can extend this reasoning to a cube with side $x$: 

![[Pasted image 20210622222916.png]]

We want to find $dV$, the change in volume. Once more, we sum up all the yellow shapes. The large prisms on the sides have sides $x, x$ and $dx$; the long ones have sides $x, dx, dx$ and the small cube has $dx, dx, dx$. So:

$$\begin{array}{cl}
dV &=& 3x^2dx + 3xdx^2 + dx^3 \to 3x^2\\
\frac{d}{dx}x^2 &=& 2x
\end{array}$$

Note the symmetry between this and the algebraic definition of the derivative.  We can redescribe the $x^2$ problem as the difference between two areas- a square with side-length $x + dx$ and a square with side-length $x$.  So we have 

$$\begin{array}{cl}
dA &=& (x+dx)^2 - x^2\\
\frac{dA}{dx} &=& \frac{f(x+dx) - f(x)}{dx}\\
\end{array}$$
where $f(x)= x^2$. 


This generalizes to any polynomial:

$$ \frac{d}{dx} x^n = nx^{n-1}$$

```ad-info
title: Algebraic Derivation of the above
collapse:true

![[Digression - properties of derivative algebraically#Derivative of powers of x]]

```

As another excercise, one could extend this reasoning to the square with side-length $1/x$ to derive the change in $x$ as $1/x$ changes - a backwards way of getting $\frac{d}{dx} 1/x$.

#### Geometric Derivative of $\sin(x)$

We are interested in $\frac{d}{d\theta} \sin{\theta}$. 

We can find this by exploiting properties of the unit circle. 

For any given point on the circle, that point can be described by an angle $\theta$ from the x-axis. We can drop a line to the x-axis from this point, and - with the x-axis and the radius - this forms a triangle.


Let the height of this triangle be $h$. We know that $\sin \theta$ is the opposite over the hypotenuse:

$$ sin\theta = \frac{O}{H} = \frac{h}{1} = h$$

So the height of this triangle is $\sin \theta$ (similarly, the base is $\cos \theta$). 
![[Pasted image 20210622230108.png]]

So how does this height change with a change in $\theta$? For small enough $d\theta$ we can approximate the subtension of theta as a line. Then we can make a triangle:

![[Pasted image 20210622230207.png]]

This triangle is similar to the larger triangle. So we know the ratio of $d \sin \theta$ to $d\theta$ is the same as the ratio of the base of the bigger triangle - i.e. $\cos \theta$ - to its hypotenuse, $1$. Thus
$$ d \sin \theta = \cos \theta d \theta$$
$$ \frac{d \sin \theta}{d \theta} = \cos\theta$$