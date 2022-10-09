---
aliases:
- "Convergence in Probability"
- "Convergence in Distribution"
creation date: Sunday, October 9th 2022, 11:00 am
date updated: Sunday, October 9th 2022, 12:56 pm

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

### Definitions

Suppose a sequence of random variables $X_n$, and a constant $c$. Then we can say that $X_n$ <font color=gree>converges in probability</font> to $c$ if, for all $\epsilon$, 

$$\lim_{n\to \infty} P(|X_n - c| > \epsilon) = 0 $$
Equivalently, 

$$\lim_{n\to \infty} P(|X_n - c| < \epsilon) = 1 $$

Notation: if $X_n$ converges in probabilty to $c$ we can say
$$\begin{align}
X_n \to_p c\\
\plim{n\to\infty} X_n = c
\end{align}$$

### Property 1
Suppose $\plim{n \to \infty} Y_n = c$. Then for some constant $b$, 
$$ \plim{n\to\infty} bY_n = bc$$
#### Proof:
We know that for any $\epsilon$, $\lim_{n\to \infty} P(|X_n - c| > \epsilon) = 0$. It follows that $\lim_{n\to \infty} P(|X_n - c| > \epsilon/|b|) = 0$; which means that $\lim_{n\to \infty} P(|bX_n - bc| > \epsilon) = 0$. This doesn't work for $b=0$ but then the result is trivial. 

### Property 2

Suppose $\plim{n \to \infty} X_n = a$ and $\plim{n \to \infty} Y_n = b$. Then 

$$ \plim{n \to \infty} X_n + Yn = a + b$$
#### Proof:

Recall triangle inequality: $|a + b| \leq |a| + |b|$. 
If $a + b > c$, then either $a > c/2$ or $b> c/2$ (or both). 
$$\begin{align}
P(|X_n + Y_n - a - b| > \epsilon) &= P(|X_n - a + Y_n - b| > \epsilon)\\
&\leq P(|X_n - a| + | Y_n - b| > \epsilon) \\ 
&\leq P(|X_n - a| > \epsilon/2 \lor | Y_n - b| > \epsilon/2) \\
&\leq P(|X_n - a| > \epsilon/2) + P( | Y_n - b| > \epsilon/2) \\
&\to 0 \text{ as } n \to \infty
\end{align}$$
### Property 3
If $\plim{n \to \infty} Y_n =c$ and $\plim{n \to \infty} X_n = d$ 
then 
$$ \plim{n\to\infty} X_n Y_n = cd $$
$$ \plim{n\to\infty} X_n/Y_n = c/d $$ the latter only if $d \neq 0$

Proof: this follow