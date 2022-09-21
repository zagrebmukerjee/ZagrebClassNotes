---
aliases:
creation date: Saturday, September 17th 2022, 10:16 am
date updated: Wednesday, September 21st 2022, 2:59 pm

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

For general functions, we can decompose them into $f = f_+ - f_-$, where $f_+ = \max(f(x), 0)$ and $f_- = \max(-f(x),0)$. Then do the above for each. $f$ is integrable if each of $f_+$ and $f_-$ are integrable, and then take $\int f_+ - \int f_-$. This doesn't work if both are $\infty$. Or if both are $-\infty$. 

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

If for almost all $x$, $f_n(x) \to f(x)$, then is it true that $\int f_n d\mu \to \int f d\mu$? It would be nice to know this so we can take a shortcut to integrating nonnegative functions. Doing some sort of $\sup_s \int s d\mu$ for all $s$ would be tedious; much better to find some $s_n \to f$ and then have $\int s_n d\mu \to \int f d\mu$. 

But this is not always true. Suppose $f_n(x) = 1_{[n, n+1)}$. Then $f_n(x)$ converges to $f(x) = 0$ for all $x$. But the integral of each $f_n$ is $1$, and the integral of $f(x)$ is $0$. 

Intuitively we want to limit $f_n$. and stop some mass 'running away' like this. For that we have two results. 


### Monotone Convergence Theorem
Let $f_n(x)$ non-negative, measurable, weakly increasing to $f(x)$ almost everywhere. This means that for any $x$, $f_{n+1}(x) \geq f_n(x)$ and these approach $f(x)$ from below. Then
$$f_n(x) \to f(x) \implies \int f_n d\mu \to \int f d\mu$$
Basically I'm requiring that the $f_n$ have some mass wherever $f$ has mass. 

### Dominant Convergence Theorem
Suppose measurable $f_n$ such that $f_n \to f$ almost everywhere. Also suppose $|f_n(x)| \leq g(x)$ almost everywhere, with $g(x) \geq 0$ and $\int g(x) d\mu$ is finite. Then $\int f_n d\mu \to \int f d\mu$. 

This stops the mass running away to $\infty$ because it's basically trapped under $g$. 

Generally the DCT is used more often. 

### Payoff

OK, so with the MCT, I can get integrals of some non-negative function with 'horizontal slices'. 

Create $s_n$: 

$$ s_n(x) = \begin{cases} 
0 &\text{if } f(x) = 0\\
(k-1)/2^n &\text{if } (k-1)/2^n < f(x) < (k)/2^n \\
n &\text{if } f(x) \geq n
\end{cases}$$
where $k =1, 2, \ldots, n2^n$. 

So consider $f(x) = x^2$ on $0 \leq x \leq 10$. Integral is 1000/3.

$$ s_1(x) = \begin{cases} 
0 &\text{if } x =0\\
0 &\text{if } 0 < x < 1/\sqrt{2} \\
1/2 &\text{if } 1/\sqrt{2} < x < 1 \\
1 &\text{if } x \geq 1
\end{cases}$$
This is two horizontal slices. Their integral is $9 + (1 - 1/\sqrt{2})/2$.
$$ s_4(x) = \begin{cases} 
0 &\text{if } x =0\\
(k-1)/16 &\text{if } (k-1)/16 < x^2 < (k)/16 \\
(k-1)/16 &\text{if } \sqrt{k-1}/4 < x < \sqrt{k}/4 \\
0 &\text{if } 0 < x < 1/4 \\
1/16 &\text{if } 1/4 < x < \sqrt{2}/4 \\
2/16 &\text{if } \sqrt{2}/4 < x < \sqrt{3}/4 \\
3/16 &\text{if } \sqrt{3}/4 < x < 1/2 \\
\vdots & \\
63/16 &\text{if } \sqrt{63}/4 = 7.9/4 < x < 2\\
4 &\text{if } x \geq 2
\end{cases}$$

So $s_n$ is $n$ horizontal slices, forming a stairway with steps of width $1/2^n$, everywhere below $x$, which caps off at $s_n(x)= n$. As $n$ grows, the cap gets closer and closer to $f$. 

## Radon-Nikodym

We have measure space $M$ with measure $\mathcal M$. Let $f$ be a nonnegative function that is integrable with respect to $\mu$. 

Define $\nu$ - 'nu' - as a function: 
$$ \nu(A) = \int 1_{A} f d\mu \textbf{\hspace{5pt} or } \int_A f d\mu$$
for any $A$ in $\mathcal M$. 

Claim: $\nu$ is a measure. 
- That it is non-negative follows from the non-negativity of $\mu$ and $f$. 
- $\nu(\emptyset)$ = $\int 1_{\emptyset} fd\mu$; since $1_\emptyset$ is everywhere zero, this is $0$.
- Countable additivity: can show this with the linearity of the Lebesgue integral w/ the indicator-function form. Suppose $A$ is a union of countable disjoint $A_i$. Then

$$\begin{align}
\nu\left(A = \bigcup A_i\right) &= \int_{A}fd\mu\\
&= \int 1_{A}fd\mu\\
&= \int \left(\sum 1_{A_i} \right)f d\mu\\
&= \int \left(1_{A_1}f+ 1_{A_2}f + \ldots \right)d\mu 
&= \int 1_{A_1}fd\mu + \int 1_{A_2}fd\mu + \ldots\\
&= \sum \nu(A_i)
\end{align}$$

So $\nu$ is a new measure (ha). 


Then we can say that, given $\nu$ and $\mu$, we can find a function $f$ to satisfy the above. 

- We wil need $\nu$ to be 'absolutely continuous' with respect to $\mu$, which we can write $\nu << \mu$. This means that $\mu(A) = 0 \implies \nu(A)=0$. 
	- As an analogy, if $X$ is continuous with probability measure $P_X$ then $P_X << \lambda$, the Lebesgue measure. 
- We will also want a condition $\sigma$-finite. This is a technical condition. It means that **TODO TODO**


### Radon-Nikodym Theorem

Measure space $M$, $\sigma$-field $\mathcal M$, measures $\nu$ and $\mu$. $\nu$ is absolutely continuous wrt $\mu$. 

Then there is some measure $f$ such that 

$$\nu(A) = \int_A fd\mu \; \forall \, A \in \mathcal M$$
and $f$ is unique on $\mu$. 