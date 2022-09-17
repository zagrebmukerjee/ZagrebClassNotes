---
aliases:
creation date: Saturday, September 17th 2022, 10:16 am
date updated: Saturday, September 17th 2022, 10:23 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/theory'
- '#types/classes/math/measure'
- '#topics/methods'
---

# [[Econometrics III - Measure-theoretic Tools]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

## Riemann Integral
Largely reminders. <font color=gree>Riemann integral</font> (R-integral) is the area under the curve. Let $f$ be on a bounded interval $[a,b] \in \R$. Choose $\pi =\{a= x_0, \ldots, x_K = b\}$ such that $\pi$ generates a partition of $[a,b]$ into a countable number of intervals. Then we can define:

$$\begin{align}
L(f, \pi) = \sum_{k=1}^K \inf \{ f(x): x\in [x_{k-1}, x_k] \cdot (x_k - x_{k-1} \}\\
U(f, \pi) = \sum_{k=1}^K \sup \{ f(x): x\in [x_{k-1}, x_k] \cdot (x_k - x_{k-1} \}\\
\end{align}$$

Then define the Riemann integral: 

$$\int_a^b f(x) dx = \sup_\pi L(f,\pi) = \inf_{\pi} U(f, \pi)$$
that is to say, when $L$ and $U$ are equal, the integral is either of them. 



## Lebesgue Integral
### Motivation

Not all functions are integrable. Consider the function $f(x)$ on $[0,1]$ that is $1$ if $x$ is irrational and $0$ otherwise. Intuitively we want this to be $1$, since $x$ is irrational 'almost everywhere' in $[0,1]$. But any interval $x_{k-1}, x_k$ contains both rationals and irrationals. So the $\inf$ is stuck at $0$, the $\sup$ at $1$, and the interal is not defined. 

The Lebesgue integral (L-integral) is a generalization of the R-integral. There are several reasons we want it: 
- Crucially the L integral allows for weighting by any measure (including the probability measures) - while the R integral is limited to the Lebesgue measure. 
- All R-integrable functions are L-integrable, but not vice versa - when both exist they are the same
- Can Lebesgue-integrate over basically arbitrary sets. 

### Definition
#### Simple Functions
A simple function is a finite-valued function