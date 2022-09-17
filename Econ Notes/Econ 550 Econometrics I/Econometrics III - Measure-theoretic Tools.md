---
aliases:
creation date: Saturday, September 17th 2022, 10:16 am
date updated: Saturday, September 17th 2022, 12:42 pm

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
A <font color=gree>simple function</font> is a function that takes on at most a finite number of values. We will first define the integral for simple functions, then for nonnegative functions - approximated with simple functions from below - then for all functions, which can be transformed into nonnegative. 

Suppose simple $f(x)$ on measure space $M, \mathcal M, \mu$. Then $f(x) = \sum_{j=1}^J c_j 1_{Aj}(x)$ with $1$ being an indicator for $A_j \in \mathcal M$ and disjoint. This is expressing that any finite valued functions can be expressed as a set of disjoint 'bars'. 

Then the Lebesgue integral with respect to measure $\mu$ is simply 
$$ \int f \,d\mu = \sum_{j=1}^J c_j \mu( A_j)$$
In the case where $\mu = \lambda$, the Lebesgue measure, this becomes the finite sum of the area of the bars under this graph - the R-integral of $f$

```ad-info
title: Alternative Notation

The integral can be written also as:
$$ \int f(x) d\mu(x)$$
$$ \int f(x) \mu(dx)$$
```

Then, for a non-negative $f$, I can write 
$$\int f(x) d\mu = \sup_{s} \int s d\mu$$
where $s$ is a set of simple functions such that $0 \leq s(x) \leq f(x)$. 

For general functions, we can decompose them into $f = f_+ - f_-$, where $f_+ = \max(f(x), 0)$ and $f_- = \max(-f(x),0)$. Then do the above for each. $f$ is integrable if each of $f_+$ and $f_-$ are integrable, and then add them. This doesn't work if both are $\infty$. Or if both are $-\infty$. 

#### Equivalence

Consider $f$ that's Riemann-integrable - nonnegative for simplicity. let $s$ be a set of simple functions as before, and $\lambda$ the L-measure. Note that every 'rectangle' $\pi$ can be made a simple function $s$. Then 
$$\int f(x) d\lambda = \sup_s \int s(x) d\lambda \geq \sup_{\pi} L(f, \pi)$$
The other direction can also be shown <font color=#F7B801>left to reader </font>


#### Integer Functions

Let $M = \mathbb Z^+$, $\mathcal M$ the power set of $M$. and $\mu$ the counting measure. Let $f(x)$ be nonnegative on $\mathcal M$ st $\sum f(x) < \infty$. Then, we can create ismple functions: 

$$s(x) = s_A(x) = \begin{cases} c_x &\text{ for some } 0 \leq c_x \leq f(x) \text{ where } x \in A \\ 
0 &\text{ otherwise}
\end{cases}$$
Then I can simply say that 

$$ \int f(x) d\mu = \sup_s \int s d\mu = \sup_s \sum c_x \mu(x) = \sup_s \sum c_x$$
which latter tends to $\sum f(x)$, our desired value. This wouldn't be possible with the riemann integral. Note that this makes the linearity of the L-integral of discrete functions pretty obvious. 

We could use $\mu$ as the probability mass function of some discrete $RV$ that takes on values $f(x)$. Then this would be the <font color=gree>expectation</font>, or <font color=gree>expected value</font>. 

## Integrability 



Monotone