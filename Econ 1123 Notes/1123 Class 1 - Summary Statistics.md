	---
date updated: 2021-06-23 15:23

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
---

## [[1123 Class 1 - Summary Statistics]]
Part of [[@Econ 1123 Index]]

Mostly review of things I already knew and will learn again 

### Data Types

Three types of data: 
- Cross-sectional: many entities at one point
- Panel: Tracking several individuals through time. Aka longitudinal.
- Time series: 1 entity through time.

Different techniques to apply to each. 

### Summarizing Data with Descriptive Statistics

Three attributes we are interested in:
- Centrality
- Dispersion
- Z-score ( a standardized measure of individual points in relation to distr)

Two core concepts: <font color="gree">population</font> (everybody) and<font color="gree"> sample</font> (subset of everyone used to make inferences about everybody). We think of them differently, since the sample is imprecise approximation of population. This difference is at the heart of social-science inference. 

#### Centrality

Where is the middle of the data? Can be measured with the <font color="gree">mean</font>, $\sum x_i/n$.  Pop mean is denoted $\mu_X$. Sample mean is $\bar{x}$.

<font color="gree">Median</font> - $50^{\text{th}}$ is another measure of centrality that's less sensitive to outliers. But more annoying to differentiate. So we use mean.

#### Dispersion 

How spread out are the data? 

Three measures:

- <font color="gree">Mean Absolute Deviation.</font> Nice but also hard to diferentiate
- <font color="gree">Variance</font> Pop var $\sigma_x^2$ is $\sum(x_i - \mu_x)^2/N$. Sample var  $\sum(x_i - \xbar)^2/(n-1)$
	- Why $n-1$? To make it an unbiased estimator of population variance. 
-<font color="gree"> Standard Deviation</font> is sqrt of variance. Pop Stdev is $\sigma_x$, sample is $s_x = \sqrt{\sum(x_i - \bar{x})^2/(n-1)}$. 

```ad-info
title: $n-1$ details - TODO
collapse:true

$\sqrt{\sum(x_i - \mu)^2/(n)}$ is biased because...

```

There are several powerful theorems that let us use means and standard deviation to get a sense of the shapes of distributions. For more information, see [[Markov's and Chebyshev's Inequalities]]

#### Z score

How far is each point from the mean? <font color="gree">$Z$-score</font> or standard score is a standardized measure: $(x_i - \bar{x})/s_x$.  "How many standard deviations away from the mean are you"?

This is used a lot for hypothesis testing. 

### More Descriptives

#### Skewness

There are other summary statistics you might want to show. One useful one is <font color="gree">skew</font> (the third moment). Skew, or skewness, is a measure of the asymmetry of a distribution. 

$$ \text{Skew}[X] = E\left[ \left( \frac{X - \mu}{\sigma}\right)^3 \right] $$

Given the measure of skew:

- Values > 1 are strongly right skewed
- Values >0 <1 are moderately right skewed
- Values <0 >-1 are moderately left skewed
- Values <-1 are strongly left skewed. 


Skew often occurs in economic variables - partly because many of them have to be non-negative (eg. prices). 


#### Correlation Coefficient 

The <font color="gree">correlation</font> measures the direction and strength of the _linear_ association between two datasets or variables. It's denoted $\text{Corr}(X,Y)$ or $\rho (X,Y)$. 

$$ \rho (X, Y) = \frac{\text{Cov}(X,Y)}{\sigma_X \sigma_Y}$$

For a given sample of $X$ and $Y$, the sample correlation coefficient $r$ estimates $\rho$. The samples have to have the same size. 

$$ r(X,Y) =  \frac{\sum\limits_{i=1}^n(x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum\limits_{i=1}^n (x_i - \bar{x})^2 \sum\limits_{i=1}^n(y_i - \bar{y})^2}} = \frac{\sum\limits_{i=1}^n x_i y_i - n\bar{x}\bar{y}}{(n-1)s_xs_y}$$

It doesn't capture non-linear relationships. 

```
a <- -100:100
cor(a,a^2)
[1] 1.022992e-18

```

