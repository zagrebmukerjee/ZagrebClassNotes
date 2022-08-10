---
aliases: 
creation date: Friday, April 22nd 2022, 6:28 pm
date updated: Wednesday, August 10th 2022, 10:54 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 15. Projections and Subspaces]]

[[18.06 Linear Algebra Strang]]



Previewed this last time. We might be interested in finding $\hat x$ which is the best $x$ for a given $Ax = b$ when this has no exact solution. 

### Intro to Projection

We will start by projecting a vector $b$ onto a line $a$ - the span of a single vector. 

Diagram:

![[Strang 15 Fig 1]]

We want to find the point on the line $a$ that is closest to $b$. The vector along $a$ that ends at this point is the projection $p$. By definition this is some multiple of $a$, $p = xa$. How do we find this?

We have a crucial insight: the distance $e$ (for error) between $b$ and $p$ is orthogonal to $a$. <font color=#F7B801>is this obvious?? am I being stupid? you can show this with triangle inequality</font>

So we can write this: 
$$ a' (b - p) = 0 \qquad a'(b-xa) = 0$$
Since we know $a$ and $b$, this is enough! We can solve it out

$$\begin{align}
0 &= a'(b-xa) \\
&= a'b - a'xa \\
&= a'b - x a'a \\
x &= a'b/a'a \\
\end{align}$$

<font color=#F7B801>looks familiar!</font>

Note that we're using the fact that $x$ and $a'a$ are scalars. 

We can then write out the projecting factor $P$ that turns $b$ into $p$; 
$$P = \frac{a  a'}{a'a}$$ 
```ad-question
title: What does he mean when he says this has $\cos \theta$
collapse: closed

Strang said as an aside there is a $\cos \theta$ here but we don't care. what does he mean?


Well - let $\theta$ be the angle between $b$ and $a$ - then 

$$\begin{align}
\cos \theta &= ||e||/||p|| \\
&= ||(b-xa)||/||xa|| \\
&= \sqrt{\frac{(b - xa)'(b-xa)}{(xa')(xa)}}\\
&= \sqrt{\frac{(b' - xa')(b-xa)}{x^2 a'a}}\\
&= \sqrt{\frac{b'b - xa'b - b'xa + x^2a'a}{x^2 a'a}}\\
\end{align}$$

what does this do?? except that it's our first-order condition


```

In a general sense this $p$ is a <font color=gree>Projection Matrix</font>. 

It has size $n \times n$. 
It's also symmetric.

The column space/rank of $P$ is the same as the column space/rank of $a$. (in other words, for any $xa$ there exists a $b$ such that the projection of $b$ onto the $a$ space is $xa$). 

What happens if you project twice?  Intuitively we can say that $PPb = Pb$ because $Pb$ is already projected. Algebraically: 

$$PP = \frac{aa'}{a'a} \frac{aa'}{a'a} = \frac{(aa')(aa')}{(a'a)(a'a)} = \frac{a(a'a)a')}{(a'a)(a'a)} = \frac{aa'}{a'a} = P$$
This means $P$ is <font color=gree>idempotent</font> - $P^n = P$. 



### Projection onto Subspaces

OK so why project? 

$Ax = b$ maybe has no solution. We want to find the most solution-like $\hat x$. In other words, we want to look at all the $\hat x \in C(A)$ - all of the $Ax$ - and find the one closest to $b$. This is the projection problem. 

![[Strang 15 Fig 2]]

First we can define the plane: we can do this with two independent vectors $a_1$ and $a_2$ that span $a$. 

The plane is the column space of a matrix then: $A = \begin{bmatrix} a_1 & a_2 \end{bmatrix}$
Then $p$ is some $\hat x_1 a_1 + \hat x_2 a_2$ which means we can say $p = A \hat x$. So the same problem arises: solve for $\hat x$. 

We can use the same idea: the error $e$ is orthogonal to both of our basis vectors: 
$$\begin{align}
a_1'(b - A\hat x) &= 0 \\
a_2'(b - A\hat x) &= 0 \\
\end{align}$$
We can then just write this as a matrix product
$$\begin{align}
0 &=  A' (b - A\hat x)\\
&= A'b - A'A\hat x\\
A'A \hat x &= A'b \\
\hat x &= (A'A)\inv A'b\\
\end{align}$$

<font color=#F7B801>hoo hoo hoo</font>

$e$ is in the left null space of $A$. 