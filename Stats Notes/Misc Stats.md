---
date updated: 2021-10-05 21:02

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/stats'
---

# [[Misc Stats]]
Part of [[@Stats Index]]


#### Gary's Gamma Distribution

##### Wiki:
parameters $k$ shape, $\theta$ scale

PDF: 
$$ f(x) = \frac{x^{k-1}\exp(-x/\theta)}{\Gamma(k)\theta^k}$$
Mean: $k\theta$
Variance: $k\theta^2$

##### Gary's gamma

Mean: $\phi$
Variance: $\phi(\sigma^2-1)$
So $\phi = k\theta$, and $\phi(\sigma^2-1) = k \theta^2$. Substitute to get that $k \theta (\sigma^2-1) = k \theta^2$;  so $\theta = (\sigma^2 - 1)$. Returning to equation 1, then we have that $k = \phi/(\sigma^2-1)$

Substitute into the PDF to get 
$$ f(x) = \frac{x^{\frac{\phi}{(\sigma^2-1)}-1}\exp(-x/(\sigma^2 - 1))}{\Gamma( \phi/(\sigma^2-1))(\sigma^2 - 1)^{\phi/(\sigma^2-1)}}$$

Simplify:
$$ f(x) = \frac{x^{\phi(\sigma^2-1)^{-1}-1}\exp[-x(\sigma^2 - 1)^{-1}]}{\Gamma[ \phi/(\sigma^2-1)](\sigma^2 - 1)^{\phi(\sigma^2-1)^{-1}}}$$

So to use Gary's notation elsewhere: shape is $\phi/(\sigma^2-1)$ and scale is $(\sigma^2 - 1)$

