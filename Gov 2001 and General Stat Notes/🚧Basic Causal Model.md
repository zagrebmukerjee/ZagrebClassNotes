---
date updated: 2021-12-27 13:06

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes'
- '#🚧'
---

# [[🚧Basic Causal Model]]

Drawing on [[🚧Angrist and Imbens 1991 Identification and Estimation of Local Treatment Effects]]



### Causal model:
$Y_0$ and $Y_1$ are outcomes if untreated/treated. $D$ is indicator for treatment. We observe $D$ and $Y = Y_D = D\cdot Y_1 + (1-D)\cdot Y_0$; that is to say, for each observation we see $Y_1$ if treated and $Y_0$ if not. 

We are interested in effect of treatment. Obstructed by the  the _fundamental problem of causal inference_: can never observe $Y_1-Y_0$ for the same observations, i.e. the counterfactual.

Proxy counterfactual with other observations - compute average treatment effects. 

One variable of interest: 
$$\alpha_0 = E[Y_1-Y_0]$$
Average treatment effect for the whole population. 

Can we measure this from a sample with the sample's ATE? Not necessarily:

$$E[Y_1|D=1] - E[Y_0|D = 0]$$

Doesn't become $E[Y_1-Y_0]$ unless treatment is independent of other covariates. (e.g. people can self-select into experimental medication). So $Y_1$ and $D$ are not independent.

Also can be interested in ATT: average treatment effect on the treated. Which is $E[Y_1 - Y_0|D=1]$. Also hard to observe without counterfactual. 

### Randomization

Randomization lets us have sample ATE be good estimate of population ATE. If participants in a medical trial are randomly assigned treatment then 
$$E[Y_i|D=0] = E[Y_i|D=1]$$
since we have accounted for both known and unknown factors creating dependence between $Y$ and $D$. 


We can use instrumental variables. Let $Z$ be an IV unrelated to $Y_0$ and $Y_1$ but correlated to $D$. 

Let $\{z_1, \ldots, z_K\}$ be the support of $Z$. For each of the $z$, define $D_z$, which is $0$ if $Z=z$ leads to non-participation, and $1$ if $Z=z$ means participation. We can't see $\{D_{z_1}, \ldots, D_{z_K} \}$ but assume it exists. 

We can see $Z, D, Y$ for a random sample, where 
$$D = D_z = \sum D_{z_K} \cdot (Z=z)$$ 
and 
$$Y = D\cdot Y_1 + (1-D)\cdot Y_0$$
as before. 

There are three conditions for an instrument. 

##### Condition 1: Existence of a valid instrument. 
$Y$ and $D$ are jointly independent of $Z$, and $P_z = E[D|Z=z] = E[D_z]$ is a nontrivial function of $z$. 

By using $Z$ as a proxy for $D$ we can address the endogeneity of treatment assignment. But we still have the problem of treatment effect heterogeneity:

Let 
$$Y_0 = \varepsilon$$
$$Y_1 = Y_0 + \eta$$
$$D_z = h(z,v)$$
where $(\varepsilon, \eta, v)$ are jointly independent of $Z$. 

Suppose treatment effect is constant: $Var(\eta) = 0$; then regression of $Y$ on $1 + P_z$ estimates $\eta$. 

But suppose it isn't? 

Let $Z$ be binary. Let's introduce covariate $v$.

Define
$$Pr(v) = \begin{cases} 
2/7 \; \text{that} \; x =0 \\
4/7 \; \text{that} \; x =1 \\
1/7 \; \text{that} \; x =2 \\
\end{cases}$$

$Y_0$ varies with the covariate:
$$E(\varepsilon|v) = \begin{cases} 
1 \; \text{if} \; v =0 \\
5/2 \; \text{if} \; v =1 \\
0 \; \text{if} \; v =2 \\
\end{cases}$$

Treatment effect does too
$$E(\eta|v) = \begin{cases} 
1 \; \text{if} \; v =0 \\
1 \; \text{if} \; v =1 \\
2 \; \text{if} \; v =2 \\
\end{cases}$$

