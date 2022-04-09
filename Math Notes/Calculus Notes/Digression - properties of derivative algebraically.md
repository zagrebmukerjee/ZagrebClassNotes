---
date updated: 2021-06-18 13:13

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/calculus'
---

### [[Digression - properties of derivative algebraically]]

In [[Video 2 Paradox of the Derivative|Video 2]] we found the derivative of $s(t) = t^3$, $\frac{ds}{dt} = 3t^2$. We found this by expanding out the fraction $\frac{s(t + dt) - s(t)}{dt}$, then dropping all the $dt$ terms.  What else can we extract from this function for univariate derivatves?

#### Derivative of a sum:

Suppose $h(x) = f(x) + g(x). 

$$
\begin{array}{} 
\frac{d}{dx}h(x) &=& \frac{h(x + dx) - h(x)}{dx}\\
&=&\frac{f(x + dx) + g(x + dx) - f(x) - g(x)}{dx} \\
&=& \frac{f(x+dx) -f(x)}{dx} + \frac{g(x+dx) -g(x)}{dx}
\end{array}$$

The derivative of the sum of two functions is the sum of the derivative. 

#### Derivative of powers of $x$

Suppose $f(x) = x^n$. Then

$$\begin{array}{} 
\frac{d}{dx}f(x) &=& \frac{f(x + dx) - f(x)}{dx}\\
&=& \frac{(x + dx)^n - x^n}{dx}\\
\end{array}$$

As in the $s(t) = t^3$ case above, we are only interested in the terms with $dx^k$ where $k<2$, since the rest (after dividing by $dx$) drop out. The first term $x^n$ also drops out. Only the $x^{n-1}dx$ term remains - which becomes $x^{n-1}$. The binomial theorem tells us the coefficient on the remaining term $\binom{n}{1}$, which is $n$. So we have 

$$ \frac{d}{dx}f(x) = nx^{n-1}$$

With these two tools, we can differentiate a polynomial of any order. 

#### Derivative of product of functions

Suppose $h(x) = f(x)g(x)$ where $f$ and $g$ are differentiable. 

$$
\begin{array}{} 
\frac{d}{dx}h(x) &=& \frac{h(x + dx) - h(x)}{dx}\\
&=&\frac{f(x + dx)g(x + dx) - f(x)g(x)}{dx} \\
&=&\frac{f(x + dx)g(x + dx) + f(x)g(x + dx) - f(x)g(x+dx)- f(x)g(x)}{dx} \\
&=&\frac{f(x + dx)g(x + dx) - f(x)g(x+dx) + f(x)g(x + dx)- f(x)g(x)}{dx} \\
&=&\frac{g(x + dx)(f(x + dx) - f(x)) + f(x)(g(x + dx)- g(x))}{dx} \\
&=&\frac{g(x + dx)(f(x + dx) - f(x))}{dx} + \frac{f(x)(g(x + dx)- g(x))}{dx} \\
&=&g(x + dx)\frac{df}{dx} + f(x)\frac{dg}{dx} \\
\end{array}$$

Since differentiable functions are continuous, the last step uses the definition of continuity to find that as $dx \to 0$, $g(x+dx) \to g(x)$. Thus:

$$\frac{d}{dx} f(x)g(x)=g(x)\frac{df}{dx} + f(x)\frac{dg}{dx} $$

#### Derivative of Quotient of Functions

Suppose $h(x) = \frac{f(x)}{g(x)}$ where $f$ and $g$ are differentiable. 

$$\begin{array}{} 
\frac{d}{dx}h(x) &=& \frac{h(x + dx) - h(x)}{dx}\\
&=& \frac{\frac{f(x + dx)}{g(x + dx)} - \frac{f(x)}{g(x)}}{dx} \\
&=& \frac{f(x+dx)g(x) - f(x)g(x+dx)} {g(x+dx)g(x)dx} \\
&=& \frac{1}{g(x+dx)g(x)} \frac{f(x+dx)g(x) - f(x)g(x+dx)} {dx} \\
&=& \frac{1}{g(x+dx)g(x)} \frac{g(x)(f(x+dx)  - f(x)) +f(x)(g(x) - g(x+dx))} {dx} \\
&=& \frac{1}{g(x+dx)g(x)} (g(x)\frac{df}{dx} + f(x)\frac{dg}{dx})
\end{array}$$

Once again we use the continuity hypothesis to say that as $dx \to 0$, $g(x+dx) \to g(x)$:

$$\frac{d}{dx}\frac{ f(x)}{g(x)}=\frac{g(x)\frac{df}{dx} + f(x)\frac{dg}{dx}}{g(x)^2}  $$