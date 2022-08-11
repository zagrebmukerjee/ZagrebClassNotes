---
aliases: 
tags: 
creation date: Thursday, August 11th 2022, 1:10 pm
date updated: Thursday, August 11th 2022, 1:56 pm
---

![[Pasted image 20220811131122.png]]

$$ \lim_{h \to 0} \frac{(a(x+h)^2 + c) - (ax^2 + c)}{h}$$
$$ \lim_{h \to 0} \frac{ax^2+2ahx + ah^2 + c - ax^2 + c}{h}$$
$$ \lim_{h \to 0} \frac{2axh + h^2}{h}$$
Already we can see that $c$ falls out. Factoring gives us $2ax + h$ which approaches $2ax$.


![[Pasted image 20220811131534.png]]

a) $15x^4 + 12x^2 - 14x$
b) $5x + 5^x\ln 5 + 5$
c)$1/3(e^x + x)(e^x + 1)$
d) 
$$\begin{align}
\frac{d}{dx} [x^3 -1]\inv[x^3 + 1] &= (x^3-1)\inv [d/dx (x^3+1)] + [d/dx (x^3 -1)\inv](x^3 + 1) \\
&= 3x^2(x^3-1)\inv -(x^3 -1)^{-2}(3x^2)(x^3 + 1) \\
&= 3x^2\left[\frac{x^3 -1 }{(x^3 - 1)^2} - \frac{x^3 + 1}{(x^3 - 1)^2}\right]\\
&= \frac{-6x^2}{(x^3-1)^2}
\end{align}$$

e) Interpreting this: 

$$\begin{align}
\frac{d}{dx} \ln \left[(x^4 + 1)(x^4 -1)\right]^\frac{1}{2} &= \frac{1}{2}\frac{d}{dx} \left[\ln (x^4 + 1) + \ln(x^4 -1)\right]\\
&= \frac{1}{2}\left[4x^3/(x^4 + 1) + 4x^3/(x^4-1) \right]
\end{align}$$
f) $3x^2e^{4x^2} + 8x^4e^{4x^2}$


![[Pasted image 20220811134301.png]]

a) First derivative is $x^2 -12$, and second is $2x$. 
Increasing where $x^2 > 12$, or where $|x|>\sqrt{12}$. Flat at those places. Decreasing elsewhere. 

Convex when x > 0 concave when x < 0
Local minimum when $x = \sqrt{12}$ and maximum when $x = - \sqrt{12}$. 

b)
First derivative is $1 - \frac{1}{x^2} = \frac{x^2 -1 }{x^2}$
Decreasing with $x <0$ increasing $x >0$ undefined at $0$. Neither minima nor maxima

Second derivative is $2x^{-3}$ which has the same sign as $x^3$; so concave left of x and convex right of x

c)
First derivative is $e^{2x}(1 + 2x)$ . This is zero when $x = -1/2$. Function increases when $x > -1/2$. Decreases when $x < -1/2$. $0$ there. 

Second derivative is $2e^{2x} + 2[e^{2x} + 2xe^{2x} ] = 4e^{2x}(1+ x)$ so the inflection point is $-1$ . Positive above, negative below. Means $-1/2$ is a minimum 
