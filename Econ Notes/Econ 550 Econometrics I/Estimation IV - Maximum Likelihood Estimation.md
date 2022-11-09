---
aliases:
creation date: Monday, November 7th 2022, 12:41 pm
date updated: Wednesday, November 9th 2022, 1:45 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation IV - Maximum Likelihood Estimation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]
A more mathematical treatment of [[2001.6 Likelihood Inference]].


## Basics

The MLE method requires picking a <font color=gree>parametric family</font> of distributions, $\mathcal F = \{f_Y(y; \theta):\theta \in \R^k\}$. In other words, same densities up to some parameter(s) $\theta$. For instance, $N(\mu, \sigma^2)$ is a parametric family (with $\theta = [\mu, \sigma]$; members of this family are $N(0,1), N(12.2, 40)$ etc. 

We observe a <font color=gree>sample</font>, $n$ i.i.d $Y_i$s, all drawn from the same $f_Y$. By independence, they have a joint density: 
$$ f_{Y_1, \ldots, Y_n} = \prod_{i=1}^Nf_Y(Y_i; \theta)$$
For any given sample $Y_i$, we can then say there is some unknown joint density from which this sample was drawn. We can call this the Likelihood function: 
$$ \mathcal L(\theta|Y_1 = y_1, \ldots, Y_n = y_n) = \prod_{i=1}^Nf_Y(\theta|Y_i = y_i)$$
For convenience we can call this $\mathcal L(\theta; \underline y)$. Maximizing this likelihood function over all $\theta \in \Theta$ gives us the value $\theta_{MLE}$ that is most likely (by definition; the word is used particularly here) to have generated our data. 

We can maximize the log-likelihood instead, since log is a strictly increasing transformation. 
$$\log \mathcal L(\theta; \underline y)= \sum_{i=1}^N \log f_Y(y_i;\theta)$$

We'll have some FOCs: 
$$0 = \frac{d}{d\theta} \sumn{i} \log f_Y(y_i;\theta)$$
### Example

Suppose I have the linear regression parametric family; that is, $Y_i$ are iid, with 

$$ Y_i \sim N(\alpha + \beta x_i, \sigma^2)$$
where $x_i$ are distributed according to some joint density $g(x_1, \ldots, x_n)$ that's independent of $Y$. Now we want a conditional joint density of $Y_i|X$; then

$$\begin{align}
\mathcal L(y_i|x_i;\theta) &= \prod_{i=1}^n \frac{1}{\sqrt{2\pi\sigma^2}}\exp\left[-\frac{1}{2}\frac{y_i - (\alpha + \beta x_i)}{\sigma^2}\right]\\
\log \mathcal L(y_i|x_i;\theta) &= \sumn{i} \log \frac{1}{\sqrt{2\pi\sigma^2}}\exp\left[-\frac{1}{2}\frac{y_i - (\alpha + \beta x_i)}{\sigma^2}\right]\\
&= \sumn{i} \left[-\frac{1}{2}\frac{y_i - (\alpha + \beta x_i)}{\sigma^2}\right] + 1/2\log 2\pi + \log \sigma\\
&= n/2\log 2\pi + n \log \sigma -\frac{1}{2\sigma^2}\sumn{i}y_i - (\alpha + \beta x_i) \\
\end{align}$$
