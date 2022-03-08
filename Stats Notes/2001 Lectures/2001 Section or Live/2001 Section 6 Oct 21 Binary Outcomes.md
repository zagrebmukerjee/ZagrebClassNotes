---
date updated: 2021-10-21 13:45

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
---

# [[2001 Section 6 Oct 21 Binary Outcomes]]
Part of [[@Stats Index]]


Assumptions of logistic model
- binary outcomes
- explanatory variables uncorrelated
- linear relationship between X and linked function of outcomes 
	- Link function specifies the transformation between $X$ and a linear relationship with $Y$.
	- For logit, the link is the logit: R code `binomial(link = 'logit')`
	- For probit, the link is the Normal CDF
- despite the weird functional form it's linear - think abt using a log regression
- can use `glm` with R, it makes new assumptions about the error term
	- `lm` assumes $\epsilon \sim \mathcal{N}(0, \sigma^2)$
- logit coefficients are log odds
	- Odds are $\frac{p}{1-p}$. Log odds are $\ln(\frac{p}{1-p})$, which is the logit function of $p$; so the coefficient is $\ln(p) - \ln(1-p)$
- Example: Fearon and Laitin 2003.
	- What predicts the onset of a civil war?
	- Ppl used to think that it was religion or ethnicity.
	- Findings: these things are not predictive! poverty, large population, and rough terrain <font color = red> score 1 for James Scott! </font>
	- Fun trick: `glm(onset ~ .)` is `glm` of everything but onset
	- `stargazer` package lets you interpret coefficients 
	- dplyr - can summarize all columns with `across`
- R fun thing: `broom::tidy` will turn summary outputs into a nice tibble of coefficients