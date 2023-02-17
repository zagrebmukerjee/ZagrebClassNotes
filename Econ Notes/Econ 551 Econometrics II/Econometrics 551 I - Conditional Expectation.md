---
aliases: 
tags: 
creation date: Friday, January 27th 2023, 1:06 pm
date updated: Friday, February 17th 2023, 11:11 am
---
 ---
aliases:
creation date: Friday, January 27th 2023, 1:06 pm
date updated: Friday, January 27th 2023, 2:44 pm

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

Now suppose $m^*$ minimizes. Then fix some $g \in M$ and $\alpha \in R$ with $\alpha \neq 0$. Let $h(X) = m^*(X) + \alpha h(X)$. 

$$\begin{align}
E[(Y - m^*(X))^2] - E[(Y - h(X))^2] &\leq 0\\
E[Y^2 - 2 m^*(X)Y + m^*(X)^2] - E[Y^2 - 2 h(X)Y + h(X)^2] &\leq 0\\
E[Y^2 - 2 m^*(X)Y + m^*(X)^2 - Y^2 + 2 (m^*(X) + \alpha g(X))Y - (m^*(X) + \alpha g(X))^2] &\leq 0\\
E[m^*(X)^2 + 2 Y \alpha g(X) - (m^*(X)^2 + \alpha g(X)^2 + 2\alpha m^*(X)g(X) )] &\leq 0\\
E[2 Y\alpha g(X) + \alpha^2 g(X)^2 + 2m^*(X)\alpha g(X) )] &\leq 0\\
2 \alpha E[g(X)(Y - m^*(X)] - \alpha^2 E[g(X)^2] &\leq 0\\
E[g(X)(Y - m^*(X)] &\leq \alpha E[g(X)^2]/2 \\
\end{align}$$

But since this holds true for all $\alpha$, it follows that $E[g(X)(Y - m^*(X)]$ must be $0$. 


### Extension

This implicit definition of the CEF can be used to define a conditional probability. Let $B$ be some measurable set, and define a random variable $W$ as a function of $Y$, $I_{Y \in B}$. Then 

$$P(Y \in B |X) = E[W|X]$$


## Properties of Expectation and CEF

The definition of the CEF as a projection makes a variety of properties of CEFs much easier to deal with.

1) Claim: $E(Y +Z|X) = E(Y|X) + E(Z|X)$. Proof: guess and check. $E[(E(Y+Z - E(Y|X) - E(Z|X))g(X)]  =$ $E[(Y - E[Y|X])g(X)] + E[(Z - E[Z|X])g(X)] = 0$, using linearity of expectation (the last step is the two conditional expectations of $Y$ and $Z$)
2) Claim: if $f$ square-integrable: $E[f(X)Y|X] = f(X)E[Y|X]$. Proof: $E[(f(X)Y - f(X)E[Y|X])g(X)]$ $= E[(f(X)(Y - E[Y|X])g(X)]$ $= E((Y - E[Y|X])h(X)) = 0$since $f$ and $g$ being square integrable means that $h = f(x)g(x)$ must be also. 
3) Claim: $E(f(X)|X) = f(X)$. Proof: guess and verify. Let $Y = f(X)$. Then $E[(Y - f(X))g(X)] = E[(f(X) - f(X))g(X)] = 0$.
4) Claim: If $P(Y \geq 0) = 1$ then $P(E[Y|X]\geq 0) = 1$. Proof: Suppose $m$ such that $P(m(X) > 0) < 1$; let $B = \{x:m(X) < 0\}$. Then $E[(Y - mX)I\{X \in B\}] = E(YI\{X \in B\}) - mXI\{X \in B\} > 0$  (since $mX$ is negative whenever $I =1$). So $m$ cannot be the CEF. 
5) Claim: Law of Iterated Expectations, $E[Y] = E[E[Y|X]]$. Proof: Follows from the orthogonality condition with $g(X) = 1$: $E[(Y - E[Y|X])] = 0 \implies$ $E[Y] = E[Y|X]$. 
	- Generalized Law of Iterated Expectations: if $X = (X_1, X_2)$, $E[Y|X_1] = E[E[Y|X_1, X_2]|X_1]$. Proof: $E[Y - E[Y|X_2, X_1]g(X_1)]$
