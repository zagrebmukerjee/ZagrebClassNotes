---
aliases:
- 'Product Rule'
- 'Quotient Rule'
- 'Power Rule' 
- 'Chain Rule'
creation date: Friday, April 14th 2023, 10:37 am
date updated: Friday, April 14th 2023, 11:09 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/calculus'
- '#status/🚧'
---

# [[Derivative Rules]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>



Various shorthands for computing the derivatives of combinations of differentiable functions. For geometric intuition see [[Video 4 Visualizing the Chain Rule and Product Rule]].

## Derivative of a Power

$$\frac{d}{dx} x^a = ax^{a-1}$$


### Proof
#status/section/🚧

## Derivative of an Exponential

$$ \frac{d}{dx} e^x = e^x $$
### Proof

From the definition of the derivative, and the property that $\lim_{t \to 0} (a^t-1)/t = \ln a$. 
$$\begin{align}
\frac{d}{dx} e^x &= \lim_{t \to 0} \frac{e^{x + t} - e^x}{t}\\
&= e^x\lim_{t \to 0} \frac{(e^t-1)}{t}\\
&= e^x \ln(e)\\
&= e^x\\
\end{align}$$
## Derivative of a Product

$$ \frac{d}{dx}[f(x)g(x)] = f'(x)g(x) + g'(x)f(x)$$
### Proof
$$\begin{align}
\frac{d}{dx}[f(x)g(x)] &= \lim_{t \to 0} \frac{f(x+t)g(x+t) - f(x)g(x)}{t} \\
&=  \lim_{t \to 0} \frac{1}{t}\left[f(x+t)g(x+t) - f(x)g(x) - f(x)g(x+t) + f(x)g(x+t) \right]\\
&=  \lim_{t \to 0} \left[\frac{[f(x+t)-f(x)]g(x+t)}{t} +  \frac{[g(x+t) - g(x)]f(x)}{t} \right]\\
&=  \lim_{t \to 0} \left[\frac{[f(x+t)-f(x)]g(x+t)}{t}\right] + f(x)g'(x)\\
&=  \lim_{t \to 0}g(x+t)\lim_{t \to 0} \left[\frac{[f(x+t)-f(x)]}{t}\right] + f(x)g'(x)\\
&=  g(x)f'(x) + f(x)g'(x)\\
\end{align}$$

## Derivative of Compositions

$$f(g(x)) = g'(x)f'(g(x))$$

### Proof

#status/section/🚧 

## Derivative of a Quotient

### Proof

A variety of proofs. Easiest one is by application of the Product Rule, Chain Rule, and Power Rule: 
$$\begin{align}
\frac{d}{dx} \frac{f(x)}{g(x)} &= \frac{d}{dx} f(x)[g(x)]\inv\\
&= f(x) \left[ \frac{d}{dx}(g(x))\inv\right] + (g(x))\inv f'(x)\\
&= - f(x) g'(x)g(x)^{-2} + g(x)\inv f'(x)\\
&= - f(x) g'(x)g(x)^{-2} + g(x)^{-2} f'(x)g(x)\\
&= \frac{f'(x)g(x) - g'(x)f(x)}{(g(x))^2}
\end{align}$$

## Derivative of Inverse Functions

$$\frac{d}{dx} f\inv(x)=  \frac{1}{f'(f\inv(x))} $$

### Proof
$$\begin{align}
x &= f(f\inv(x))\\
\frac{d}{dx} x &= \frac{d}{dx} f(f\inv(x))\\
1&= [f^{-1'}(x)]f'(f\inv(x))\\
f^{-1'}(x) &= \frac{1}{f'(f\inv(x))}
\end{align}$$
