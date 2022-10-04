---
aliases: 
date updated: Tuesday, October 4th 2022, 12:20 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/foundations'
creation date: Thursday, April 7th 2022, 3:48 pm
---

## [[Markov's and Chebyshev's Inequalities]]

### Markov's Inequality

Markov's inequality acts to bound tail probability of random variables. Suppose $X$ is a random variable: then for all $k > 0$, $P(|X|>k) \leq E|X|/k$. In other words, the tail declines at least as fast as $1/k$. This is useful, for instance, when considering the Law of Large Numbers. There we are talking about averaging lots of random variables - we need to assure ourselves that the tails are not too huge. 

Proof:
$$\begin{align}
E|X| &= E|X|1_{X\geq k} + E|X|1_{X < k} \\
&\geq E|X|1_{X\geq k} \text { because }E|X|1_{x < k} \geq0\\
&\geq k1_|X|{X\geq k} \text{ because this implies } E|X| > k\\
& \geq k E1_{X\geq k}\\
&\geq P(X \geq k) \\
\end{align}$$

### Chebyshev's Inequality

For a wide array of distributions, Chebyshev's inequality places limits on how many values can be beyond a given distance from the mean. This is a very powerful tool, letting us make statements like "no more than 25% of the values are more than 2 standard deviations from the mean" for many (normal and non-normal) random variables. ^intro

#### Theorem

Let $X$ be an integrable random variable, with finite EV $\mu$ and finite variance $\sigma^2$. Then, for $\{k \in \mathbb{R} | k > 0\}$ 

$$ P(|X - \mu| \geq k\sigma) \leq \frac{1}{k^2}$$

For instance, if I want to know what proportion of draws would be more than three standard deviations from the mean, I can say the probability is less than $\frac{1}{9}$.

### Proof
