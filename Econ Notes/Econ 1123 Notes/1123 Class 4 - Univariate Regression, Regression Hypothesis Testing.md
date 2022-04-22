---
date updated: 2021-07-01 13:52

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/econ/econ1123'
---

## [[1123 Class 4 - Univariate Regression, Regression Hypothesis Testing]]
Part of [[@Econ 1123 Index]]


### Univariate Regression Intro

Moved from [[1123 Class 3 - Hypothesis Testing]]

#### Population univariate linear regression?

For the population of college-educated workers in Boston, suppose $X$ is GPA and $Y$ is annual income. We want to know the observed relationship of $X$ and $Y$. 

We can put these two variables on a scatter plot. If we think they are linearly related, we can draw a line of "best fit" through the scatter, which represents a prediction $Y$ with:

$$ Y = \beta_0 + \beta_1X_1$$

Here, $\beta_0$ is a constant term, and $\beta_1$ is the slope of the regression line - the average marginal effect of a change on GPA on annual income. 

If we know $x_i$, we can compute 

$$ \hat{y}_i = \beta_0 + \beta_1 x_i  $$

There will be some variation in $Y$ that we don't predict - $\hat{y}_i - y$. We call this an error term $u_i$. This represents everything in $Y$ that is not explainable by $X$. In our GPA/income example, income may also vary with race or sex - which, if they are uncorrelated to GPA (a strong assumption!) will not be captured by the $\beta$s. 

#### Sample Univariate Linear Regression

Now, suppose we don't have the population - just a sample. We can use the sample to produce estimates $\betahat_0$ and $\betahat_1$ by putting a line through the sample's scatter plot. But how do we choose which line to put?

There are several possible criteria for picking a line. Most minimize some measure of error terms - called ==residuals== in the sample. For example, we could say:

$$ \underset{\betahat_0, \betahat_1}{\text{min}} \sum_{i=1}^n |y_i - \yhat_i|$$

This criterion is the Least Absolute Deviation (LAD) and it's a pain to differentiate. 

So we use a different but related one:

$$ \underset{\betahat_0, \betahat_1}{\text{min}} \sum_{i=1}^n (y_i - \yhat_i)^2 \equiv \underset{\betahat_0, \betahat_1}{\text{min}} \sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)^2 $$

This estimator minimizes the squared residuals. So it's called ==least-squares==, or Ordinary Least Squares (OLS). 

``` ad-info 
title: Digression: First Order Conditions and Closed-Form Expression for OLS
collapse: closed

We have 

$$\underset{\betahat_0, \betahat_1}{\text{min}} \sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)^2$$

Let's say  $f(\betahat_0, \betahat_1) :=\sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)^2$ To minimize this, we can compute two first order conditions:

$$ \frac{\partial f(\betahat_0, \betahat_1)}{\partial \betahat_0} = 0$$

$$ \frac{\partial f(\betahat_0, \betahat_1)}{\partial \betahat_1} = 0$$

First we can look at the upper one. Let's expand it out and then distribute the sum. 

$$\begin{array}{rcl} 
0 &=& \frac{\partial}{\partial \betahat_1}  f(\betahat_0, \betahat_1)\\ 
&=& \frac{\partial}{\partial\betahat_0} \sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)^2\\
&& \text{use chain rule} \\
&=& -2 \sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)\\
&=& -2 [\sum_{i=1}^n y_i - n \betahat_0 - \sum_{i=1}^n\betahat_1x_i]\\
\betahat_0 &=& \sum_{i=1}^n y_i/n - \betahat_1\sum_{i=1}^nx_i/n\\
\betahat_0 &=& \ybar - \betahat_1 \xbar\\
\end{array}$$

Now differentiate the other one:

$$

\begin{array}{rcl} 
0 &=& \frac{\partial}{\partial \betahat_1}  f(\betahat_0, \betahat_1)\\ 
&=& \frac{\partial}{\partial\betahat_1} \sum_{i=1}^n (y_i - \betahat_0 - \betahat_1x_i)^2\\
&& \text{chain rule again}\\
&=&-2\sum_{i=1}^n x_i(y_i - \betahat_0 - \betahat_1x_i)\\
&=&\sum_{i=1}^n x_iy_i - \betahat_0 \sum_{i=1}^nx_i - \betahat_1\sum_{i=1}^nx_i^2\\
&&\text{substituting for }\betahat_0\\
&=&\sum_{i=1}^n x_iy_i - (\ybar - \betahat_1 \xbar)\sum_{i=1}^nx_i - \betahat_1\sum_{i=1}^nx_i^2\\
&=&\sum_{i=1}^n x_iy_i - \ybar\sum_{i=1}^nx_i + \betahat_1 \xbar\sum_{i=1}^nx_i - \betahat_1\sum_{i=1}^nx_i^2\\
\betahat_1 &=&\sum_{i=1}^n x_iy_i - \ybar\sum_{i=1}^nx_i/(\xbar\sum_{i=1}^nx_i - \sum_{i=1}^nx_i^2) \\
\betahat_1 &=&\sum_{i=1}^n x_iy_i - \xbar\ybar/(\xbar^2 - \sum_{i=1}^nx_i^2) \\
\betahat_1 &=&\sum_{i=1}^n (x_i - \xbar)(y_i - \ybar)/\sum_{i=1}^n (x_i - \xbar)^2 \\
\end{array}$$ 

This may be recognizable as 
$$\betahat_1 = \text{Cov}(X,Y)/\text{Var}(X)$$.

```

