---
aliases:
creation date: 2022-10-30 12:31
date updated: 2022-10-30 12:31

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics IX - Least Squares]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Least Squares Estimator

#status/section/🚧 



### Assumption 3

Now we're interested in the random regressors case. 
1) Assume $X_i , U_i$ i.i.d. 
2) $E(U_i |X_i) = 0$ almost surely. 
3) $EU_i^2 < \infty$; and the homoskedasticity assumption, $\var(U_i) = \sigma^2$ almost surely. 
4) $EX^2 < \infty$; $\var(X_i) = \sigma^2_X > 0$. 

Then:  $\sqrt{n}(\hat \beta_n - \beta_0) \to_d N(0, \sigma^2/\sigma^2_X)$. 

