---
aliases:
creation date: Wednesday, September 21st 2022, 3:54 pm
date updated: Friday, November 4th 2022, 11:15 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics IIIa - Linearity of Lebesgue Integral]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

We want to show that the Lebesgue integral is linear - that is, $\int (a f(x) + bg(x))d\mu = a \int f(x) d\mu + b \int g(x)d\mu$. 

## Linearity for Simple Functions

Let $f(x)$ be a measurable simple function, i.e. a function that takes on a finite number of values, on a measure space $M, \mathcal M, \mu$. I can then have finite, disjoint sets $A_i$ in $\mathcal M$ s.t. $f$ takes constant values $c_i$ in each $A_i$. Then I can write it as follows: 

$$ f(x) = \sum_{j=1}^J c_j 1_{A_j}(x)$$

By definition the integral is 

$$\int f(x) d\mu = \sum_{j =1}^J c_j \mu(A_j) $$

Now we are interested in linearity. We want to show that $\int af(x) + bg(x) d\mu = a\int f(x) d\mu+ b\int g(x) d\mu$ for simple $f,g$. That $\int af(x)d\mu$ follows from multiplication's distributivity: 

$$
\begin{align*}
    \int af(x) d\mu &= \sum_{j =1}^J ac_j \mu(A_j) \\
    &= a\sum_{j =1}^J c_j \mu(A_j) \\
    &= a \int f(x) d\mu
\end{align*}
$$

Define $f$ as above, and $g$ as

$$ g(x) = \sum_{k=1}^K d_k 1_{B_k}$$

with $B_k \in \mathcal M$. Then the function $h(x) = f(x) + g(x)$ is simply 
$$ h(x) = \sum_{j=1}^J \sum_{k=1}^K \left[c_j 1_{A_j}(x) + d_k 1_{B_k}(x) \right]$$


Let $A$ be the disjoint union of $A_j$ and $B$ the disjoint union of $B_j$. 

We can then write each $A_j = (A_j \cap B) \cup (A_j \cap B^c)$ - splitting into points shared with $B$ and not. Then $1_{A_j} = 1_{A_j \cap B} + 1_{A_j \cap B^C}$. Similarly for $B$. 

Let $A_1 = \bigcup_{j=1}^J A_j \cap B^c$, and $B_1 = \bigcup_{k=1}^K B_k \cap A^c$. 
Let $C = A \cap B$. Since $A_j$ partition $A$ and $B_k$ partition $B$ I can say $C = \bigcup_{j=1}^J (A_j \cap B) = \bigcup_{k=1}^K (B_k \cap A) $. These sets $A_1, B_1, C$ are finite collections of disjoint intervals. 

Thus $h(x)$ is defined over $A_1 \cup B_1 \cup C$. Call this set $S$, made of disjoint intervals $S_i$. Each interval will be in only one of $A_1, B_1, C$. Let 
$$k_i = \begin{cases}
c_j &\text{ if }S_i = A_j \cap A_1\\
d_k &\text{ if }S_i = B_k \cap B_1\\
c_j + d_k &\text{ if }S_1 = A_j \cap B_k\\
\end{cases} $$

So I can write $h(x) = f(x) + g(x)$ as 
$$ \sum_{i=1}^I k_i 1_{S_i}(x)$$

