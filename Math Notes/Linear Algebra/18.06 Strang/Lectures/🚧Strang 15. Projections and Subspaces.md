---
aliases: 
date updated: Wednesday, August 10th 2022, 10:40 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
creation date: Friday, April 22nd 2022, 6:28 pm
---

[[18.06  Linear Algebra Strang]]

Previewed this last time. We might be interested in finding $\hat x$ which is the best $x$ for a given $Ax = b$ when this has no exact solution. 

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

We can then write out the projecting factor $p$; 
$$p = a \frac{a'b}{a'a}$$ 
```ad-question
title: Trigonometry Digression
collapse: closed

Strang said as an aside there is a $\cos \theta$ here but we don't care. what does he mean?



```
Well - let $\theta$ be the angle between $b$ and $a$ - then 

$$\begin{align}
\cos \theta &= ||e||/||p|| \\
&= ||(b-xa)||/||xa|| \\
&= \sqrt{\frac{(b - xa)'(b-xa)}{(xa')(xa)}}\\
&= \sqrt{\frac{(b' - xa')(b-xa)}{x^2 a'a}}\\
&= \sqrt{\frac{b'b - xa'b - b'xa + xa'xa}{x^2 a'a}}\\
\end{align}$$
