---
aliases:
creation date: Sunday, October 30th 2022, 12:30 pm
date updated: Friday, November 4th 2022, 11:14 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation I - Least Squares]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]


## Least Squares Estimator

#status/section/🚧 



### Assumption 3

Now we're interested in the random regressors case. 
1) Assume $X_i , U_i$ i.i.d. 
2) $E(U_i |X_i) = 0$ almost surely. 
3) $EU_i^2 < \infty$; and the homoskedasticity assumption, $\var(U_i) = \sigma^2$ almost surely. 
4) $EX^2 < \infty$; $\var(X_i) = \sigma^2_X > 0$. 

Then: $\sqrt{n}(\hat \beta_n - \beta_0) \to_d N(0, \sigma^2/\sigma^2_X)$. 

Proof: 
$$\begin{align}
\limn (\betahat_n - \beta_0) &= \limn \frac{\sumn{i} (X_i - \Xbar_n)(Y_i - \Ybar_n) }{\sumn{i}[X_i - \Xbar]^2} - \beta_0\\
&= - \beta_0 + \limn \frac{\sumn{i} (X_i - \Xbar_n)(Y_i) }{\sumn{i}[X_i - \Xbar]^2} + \limn \frac{- \Ybar_n\sumn{i} (X_i - \Xbar_n) }{\sumn{i}[X_i - \Xbar]^2}\\
&= \limn \frac{n\inv\sumn{i} (X_i - \Xbar_n)(Y_i) }{n\inv\sumn{i}[X_i - \Xbar]^2} - \frac{\beta_0 n\inv\sumn{i}[X_i - \Xbar]^2}{n\inv\sumn{i}[X_i - \Xbar]^2} \text{ since }\sumn{i}(X_i-\Xbar_n) \to 0\\
\end{align}$$

Now take the numerator: 

$$\begin{align}
\limn n\inv\sumn{i} (X_i - \Xbar_n)(Y_i) - \ldots &= \limn n\inv\sumn{i} (X_i - \Xbar_n)(X_i\beta_0 + U_i) - \beta_0 n\inv\sumn{i}[X_i - \Xbar]^2\\
&= \limn n\inv\sumn{i} (X_i - \Xbar_n)(X_i\beta_0 + U_i) - n\inv\sumn{i}[X_i - \Xbar][X_i\beta_0 - \Xbar\beta_0]\\
&= \limn n\inv\sumn{i} (X_i - \Xbar_n)(X_i\beta_0) + \sumn{i} (X_i - \Xbar_n)U_i - n\inv\sumn{i}[X_i - \Xbar][X_i\beta_0] +n\inv \sumn{i}[X_i - \Xbar][\Xbar\beta_0]] \\
&=\limn n\inv\sumn{i} (X_i - \Xbar_n)(X_i\beta_0) + \sumn{i} (X_i - \Xbar_n)U_i - n\inv\sumn{i}[X_i - \Xbar][X_i\beta_0] \text{ since }\sumn{i}(X_i-\Xbar_n) \to 0\\ 
&=\limn n\inv \sumn{i} (X_i - \Xbar_n)U_i \\ 
&=\limn n\inv \sumn{i} (X_i - \mu)U_i + n\inv \sumn{i} (\Xbar_n - \mu)U_i \\ 
&= \limn n\inv \sumn{i} (X_i - \mu)U_i \text{ because } \Xbar_n -\mu \to_d 0\\ 
\end{align}$$
#status/section/🚧 
