---
aliases:
- "Mean Value Expansion"
creation date: Thursday, November 17th 2022, 1:12 pm
date updated: Thursday, November 17th 2022, 1:21 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mean Value Theorem]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Mean Value Theorem

Suppose $f()$ continuous on $[a,b]$, and differentiable on $(a,b)$. 
Then there exists some $c \in (a,b)$ such that:

$$f'(c) = \frac{f(a)-f(b)}{a-b}$$
In other words: we can approximate $f$ on this interval iwth a line going from $a, f(a)$ to $b, f(b)$. That line has slope $f(a) - f(b)/(a-b)$. There's some point where the derivative of $f$ is parallel to that approximation. 

![[Mean Value Theorem 2022-11-17 13.15.08.excalidraw|300]]

## Mean Value Expansion

Suppose I know that $f(x) = k$, but I don't know $y$. I can say:
$$\begin{align}
\exists c: f'(c) &= \frac{f(x) - f(y)}{x-y}\\
(x-y)f'(c) &= k - f(y)\\
k &= (x-y)f'(c) + f(y)\\
\end{align}$$

I might be more able to examine $f'(c)$ than $f(y)$. 
