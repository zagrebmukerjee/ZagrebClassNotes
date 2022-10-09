---
aliases:
- "Convergence in Probability"
- "Convergence in Distribution"
creation date: Sunday, October 9th 2022, 11:00 am
date updated: Sunday, October 9th 2022, 12:00 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/theory'
- '#topics/methods'
---

# [[Econometrics VIIa - Convergence in Probability and Distribution]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


Define two forms of convergence that are useful for characterizing sample behavior. 

## Convergence in Probability

Suppose a sequence of random variables $X_n$, and a constant $c$. Then we can say that $X_n$ <font color=gree>converges in probability</font> to $c$ if, for all $\epsilon$, 

$$\lim_{n\to \infty} P(|X_n - c| > \epsilon) = 0 $$
Equivalently, 

$$\lim_{n\to \infty} P(|X_n - c| < \epsilon) = 1 $$

Notation: if $X_n$ converges in probabilty to $c$ we can say
$$\begin{align}
X_n \to_p c\\
\underset{n \to \infty}{\text{plim}} X_n = c
\end{align}$$
