
- convex function is smiley face

## Multivariable optimization
- Young's theorem: partial derivatives are the same regardless of order; $\frac{\partial f(x,y)}{\partial x \partial y} = \frac{\partial f(x,y)}{\partial x \partial y}$. When you write it that way, it seems a little stupid. 


Second order conditions in two dimensions: more complicated than just checking $f_{xx}$ and $f_{yy}$. Imagine kinimizinga function that's like a taco with the ends pulled down - $x^2 + y^2 + 3xy$. FOC tells us $0,0$; $f_{xx}$ and $f_{yy}$ are both positive. Movement in either the $x$ or $y$ direction is fine - the function is convex. But along the $x = -y$ line the function turns out to be concave! 

So you have to look at $f_{xy}$ also

What we do is create a matrix - a hessian matrix - that lets us keep track of all the partials. 

$$\begin{bmatrix} \frac{\partial f}{\partial x_1 \partial x_1} & \cdots & \frac{\partial f}{\partial x_1 \partial x_n} \\ &\vdots &\\
\frac{\partial f}{\partial x_n \partial x_1}& \cdots & \frac{\partial f}{\partial x_n \partial x_n}\end{bmatrix}$$

These matrices are square and symmetric. We fortunately have many results about what to do with square matrices. 

Take the determinant of this matrix $\det(H)$. $\det(H)$ has to be positive and the diagonal also has to be positive. 

For a maximum, determinant positive and diagonal negative. 

In other words, this is saying that for a minimum the matrix has to be positive semi-definite: $z'Hz > 0$ for all $z$. For a negative, it has to be such that $z'Hz < 0$. 

TODO: demonstrate the equality of these two conditions. #status/section/🚧 

The hessian is a linear transformation - of what??? 


## Constrained Optimization

Basic problem: $\underset{x_1, x_2}{\max} U(x_1, x_2)$ subject to $y = p_1x_1 + p_2 x_2$. Can cheat with saying that $x_1 = (y - p_2x_2)/p_1$, given that this is an equality constraint. Then can just $\underset{x_1}{\max} U(x_1)$ - that gives you an $x_1^*$ which you can use to compute $x_2^*$. 

Fun trick: given cobb douglasy type utility, $x_1^\alpha x_2^\beta$, you can take log of both sides. This makes differentiation easier


Lagrangian: can create a new expression as follows:
$$\mathcal L = x_1 ^\alpha + x_2 ^ \beta  + \lambda(y - p_1x_1 - p_2 x_2)$$

A very useful theorem says that under reasonable conditions, maximizing $\mathcal L$ solves the problem of the constrained optimization 

So we can get FOC: 

$$\begin{align}
0 = \frac{\partial \mathcal L}{\partial x_1}  &= U_1(x_1,x_2) - \lambda p_1 \\
0 = \frac{\partial \mathcal L}{\partial x_2}  &= U_2(x_1,x_2) - \lambda p_2 \\
0 = \frac{\partial \mathcal L}{\partial \lambda}  &= y - p_1 - p_2 \\
\end{align}$$

Then find $x_1^*$ and $x_2^*$ that satisfy this

Hessian: 

$$\begin{align}
\frac{\partial^2 \mathcal L}{\partial x_1^2} &= U_{11}(x_1,x_2) \\
\frac{\partial^2 \mathcal L}{\partial x_2^2} &= U_{22}(x_1,x_2) \\
\frac{\partial^2 \mathcal L}{\partial x_1 \partial x_2} &= U_{12}(x_1,x_2) \\
\end{align}$$

And the second lambda partials are $-p_1$, $-p_2$, $0$. 

So hessian is 

$$\begin{bmatrix}
U_{11} & U_{12} & -p_1 \\
U_{21} & U_{22} & -p_2 \\
-p_1 & - p_2 & 0 \\
\end{bmatrix}$$



## Implicit Function Theorem

reiterate. 

