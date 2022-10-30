---
aliases:
creation date: Saturday, October 29th 2022, 3:13 pm
date updated: Sunday, October 30th 2022, 3:24 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Implicit Function Theorem]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Sometimes there are expressions of some form like $F(x,y) = c$ for some function $F$. We are generally used to working with functions of the form $y = f(x)$, and it would be nice to be able to generate this kind of function out of that expression. The IFT describes when and how one might do so. 

## Statement

Suppose $X \subseteq \R^m$ and $Y \subseteq \R^n$; let $F:X \times Y \to \R^n$. Let $F$ be in $C^1$, ie. once differentiable; for some $X^* \in X$ and $y^* \in Y$, let $F(x^*, y^*) =c$. Define $F_Y$ 
$$F_Y = \begin{bmatrix} 
\frac{\partial F_1}{\partial y_1} & \ldots & \frac{\partial F_1}{\partial y_n} \\
& \vdots & \\
\frac{\partial F_n}{\partial y_1} & \ldots & \frac{\partial F_n}{\partial y_n} \\
\end{bmatrix}$$


If $F_Y$ is nonsingular, then there exists some open ball around $x^*$, $B \subseteq X$ and a $C^1$ implicit function $f:B \to Y$ such that
1) $f(x^*) = x^*$
2) $F(x, f(x)) =c$ for all $x \in B$; and 
3) $\frac{\partial f(x)}{\partial x} = F_Y\inv F_X$ where the RHS is a function evaluated at some $x, f(x)$ in our ball.. 


## Intuition

![[Implicit Function Theorem 2022-10-29 15.22.43.excalidraw]]
