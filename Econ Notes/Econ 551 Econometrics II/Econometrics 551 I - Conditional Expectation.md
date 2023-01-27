---
aliases:
creation date: Friday, January 27th 2023, 1:06 pm
date updated: Friday, January 27th 2023, 2:03 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Econometrics 551 I - Conditional Expectation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>



Defining conditional expectations in terms of conditional probabilities becomes a bit messy when thinking about continuous RVs, and we risk dividing various things by zero. Instead, we can define it implicitly as a projection. Because when has defining something implicitly not been clarifying?

### Motivation

First introduce the notion of a <font color=gree>square-integrable</font> function; this means that the square of the absolute value is integrable. This lets us say that if $E[X^2] < \infty$ then $E[f(X)^2] < \infty$. Let $X$ be a $k-$dimensional random vector, and $M$ be the space of square-integrable functions that map from $\R^k \to R$. 

We want to find the (SI) function of $X$ that is the best approximation of $Y$; in this case, best being Mean Squared Error (MSE) minimizing.

Define the CEF as $m^*$: 


$$ m ^* = \inf_{m \in M} E[(Y - m(X))^2] $$
It can be shown that $m^*$ exists and is weakly best. 

### Theorem

Given an $m^*$ satisfying the above, 
1) It defines a class of functions equal with probability $1$ that is unique on $M$, and 
2) It satisfies the minimum criterion if and only if it satisfies an orthogonality criterion: for any square-integrable function $g$,  

$$ E[(Y - m^*(X))g(X)] = 0$$
<font color=#F7B801>interpreting this as an inner product of two vectors being zero? Hence orthogonality. Is the inner product </font>$\langle f(x), g(x) \rangle = f(x)g(x)$?

#### Proof

Suppose $m$ and $m^*$ are in $M$. Then by Cauchy-Schwarz, $m - m^* \in M$ as well. 

First, expand the MSE expression: 

$$\begin{align}
E[(Y - m(X))^2] &= E[((Y - m^*(X))-(m(X) - m ^*(X)))^2]\\
E[(Y - m(X))^2] &= E[(Y - m^*(X))^2]+E[(m(X) - m ^*(X))^2] - 2 E[(Y - m^*(X))(m(X) - m ^*(X))]\\
\end{align}$$
**Orthogonality implies Minimum Condition**

First, suppose that $m^*$ satisfies the orthogonality condition. Then, since $m(X) - m^*(X) \in M$, the condition implies that $E[(Y - m^*(X))(m(X) - m ^*(X))]= 0$. Note also that $E[(m(X) - m ^*(X))^2]$ is always nonnegative, and therefore 

$$E[(Y - m(X))^2] \geq E[(Y - m^*(X))^2]$$
It follows that if $m, m^*$ both satisfy the minimum condition, then we must have $E[(Y - m^*(X))^2]$ $= E[(Y - m(X))^2]$; so $E[(m(X) - m ^*(X))^2]$ must be zero and therefore $m(X) = m^*(X)$ with probability $1$. 

**Minimum Condition implies Orthogonality**

Now suppose $m^*$ minimizes. Then fix some $g \in M$ and $\alpha \in R$. Let $h(X) = m^*(X) + \alpha h(X)$. 

$$\begin{align}
E[(Y - m^*(X))^2] - E[(Y - h(X)^2] &\leq 0\\
E[Y^2 - 2 m^*(X)Y + m^*(X)^2] - E[Y^2 - 2 h(X)Y + h(X)^2] &\leq 0\\
E[Y^2 - 2 m^*(X)Y + m^*(X)^2 - Y^2 + 2 (m^*(X) + \alpha g(X))Y - (m^*(X) + \alpha g(X))^2] &\leq 0\\
E[m2 Y g(X) - (m^*(X)^2 + g(X)^2 + 2m^*(X)g(X) )] &\leq 0\\
E[2 Y g(X) - (m^*(X)^2 + g(X)^2 + 2m^*(X)g(X) )] &\leq 0\\
\end{align}$$
