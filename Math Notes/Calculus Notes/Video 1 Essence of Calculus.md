---
date updated: 2021-06-17 12:23

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/calculus'
---

#### [[Video 1 Essence of Calculus]]

##### Area of a Circle

We know that the area of a circle is $\pi R^2$, where $R$ is the radius. But why?

 We can envision the circle broken into a set of concentric rings (like the rings of a tree). Then the area of the circle will be the sum of the areas of the rings.
 
 What is the area of the ring located $r$ distance from the center? We can approximate it as a rectangle. We know the width of the rectangle - it is the circumference of the circle inside the ring, $2 \pi r$. Call the height of the rectangle $dr$ - as $dr$ becomes smaller, the area of the rectangle approaches $2\pi r \: dr$. 
 
 Then we can look at all the rectangles for $0 < r < R$, and line them up in increasing order. 
 
Suppose $R$ is $3$ - it would look like this: 

 ![[Pasted image 20210617123020.png]]
 
What is the total area of these rectangles? Together, the tops of the rectangles approximate a line $y = 2 \pi r$. The total area then is the area $A$ under this line - which is a triangle with base $R$, and height equal to the tallest ring's width, $2 \pi R$. 

$$A \approx \frac{1}{2}(R)(2 \pi R) = \pi R^2$$

As $dr$ gets smaller, this approximation gets better and better. 

##### Generalizing 

This general form of problem - an accumulation of some changing $f(x)$ - has many applications. 

Given a car's changing velocity $v(t)$, how far has it  travelled at time $t$? |
------------ | 
At time $t$, and in a given window of time $dt$, it travels about $v(t) dt$. Once again, if $v(t)$ were a curve, this would be the area under the curve, approximated by rectangles. And as $dt$ - the rectangles' base - gets smaller, the approximation approaches the real area.  |

So what's the area under a parabola $f(x) = x^2$? 

Again, we can draw a bunch of little rectangles under the parabola. Let the function $A(x)$ be the sum of these rectangles between $0$ and $x$. $A(x)$ is an _integral_ of $x^2$ 

As $x$ increases by $dx$, $A$ increases by $dA$. As $dx \to 0$, $dA \to x^2 dx$ - by the same rectangle logic as before. So:

$$\frac{dA}{dx} = x^2 = f(x)$$

We can call $\frac{dA}{dx}$ the _derivative_ of $A$ with respect to $x$. So the derivative of the integral is the function itself! ^[ignoring constants] This is the _Fundamental Theorem of Calculus_:

$$\frac{d}{dx} \int f(x)dx= f(x)$$

Another definition of the derivative - consider a very small number $\epsilon$. Then, 

$$\lim_{\epsilon \to 0} \frac{A(x+\epsilon) -A(x)}{\epsilon} = x^2$$

The derivative is like a measure of how sensitive a function is to changes in inputs (see [[Chaos Theory#Sensitive Dependence]] for a related concept).  

Hopefully we will go on to determine how to find all of these things.
