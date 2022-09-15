---
aliases:
creation date: Thursday, September 15th 2022, 1:41 pm
date updated: Thursday, September 15th 2022, 1:45 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
---

# [[Micro Theory IIc - Hemicontinuity]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

We are concerned now with correspondences, which can map $x$ to some set of $y$s. Intuitively that corresponds to flat regions on indifference curves. 

## Upper Hemicontinuous
Suppose a correspondence $f: X \to Y$. Suppose $f(x) \subseteq$ some compact subset of $Y$. As a heuristic, I say that $f$ is hemicontinuous if the graph of $f$ is a closed set. That means:
- For any convergent sequence $x_n \in X: x_n \to x$, and 
- if there is $y_n \in f(x_n)$ that converges to $y$; then
- $y \in f(x)$. 

Intuitively, imagine the correspondence given by $f(x) = [x, x+1)$. Suppose $x_n = 1 - 1/n$. This converges to $1$. Then $f(x_4)$ will be $[3/4, 7/4)$. Choose $y_n$ as $2-2/n$. Then $y_4 = 2 - 2/4 = 3/2 \in f(x_4)$. It's apparent that $y_n$ converges to $2$ , but $2$ is not in $f(1)$. 