For more generalized statements of the above, see
[[Matrix formulation of Linear Regression]]
For proof that this estimator is unbiased and has several desirable properties, see:
[[Gauss-Markov Theorem]]

### Using and Interpreting Linear Regressions

#### Explanatory Power

So we have fit our least-squared-errors line through our data. We can be confident we've done the best we can. But how good is our regression?

We can use a statistic $r^2$ to describe the proportion of observed variance in $Y$ explained by $X$. We can think of the sample variance of $Y$ as $\sum(y_i - \ybar)^2$. The proportion explained by $X$ is $\sum(\yhat_i - \ybar)^2$. Then we write

$$ r^2 = \frac{\sum(\yhat_i - \ybar)^2}{\sum(y_i - \ybar)^2} \equiv 1 - \frac{\sum(y_i - \yhat)^2}{\sum(y_i - \ybar)^2}$$

In other words, the greater the residuals $(y_i - \yhat)$ relative to the variation in $Y$ (y_i - \ybar)$, the less useful the explanation. 

In the multivariate case, we will largely use an adjusted $r^2$, to be described later. 


#### Sampling Distribution of $\betahat$.

Very similar to previous discussion of [[1123 Class 2 - Intro to Sampling, Normal Distribution and Parameter Estimation|sampling distribution]]. For each sample size, a given observed $\betahat_1$ is a draw from a distribution of all possible $\betahat_1$, that is centered on the true $\beta_1$ for the population. 

This distribution tends towards a normal distribution <font color="red"> why????? </font>. The dispersion of that normal distribution is given by a standard error of the regression. 

There are heteroskedasticity-robust and homoskedasticity-only versions of the standard error formula. We should always use the heteros version, since it maps to the homos-only version when homoskedasticity holds (for more, see [[2001.13  Robust Standard Errors]]). 

#### Hypothesis testing on $\betahat$. 

As before, we have a null hypothesis: $H_0:\beta_1 = \beta_{1,0}$. We want to see if our observed $\betahat_1$ is "far enough" from $H_0$ that we can reject. 

How far? We use the same sort of assumption: if $H_0$ were true, then $\betahat ~ \mathcal{N}(\beta_{1,0}, SE_\betahat)$ - using a standard error estimated from the data. So we can use the same techniques: the gates method, the t-stat, the p-value. 

#### Homo- and Hetero-skedasticity 

Given a population where the regression line is $Y = \beta_0 + \beta_1 X$, consider  a small interval of $X$, call it $a$.  We can define a value that is the variance of $Y$ conditional on $X \in a$ - denote it $\text{Var}(Y|X=a)$. This is called a skedastic function. 

Homoskedasticity is a condition under which the skedastic function is constant across values of $X$ in the population. Returning again to the relationship between income and GPA, this would mean that the variance of income is the same when GPA is 2.0 and when it is 4.0. 

Data that is not homoskedastic is heteroskedastic. This creates all sorts of problems, since homoskedasticity is one of the [[Gauss-Markov Theorem]] assumptions. Specifically for our purposes, the homos standard error will understate the dispersion of the sampling distribution. So we need to use a heteros standard error formula. 

![](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Heteroscedasticity.png/300px-Heteroscedasticity.png) 
Heteroskedastic data: image from Wikipedia

Practically, a great deal of economic data is heteroskedastic. So we need to watch out for that. 