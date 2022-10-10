---
aliases:
- "Convergence in Probability"
- "Convergence in Distribution"
creation date: Sunday, October 9th 2022, 11:00 am
date updated: Monday, October 10th 2022, 1:42 pm

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

Proof: this follows from the Slutsky theorem. 


## Slutsky Theorem

Suppose $Y_n \to_p c$, a constant, as $n \to \infty$. Suppose some function $h()$ is continuous at $c$. Then
$$ h(Y_n) \to_p h(c)$$
This is a very useful result. For instance, I have shown that the [[Econometrics VII - Sampling|Sample Variance]] converges in probability to the population variance. Does the sample standard deviation converge to the population sd? I could prove that too; or I could use Slutsky's theorem, observe that $\sqrt{x}$ is continuous for $x \geq 0$, and then get this result for much less work.

This result can be generalized to vector-valued functions, with length $|| \cdot ||$ replacing the absolute value. 

#### Proof
Proof relies on using continuity to squeeze $h(Y_n)$ and $h(c)$ together. 

We want to show that, for any epsilon,
$$ \lim_{n \to \infty} P(|h(Y_n) - h(c)|< \epsilon) = 1$$
$h$ is continuous at $c$: so, for any $\epsilon > 0$, there is some $\delta > 0$ such that $|a - c| <\delta \implies |h(a) - h(c)| < \epsilon$. But the fact that $Y_n \to_p c$ means that $\lim_{n\to\infty} P(|Y_n - c| <\delta) = 1$. So $P(|h(Y_n) - h(c)| < \delta) = 1$. 
