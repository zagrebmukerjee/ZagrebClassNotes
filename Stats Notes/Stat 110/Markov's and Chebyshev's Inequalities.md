---
date updated: 2021-06-30 11:26

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/stats/foundations'
---

## [[Markov's and Chebyshev's Inequalities]]

### Markov's Inequality 

### Chebyshev's Inequality


For a wide array of distributions, Chebyshev's inequality places limits on how many values can be beyond a given distance from the mean. This is a very powerful tool, letting us make statements like "no more than 25% of the values are more than 2 standard deviations from the mean" for many (normal and non-normal) random variables. ^intro

#### Theorem

Let $X$ be an integrable random variable, with finite EV $\mu$ and finite variance $\sigma^2$. Then, for $\{k \in \mathbb{R} | k > 0\}$ 

$$ P(|X - \mu| \geq k\sigma) \leq \frac{1}{k^2}$$

For instance, if I want to know what proportion of draws would be more than three standard deviations from the mean, I can say the probability is less than $\frac{1}{9}$.

### Proof

