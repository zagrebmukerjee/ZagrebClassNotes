---
date updated: 2022-04-07 20:34

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/stats/causalinf'
- '#topics/methods/quant/causalinf'
---

# [[Confounding]]


Let's borrow the notation from the [[Basic Causal Model]]; $D = 1$ if treated and $0$ if not; $Y_1$ is the outcome if treated, $Y_0$ if not. 

Say we want to compute the SATE, the sample average treatment effect (setting aside sampling concerns for now).
$$ \alpha_0 =  E[Y_1 - Y_0]$$
We suffer from the fundamental problem of causal inference. We can't directly observe $E[Y_1 - Y_0|D=0]$, what the treatment effect is for the untreated. So what can we observe? Say we observe a difference between treatment and control groups:
$$E[Y_1|D = 1] - E[Y_0|D=0]$$Is this enough? We can collapse this to $\alpha_0$ if we can say that $\alpha_0$ and $D$ are independent: $E[Y_1 - Y_0|D] = E[Y_1 - Y_0]$. 

A confounder is something that causes this assumption to be violated. A simple example: suppose a dichotomous variable $v$ with distribution as follows:
$$ 
v = 
\begin{cases}
0 & \text{with probability} & 2/3\\
1 & \text{with probability} & 1/3\\
\end{cases}
$$
So $E(v) = 1/3$. Let $Y_0 = \mu$, $Y_1 = \mu + \eta(v)$, where $$\eta(v) = \begin{cases} \eta_0 & v = 0 \\ \eta_1 & v = 1\end{cases} $$
So we can calculate the treatment effect, using the law of total probability:

$$
\begin{aligned}
\alpha_0 &= E[Y_1 - Y_0] \\
&= P(v=1)E[Y_1 -Y_0| v =1 ] + P(v=0)E[Y_1 -Y_0| v =0 ] \\
&= (2/3)\eta_0 + (1/3)\eta_1\\
\end{aligned}
$$
Note: If $E[D|v=1] = E[D|v = 0] = E[D]$ then we're still OK! Our treatment and control groups will be balanced for $v$.

But if it's not? How unbalanced will it be? Well, let's describe the relationship between $v$ and $D$ as follows:
$$ P(D = 1|v) = \begin{cases} 
3/7 & \text{when} &  v= 0 \\
5/7 & \text{when} &  v= 1 \\
\end{cases}
$$
$$
P(D = 0|v) = \begin{cases} 
4/7 & \text{when} &  v= 0 \\
2/7 & \text{when} &  v= 1 \\
\end{cases}$$
So what is the composition of our treatment group in terms of $v$? Bayes' rule helps:

$$
\begin{aligned}
P(v = 1|D = 1) &= \frac{P(v = 1)}{P(D=1)}P(D= 1|v = 1)\\
&= \frac{P(v=1)}{P(v=1)P(D=1|v=1) + P(v=0)P(D=1|v=0)}\\
&\qquad \times P(D= 1|v = 1)\\
&= \frac{1/3}{(1/3)(5/7) + (2/3)(3/7)}(5/7)\\
&= \frac{7/21}{11/21}(5/7) \\
&= 5/11
\end{aligned}
$$

Now we have a problem with our treatment vs control estimator. Let's apply the LTP some more:

$$
\begin{aligned}
E[Y_1|D = 1] &= P(v=1|D=1)E[Y_1|D = 1,v=1] \\
& \qquad + P(v=0|D=1)E[Y_1|D = 1,v=0]\\
&= (5/11) (\mu + \eta_1) + (6/11)(\mu + \eta_0)\\
E[Y_1|D = 1] - E[Y_0|D = 0] &= (5/11)\eta_1 + (6/11)\eta_0\\
&\neq (2/3)\eta_0 + (1/3)\eta_1 \\
\end{aligned}
$$