Given the probabilities of $v$ we can compute a 'true' average treatment effect:
$$ \begin{aligned}
\alpha_0 &= \sum_{v_i}Pr(v = v_i)E(\eta|v = v_i) \\
&= \frac{2}{7}E(\eta|v = v_i) + \frac{4}{7}E(\eta|v = 1) + \frac{1}{7}E(\eta|v = 2) \\
&= \frac{2}{7} + \frac{4}{7} + \frac{2}{7} \\
&= \frac{8}{7} \\
\end{aligned}$$

Let $h(\cdot,\cdot)$ be such that:
$$h(1,0) = h(0,2) = 1$$
$$ h(0,0) = h(0,1) = h(1,1) = h(1,2) = 0$$

What is probability of participation, $E(D)$, conditional on $z$?
$$ \begin{aligned}
E(D|z=1) &= E(h(z,v)|z=1) \\
&= E(h(1,v))\\
&= \sum_{v_i} Pr(v = v_i)h(1,v_i)\\
&= \frac{2}{7}h(1,0) + \frac{4}{7}h(1,1)  + \frac{1}{7}h(1,2) \\
&= \frac{2}{7}(1) + \frac{4}{7}(0)  + \frac{1}{7}(0) \\
&= \frac{2}{7} \\
\end{aligned}$$

$$ \begin{aligned}
E(D|z=0) &= E(h(z,v)|z=0) \\
&= E(h(0,v))\\
&= \sum_{v_i} Pr(v = v_i)h(0,v_i)\\
&= \frac{2}{7}h(0,0) + \frac{4}{7}h(0,1)  + \frac{1}{7}h(0,2) \\
&= \frac{2}{7}(0) + \frac{4}{7}(0)  + \frac{1}{7}(1) \\
&= \frac{1}{7} \\
\end{aligned}$$

Now what is $E(Y|D,Z)$? 

If $Z = 0$, then:

$$ \begin{aligned}
E(Y|Z = 0) &= E(\varepsilon + \eta \cdot D|Z = 0)\\
&= E(\varepsilon|Z=0) + E(\eta \cdot D|Z = 0) \\
E(\varepsilon|Z=0) &= E(\varepsilon) \\ 
&= \sum_{v_i} Pr(v_i)E(\varepsilon|v = v_i)\\
&= \frac{2}{7}(1) + \frac{4}{7}(\frac{5}{2}) + \frac{1}{7}(0)\\
&= \frac{12}{7}\\
 E(\eta \cdot D|Z = 0) &= \sum_{v_i} Pr(v_i)E(\eta \cdot D|v = v_i) \\
 &= \frac{2}{7}(1\cdot h(0,0)) + \frac{4}{7}(1\cdot  h(0,1)) \\ 
 & \qquad + \frac{1}{7}(2\cdot h(0,2))\\
 &= \frac{2}{7}\\
Y &= (\varepsilon|Z=0) + E(\eta \cdot D|Z = 0) \\
&= \frac{12}{7} + \frac{2}{7} \\
&= 2 \\
\end{aligned}
$$

If $Z = 1$, then:

$$ \begin{aligned}
E(Y|Z = 1) &= E(\varepsilon + \eta \cdot D|Z = 1)\\
&= E(\varepsilon|Z=1) + E(\eta \cdot D|Z = 1) \\
E(\varepsilon|Z=1) &= E(\varepsilon) \\ 
&= \sum_{v_i} Pr(v_i)E(\varepsilon|v = v_i)\\
&= \frac{2}{7}(1) + \frac{4}{7}(\frac{5}{2}) + \frac{1}{7}(0)\\
&= \frac{12}{7}\\
 E(\eta \cdot D|Z = 1) &= \sum_{v_i} Pr(v_i)E(\eta \cdot D|v = v_i) \\
 &= \frac{2}{7}(1\cdot h(1,0)) + \frac{4}{7}(1\cdot  h(1,1)) \\ 
 & \qquad + \frac{1}{7}(2\cdot h(1,2))\\
 &= \frac{2}{7}\\
Y &= (\varepsilon|Z=0) + E(\eta \cdot D|Z = 0) \\
&= \frac{12}{7} + \frac{2}{7} \\
&= 2 \\
\end{aligned}
$$

When we change $Z$ from $0$ to $1$, the people with $v = 0$ enter the sample and the people with $v=2$ leave. That is OK if the treatment effect is constant because of the IV 🚧why?  But in the above case creates a problem


### IV example