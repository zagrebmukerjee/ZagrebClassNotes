
## Basics

Let $Y^0_i$, $Y^1_i$ be 'potential' outcomes for the individual when not treated or treated respectively. Let $D_i$ be a treatment indicator. Only $D$ and an outcome $Y_i$ are observable. 

$$Y_i = D_i Y_i^1 + (1-D_i)Y_i^0$$
Suppose a basic framework. Each observation is some individual $\times$ one of two time periods, $T = 0$ and $T = 1$. There are two groups $G_i = 0, G_i = 1$. At time $0$ nobody is treated. At time 1, group 1 is treated. Then we can say $D_i = G_i T_i$. 

### Model

First, a linear model of outcomes in the absence of treatment

$$ Y_i^0 = \alpha + \beta T_i + \gamma G_i + \epsilon_i$$
The three coefficients represent three different types of effect. $\alpha$ is the constant, $\beta$ is the time effect, and $\gamma$ is the group effect. Note that time and group effects are separate. The error $\epsilon_i$ is assumed $\indep$ of $G_i, T_i$, and has mean $0$. 

Create an estimand for an average/expected treatment effect. 

$$ \tau_{\small{DID}} = \bigg[E(Y_i|G_i = 1, T_i = 1) - E(Y_i |G_i = 1, T_i = 0)\bigg] - 
\bigg[E(Y_i|G_i = 1, T_i = 1) - E(Y_i |G_i = 1, T_i = 0)\bigg]  $$
Consider the first term, using the proposed model: 
$$\begin{align}
E(Y_i|G_i = 1, T_i = 1) &= 
E(\alpha + \beta T_i + \gamma G_i + \epsilon_i + \tau_0|G_i = 1, T_i = 1) \\ 
&= \alpha + \beta E(T_i|G_i = 1, T_i = 1) + \gamma E(G_i|G_i = 1, T_i = 1) + E(\epsilon_i|G_i = 1, T_i = 1)\\
&= \alpha + \beta  + \gamma + E(\epsilon_i) \text{ using independence }\\
&= \alpha + \beta + \gamma \text{ since }E(\epsilon_i) = 0\\
\end{align}$$
Given the binary nature of $G_i$ and $T_i$, $\gamma$ and $\beta$ are fixed effects terms; $\gamma$, for instance, is a group 1 FE. Using the same logic for each of the other terms makes it clearer what is happening. 

$$\begin{align} \tau_{\small{DID}} &= \bigg[E(Y_i|G_i = 1, T_i = 1) - E(Y_i |G_i = 1, T_i = 0)\bigg] - 
\bigg[E(Y_i|G_i = 1, T_i = 1) - E(Y_i |G_i = 1, T_i = 0)\bigg] \\
&= \bigg[(\alpha + \beta + \gamma + \tau_0)  - (\alpha + \gamma + \tau_0) \bigg] -\bigg[(\alpha + \beta )  - (\alpha  ) \bigg] \\
&= \beta + \tau_0 - \beta\\
&= \tau_0\\
\end{align}$$
Intuitively, what's happening is the elimination of non-treatment influences in two steps. In the first step,  subtract "before" and "after" for the treatment group. This removes $\gamma$, the particular characteristics of the treatment group, and $\alpha$, leaving $\beta + \tau_0$. Take the same difference for the control group to isolate $\beta$, the time trend assumed to be the same across both groups; then use that $\beta$ to isolate $\tau_0$ from the first difference. 

The above interpretation is based on an assumption that $\tau$ is constant across individuals. But the concept can be generalized to give the expected treatment effect across individuals. 

#### Extensions

The independence assumption $\epsilon_i \indep T_i, G_i$ can be relaxed to mean independence ([[Abadie 2005 Semiparametric difference-in-differences estimators|Abadie 2005]]). The framework can be extended to 'changes in changes' estimators, per [[Athey and Imbens 2006 Identification and Inference in Nonlinear Difference-in-Differences Models|Athey and Imbens 2006]].
