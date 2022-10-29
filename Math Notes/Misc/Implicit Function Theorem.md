---
aliases:
creation date: 2022-10-29 15:13
date updated: 2022-10-29 15:13

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Implicit Function Theorem]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Sometimes there are expressions of some form like $F(x,y) = c$ for some function $F$. We are generally used to working with functions of the form $y = f(x)$, and it would be nice to be able to generate this kind of function out of that expression. The IFT describes when and how one might do so. 

Suppose $X \subseteq \R^m$ and $Y \subseteq \R^n$; let $F:X \times Y \to \R^n$. Let $F$ be in $C^1$, ie. once differentiable; for some $\bar x \in X$ and $\bar y \in Y$, let $F(\bar x, \bar y) =c$. 

Write 
$$F_Y = \begin{bmatrix} 
\frac{\partial F_1}{\partial y_1} \\
\frac{\partial F_1}{\partial y_1} 
\end{bmatrix}$$


If $F_Y$ is nonsingular
