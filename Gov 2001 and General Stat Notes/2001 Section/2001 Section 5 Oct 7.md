---
date updated: 2021-10-07 13:40

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
- '#🚧'
---

# [[2001 Section 5 Oct 7]]
Part of [[@Gov 2001 and Stats Index]]


- All estimators use either analytical or computational methods - some both. one computational method is MCMC simulation - drawing from the "likelihood grid"


Uncertainty of MLEs
- Likelihood framework - what CIs, hyp tests use
- asymptotic normality - if we pick an estimator that's not asymptotically normal, we can still get pretty far by either 1) quadratic approx or 2) iid assumption


Standard error:
- standard deviation of an estimator for a parameter of interest
	- $\sqrt{\hat{V}(\thetahat_{\text{MLE}})}$
- For MLEs - inverse negative square root of the hessian (ugh lol)
- Sigma MLE is not unbiased - need to divide by n-1 instead


Hypothesis testing
- estimate observed $\hat{\mu}_{\text{MLE}}$
- choose null hypothesis and direction to test/alternative hypothesis
- Choose a critical value
- simulate MLEs of parameter from null distribution
- then calculate proportion of MLEs that are as weird or weirder as observed



Uncertainty of MLEs: Hypothesis testing

After assuming asymptotic normality - analytic test (Wald Test)
- Aka t test
- estimate $\hat{\mu}_{\text{MLE}}$
- choose null hypothesis
- choose CV
- wald stat -> $[\hat{\mu}_{\text{MLE}} - \mu_0]/SE$
- Reject $H_0$ if $T$ falls into a critical region


Confidence interval
- same concept as above. all the null hypotheses you can't reject


just always use qnorm


likelihood ratio test
- two models, one nested in the other
- comparing one model's likelihood surface at best possible value to the other's
- LR can make a test state -2 ln LR which is $\chi^2$ distributed. Can use the anova function - pass in two models and specify LRT test and it does it for you
- $k(y)$ is only the same for nested models