Suppose I have some $f(x, y)$ of endogenous $x$ and exogenous $y$. And I want $x^*(y)$ such that $f(x^*,y) = 0$. Even if I don't know what $y$ is, I can say 

$$\frac{\partial x^*}{\partial y} = \frac{\frac{\partial f}{\partial y}\big|_y}{\frac{\partial f}{\partial x^*}\big|_{x^*,y}}$$
as long as the bottom isn't zero at our point. This is actually intuitive because it reflects that the point of tangency at $f = 0$ is also a min/max which means changing things a bit will either eliminate or duplicate the tangency

$n$-dimensional statement of IFT: Suppose $f: \R^{m+n} \to \R^m$. Interested in solutions where $f(x,y) = 0$. Want solutions where $x \in \R^m$ and $y \in \R^n$. 

Choose $a \in \R^m$ and $b \in \R^n$. Then I can write smth:

$$Df(a,b) = \begin{bmatrix} \frac{\partial f_1}{\partial y_1} & \cdots & \frac{\partial f_1}{\partial y_n } &|& \frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_m }  \\
\vdots & & &|& \vdots  \\
\frac{\partial f_m}{\partial y_1} & \cdots & \frac{\partial f_m}{\partial y_n} &|& \frac{\partial f_m}{\partial x_1} & \cdots & \frac{\partial f_m}{\partial x_m}\end{bmatrix}$$

We can think of this as some sort of block matrix $[Y |X]$ 

We had the condition that the denominator before wasn't zero: in this case, $[X]$ has to be invertible.


Then the theorem is: If $f$ is smooth and $X\inv$ exists then there is a unique continuously differentiable function $g: \R^n \to \R^m$ such that 
$$ \frac{\partial g_i}{\partial y_j} = -X\inv Y$$



## Integration 

### First Fundamental Theorem of Calculus

Let $f:[a,b] \to \R$ be continuous. Let $F(x) = \int_a^x f(t)dt$. 

Then: 
$F()$ is continuous on $[a,b]$, it is differentiable on $(a,b)$, and $F'(x) = f(x) \quad \forall x \in (a,b)$ 


### Second Fundamental Theorem of Calculus
Take $f: [a,b] \to \R$ with antiderivative $F$ (i.e., $f(x) = F'(x) \quad \forall x \in (a,b)$. If $f()$ is integrable on $[a,b]$ then $\int_a^b f(x) dx = F(b) - F(a)$. 

### Integration Rules

$$ \int a \; dx  = ax + c$$
$$ \int x \; dx = \frac{1}{2} x^2 + c$$
$$ \int x^n \; dx = \frac{1}{n+1}x^{n+1} + c$$
$$ \int k f(x) = k \int f(x) $$
$$ \int 1/x \; dx = \ln |x|$$
Integration is linear
$$ \int af(x) + bg(x) \; dx = a \int f(x) \; dx + b \int g(x) \; dx$$
exponent is its own integral

$$ \int a^x \; dx = x \frac{a^x}{\ln a} + c$$
$$ \int \ln x= x \ln x  -  x+ c $$
### Two Integration Tricks

#### $U$-Substitution

Motivating example: 

$$ \int (2x^3 + 1)^7 x^2 dx $$
gross

set $U = 2x^3 + 1$. I see $U'$ sort of floating around: $\frac{\partial U}{\partial x} = 6x^2$, so $\partial U = 6x^2 \partial x$. Then I can say this is the same as 

$$ \frac{1}{6} \int U^7 \; dU$$ so then we can say this is $\frac{1}{6}\frac{1}{8}U^8 + c$ = $\frac{1}{48}(2x^3+1)^8 + c$. 

A general statement:
$$ \int_a^b f(\rho(x))\rho'(x)dx = \int_{\rho(a)}^{\rho(b)}f(U) \;d(U)$ $$


#### Integration by Parts

$$\int UdV = UV - \int VdU$$

$$\int_a^b U(x)V(x)dx = U(x)V(x)\big|_a^b - \int U'(x)V(x)dx$$