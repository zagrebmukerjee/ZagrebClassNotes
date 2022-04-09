---
date updated: 2021-06-30 19:34

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/econ/econ1123'
---

## [[1123 Class 3 - Hypothesis Testing]]
Part of [[@Econ 1123 Index]]


### Hypothesis Testing 

We're interested in rejecting, or failing to reject, a claim about the world. We call this claim the ==Null Hypothesis==; $H_0$. Suppose we are looking at the population mean. A null hypothesis about the population mean would be some value that we call $\mu_{X,0}$.

We can test this claim by drawing a sample from the population. This theory of inference is interested in asking: "Given the null hypothesis, how likely is the sample we observed?" We want to look at the sampling distribution that's centered around $\mu_{X,0}$ - the "samples we would have gotten if $H_0$ were true." To guess the dispersion of this distribution, we have to use our standard error from the sample as an estimator of the sampling distribution's standard deviation.  Are my data "too far" from $H_0$? 

Now we can hypothesis test. There are 3 steps.

1) Determine $\alpha$, the ==significance level==. This is how comfortable you would be with erroneously rejecting the null hypothesis. Frequently people use 5%, others choose 1%. 
2) State your null $H_0$ and alternative hypothesis and $H_1$. For example, this could be that $\mu_X = \mu_{X,0}$ and $\mu_X \neq \mu_{X,0}$. 
3) Take a sample - compute $\bar{x}$ and the standard error, $s_x/\sqrt{n}$. Then check if $\bar{x}$ is "statistically too far away" from $\mu_{X,0}$. 

Step 3 is the meat of the difficulty. There are three approaches that are very similar: 
- Assume that $H_0$ is true, and $\bar{x} \sim \mathcal{N}(\mu_{X,0}, SE)$. 
- Use the resulting distribution to figure out how likely it is that you'd observe $\bar{x}$  given $H_0$. 
- If that probability is sufficiently low - less than $\alpha$ - reject $H_0$. 

**<u>All  approaches assume that the [[Central Limit Thm and Law of Large Numbers|Central Limit Theorem]] has kicked in at your $n$</u>**. In addition, all approaches give the same results. 

#### Approach 1: Gates method 

Create two gates $G_L, G_R$ in $\bar{x}$ space such that

$$ P(G_L \leq \bar{x} \leq G_R| \bar{x} \sim \mathcal{N}[\mu_{X,0}, SE(\bar{x})] ) = 1 - \alpha$$

This can be done using the $z$-tables at $2.5\%$ and $97.5%$ (for convenience, we can remember that these correspond to $z$-scores of $\pm 1.96$. Then, we can simply say that if $\bar{x}$ is outside the gates, we reject the null. Otherwise we fail to reject. 

$1.96$ here is called the ==critical value==.

This method is rarely used in favor of the other two. 

#### Approach 2: T Statistic

The $t$-statistic, or $t$-stat ($t$ standing for test), is a rephrasing of the Gates method using the $z$-score. We can compute the $z$ score of $\bar{x}$ using mean $\mu_{X,0}$ and the standard error. We can then put our $\alpha$ into $z$-score space with the $z$-table as before. Then compare the $z$-score of $\bar{x}$ to the critical values. If it's outside that bound, reject the null. Otherwise don't reject. 

#### Approach 3: P-Value. 

We ask the question - what is the probability under the null that, running another experiment with the same $n$, we'd get a result as extreme as $\bar{x}$? 

The new experiment is simply another draw from the sampling distribution. We want to know if the absolute $z$-score of $\bar{x}_2$ is greater than that of $\bar{x}$. To do this, we can just look at the area outside of the gates given by $\pm Z(\bar{x})$ (where $Z(a)$ is the $z$-score function). If that area - the $p$-value - is less than $\alpha$, we can reject the null. 

Alternatively, our $p$-value is the same as $2(CDF_{Z}(-|t|))$, where $CDF_{Z}$ is the $z$-table function. 


### Univariate Regression Intro

Moved to Class 4 for consistency. 