Almost done. The integral is 
$$
\begin{align}
    \int f(x) + g(x) d\mu &= \int h(x) d\mu \nonumber\\
    &= \sum_{i=1}^I k_i \mu(S_i)\\
    &= \sum_{j=1}^J \sum_{k=1}^K c_j \mu(A_j \cap A_1) + d_k \mu(B_k \cap B_1) \nonumber\\
    &\hspace{.25in}+ (c_j + d_k)\mu(A_j \cap B_k)\\
    &= \sum_{j=1}^J \sum_{k=1}^K c_j \left[\mu(A_j \cap A_1) + \mu(A_j \cap C)\right] \nonumber\\
    & \hspace{.25in} + d_k \left[(\mu(B_k \cap B_1) + \mu(B_k \cap C)\right]\\
    &= \sum_{j=1}^J c_j \left[\mu(A_j \cap A_1) + \mu(A_j \cap C)\right] \nonumber\\
    & \hspace{.25in} + \sum_{k=1}^K d_k \left[(\mu(B_k \cap B_1) + \mu(B_k \cap C)\right]\\
    &= \sum_{j=1}^J c_j \mu(A_j) + \sum_{k=1}^K d_k \mu(B_k)\\
    &= \int f(x)d\mu + \int g(x) d\mu
\end{align}
$$
Line 1 uses the definition of the integral for simple functions. Line 2 uses the definition of $k$ and our division of each $A_j$ into $A_j \cap A_1$ and $A_j \cap B_k$ for some $k$s, and vice versa. Line 3 uses our definition of $C$, line 4 rearranges, and line 5 reverses the decomposition of each $A_j$. Line 6 uses the definition of the Lebesgue integral. 


## Linearity for Non-negative Functions

Suppose $f(x), g(x)$ nonnegative and integrable. Suppose we create the same sort of simple step-functions to converge to $f(x)$ as in class, that is to say: 
$$ s_n(x) = \begin{cases} 
0 &\text{if } f(x) = 0\\
(k-1)/2^n &\text{if } (k-1)/2^n < f(x) < (k)/2^n \\
n &\text{if } f(x) \geq n
\end{cases}$$

It's clear that $s_n(x)$ is increasing in $n$: each new 'slice' is taking an existing slice and replacing it with one slice just as wide and another that's $1/2^n$ wider. So it's also clear that $s_n(x) \to x$. 

So we can say with the MCT:
$$
\begin{align}
    \int f(x) d\mu &= \lim_{n \to \infty} \int s_n(x) d\mu \nonumber\\ 
    \int af(x) d\mu &= \lim_{n \to \infty} \int as_n(x) d\mu \nonumber\\
    &=a \int \lim_{n \to \infty} s_n(x) d\mu \\
    &= a \int f(x) d\mu
\end{align}
$$
In line 7, I use the linearity of simple functions and the MCT. In line 8 I use the definition of the integral.

Now consider $h(x) = f(x) + g(x)$. Let $t_n$ converge to $g(x)$.

I will show first that $\lim_{n \to \infty}s_n(x) + t_n(x)$ converges to $h$, and then that this implies $\int h d\mu = \int f d\mu + \int g d\mu$.

Consider $s_n (x) + t_n(x)$. 
$$ u_n(x) = s_n(x) + t_n(x) = \begin{cases} 
0 &\text{if } f(x) = g(x) = 0\\
s_n(x) &\text{if } f(x) > 0 \text{ and } g(x) = 0\\
t_n(x) &\text{if } g(x) > 0 \text{ and } f(x) = 0\\
s_n(x) + t_n(x) &\text{if } 0 < f(x) + g(x) < n \\
n &\text{if } n \leq f(x) + g(x)\\
\end{cases}$$
Intuitively this is the two sets of slices stacked atop each other. 

Since $s_n$, $t_n$ are weakly increasing in $n$, $u_n$ is weakly increasing in $n$.

Now suppose any ball of $\epsilon > 0$ around $f(x) + g(x)$. By convergence we know the lower part of this ball contains some $s_m(x)+ t_n(x)$ almost everywhere. Let $N = \max(m,n)$; then $u_N(x)$ is in this ball, so $u_N(x) \to h(x)$. 

So we have: 
$$
\begin{align}
    \int h(x) d\mu &= \lim_{n\to\infty} \int u_n(x) d\mu \nonumber \\
    &= \lim_{n\to\infty} \int s_n(x) + t_n(x) d\mu \nonumber \\
    &= \lim_{n\to\infty} \int s_n(x)d\mu + \int t_n(x) d\mu \\
    &= \int\lim_{n\to\infty} s_n(x)d\mu + \int \lim_{n\to\infty}t_n(x) d\mu \\
    &= \int f(x) d\mu + \int g(x)d\mu
\end{align}
$$
Line 9 uses the linearity of simple functions. Line 10 uses linearity of convergent limits and the MCT. Line 11 uses the definition of the integral. 

## Linearity in General
To extend this result to all integrable functions, divide $f= f_+ - f_-$ where $f_+ = \max(f(x), 0)$ and $f_- = \max(-f(x),0)$. Each is nonnegative. That $f$ is integrable means each of $f_+$ and $f_-$ are integrable.So we have a linearity result for each of $f_+$ and $f_-$. 

$$\int f(x) d\mu = \int f_+ (x) d\mu - \int f_-(x) d\mu$$

Let 
$$
\begin{align}
    a \int f(x) d\mu + b\int g(x) d\mu &= a\left(\int f_+ (x) d\mu - \int f_-(x) d\mu\right) \nonumber \\ 
    &\hspace{.25in}+ b\left(\int g_+ (x) d\mu - \int g_-(x) d\mu\right)\nonumber \\
    &= a \int f_+ (x) d\mu - a \int f_-(x) & \nonumber \\
    &\hspace{.25in}+ b\int g_+ (x) d\mu - b\int g_-(x) d\mu\\
    &= \int a(f_+(x) - f_-(x)) + b(g_+(x) - g_-(x)) d\mu\\
    &= \int af(x) + bg(x) d\mu
\end{align}
$$
Lines 12 and 13 use the already-known linearity of nonnegative functions. Line 14 uses the definition of the integral. 
