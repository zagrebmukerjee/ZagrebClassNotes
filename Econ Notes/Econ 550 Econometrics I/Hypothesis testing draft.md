---
aliases: 
tags: 
creation date: Saturday, December 3rd 2022, 4:45 pm
date updated: Saturday, December 3rd 2022, 5:16 pm
---
## Hypotheses

See: [[2002.3 Hypothesis Testing]]. As with other presentations, there's a null and alternative hypothesis, $H_0$ and $H_A$ or $H_1$. 

Think of this as differentiating members of a parametric family. For instance, $X_i \sim N(\mu, 5)$. Then we can have $H_0: \mu = 0$ and $H_A: \mu = 1$. 

This is a family $\mathcal F = \{ N(\mu, 5): \mu \in \{0, 1\} \}$. So the hypotheses represent a disjoint partition of this parametric family. 

More generally: 
$$ \mathcal F = \{ f(\cdot, \theta): \theta \in \Theta \}$$
Then we can have $H_0: \theta \in \Theta_0$ and $H_A: \theta \in \Theta_A$, with $\Theta_0 \cup \Theta_A = \Theta$ and $\Theta_0 \cap \Theta_A = \emptyset$. 


We can also have composite hypotheses about multiple possible parameter values: e.g. with $H_A: \mu > 0$, or $H_A: \mu \neq 0$. 
Can also have $H_0: \mu \leq 0$ and $H_A: \mu > 0$; or with $\mathcal F : \{ N(\mu, \sigma^2), \mu \in \R\}$, we can have $H_0: \mu = \mu_0, \sigma^2 > 0$, and $H_A : \mu \neq \mu_0, \sigma^2 > 0$. Important to remember the $\sigma$ component <font color=#F7B801>why</font>

## Tests

A test is some way of using the data to decide whether $H_0$ or $H_1$ is true. For instance, take the case where $H_0 : \mu = \mu_0$, and $H_1: \mu \neq \mu_0$. Then we could say eg reject the null hypothesis if it falls outside a confidence interval:

$$H_0 \notin \left[ \Xbar \pm S_{Xn} z_{1-\alpha}/\sqrt{n}\right]$$
We could transform this into a <font color=gree>test statistic</font>; 

$$ T_n = \left| \frac{\sqrt{n}(\mu_0 - \Xbar_n)}{S_{Xn}}\right|$$
Then we can reject the null hypothesis if $T_n \geq z_{1-\alpha}$, which is equivalent to saying that $H_0$ would fall outside the interval estimate. We are using $z_{1-\alpha}$ as a <font color=gree>critical value</font>.

A test will consider the possible data values for which the null hypothesis can be rejected, called the <font color=gree>critical region</font>.

If an $H_A$ is not specified, we're testing $H_A: \theta \in \Theta \setminus \Theta_0$. 

### Type 1 and Type 2 Errors

Time to finally get this right?
- <font color=gree>Type 1 errors</font>: Wrongly reject the null.
- <font color=gree>Type 2 errors</font> Wrongly fail to reject the null

Given the covid test example: A Type 1 error is the false positive, test comes out as positive if you don't have it (the test is not specific). A Type 2 error, false negative would be test saying you don't have covid when you do: test is not sensitive. 

We can define the <font color=gree>size</font> of a test as the greatest possible probability of Type 1 errors for $\theta \in \Theta_0$. The <font color=gree>significance level</font> is a threshold: a test is significant at the 5 percent level if size is less than or equal to 5%. 

We can talk about Type 2 errors/false negatives also. $\beta$ is frequently used as notation for a false negative probability: 

$$\beta = P(\text{Accept }H_0\; |\;H_1\text{ is true})$$
Then $1-\beta$ is the probability of rejecting $H_0$ if $H_1$ is true. This is the <font color=gree>power</font> of a test. 

The confidence interval test has the same probability of Type 1 error for any value of $\theta_0$; we call this <font color=gree>similarity</font>. Not all tests are similar.