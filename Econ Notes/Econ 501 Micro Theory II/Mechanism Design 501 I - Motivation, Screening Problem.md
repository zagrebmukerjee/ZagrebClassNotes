---
aliases:
creation date: Saturday, April 8th 2023, 12:13 pm
date updated: Saturday, April 8th 2023, 1:44 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Mechanism Design 501 I - Motivation, Screening Problem]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Basic Form

From [[Fudenberg and Tirole 1991 Game Theory|Fudenberg and Tirole 1991]].

Suppose a monopolist faces one consumer, and has to decide what to produce (at cost $c$) and charge. The consumer's utility takes the form $\theta V(q) - T$ where $V'>0$, $V''<0$, $T$ is a transfer to the seller, and $\theta$ is some constant. Then the monopolist faces a simple problem. Charge $T = \theta V(q)$. The profit maximization is $\theta V(q) - cq$; so $\theta V'(q) = c$ gives profit maximizing $q$. 

But suppose that information is imperfect so that the consumer is type $\overline \theta$ with probability $\bar p$ and $\underline \theta$ with probability $\underline p$. with $\overline \theta > \underline \theta$. The monopolist then has to produce a price schedule detailing bundles $\overline q, \overline t$ and $\underline q, \underline t$ for the consumer to choose between. $q = T = 0$ is always a choice also.

The goal of the monopolist is to maximize expected profit, which is $\bar p (\overline t - c \overline q) + \underline p (\underline t - c\underline q)$. 

This takes the form of a constrained optimization, with four constraints. The first two are that both types of consumers should want to make a positive purchase: 

$$\begin{align}
\underline \theta V(\underline q) - \underline t \geq 0\\
\overline \theta V(\overline q) - \overline t \geq 0 \\
\end{align}$$

Call these $IR_1$ and $IR_2$ where $IR$ means individually rational - it's individually rational to participate. 

Then the other two constraints are that consumers should buy the bundle intended for them; the high-type shouldn't prefer the low-type bundle and vice versa. 

$$\begin{align}
\underline \theta V(\underline q) - \underline t &\geq \underline \theta V(\overline q) - \overline t \\
\overline \theta V(\overline q) - \overline t &\geq \overline \theta V(\underline q) - \underline t \\
\end{align}$$
Call these $IC_1$ and $IC_2$ for Incentive Compatibility, ie it's incentive compatible to 'report' your type; $IC_1$ says low type doesn't want to pretend to be high, and $IC_2$ that high type doesn't want to pretend to be low. 

So what do these constraints entail? Specifically, which ones bind with equality at the maximizer? At least one of $IR_1, IR_2$ must bind; otherwise, the monopolist could increase at least one of the $T$s a tiny amount (which one depending on the IC constraint) to extract more of the consumer surplus. Similarly, at least one of $IC_1$ and $IC_2$ must bind, otherwise the monopolist could charge someone a tiny bit more without making them switch. 


Suppose $IR_1$ does not bind; then the low type consumer would be obtaining positive utility: $\underline \theta V(\underline q) - \underline t > 0$. But then, apply $IC_2$; 

$$\begin{align}
\underline \theta V(\underline q) - \underline t &> 0\\
\overline \theta &> \underline \theta\\
\overline \theta V(\underline q) - \underline t  &> \underline \theta V(\underline q) - \underline t\\
\overline \theta V(\overline q) - \overline t  &\geq \overline \theta V(\overline q) - \overline t\\
\overline \theta V(\overline q) - \overline t &> 0\\
\end{align}$$

This contradicts the above, meaning that $IR_1$ must bind in maximization. The intuition is that $\overline \theta > \underline \theta$, meaning that the marginal unit is better for the high type. So if there's some bundle for the low type that gives him positive utility, the high type could also consume that bundle for positive utility; and the incentive-compatibility means that his bundle must give him at least as much utility as that. 

The binding of $IR_1$ lets us say that $\underline t = \underline \theta V(\underline q)$.

$IC_1$ is somewhat hollow. The low type consumer gets utility $0$ from participation, by $IR_1$ binding. So if $IC_1$ binds then the low type consumer gets $0$ utility from both bundles since he is indifferent. But the indifference curve for the high type is steeper. $IC_2$ implies that they weakly prefer the high type bundle, so the indifference curve that crosses at the low type bundle must lie above at the high type, meaning that the monopolist is undercharging. So $IC_2$ must bind. A pictorial illustration: 

![[Mechanism Design 501 Ia - Motivating Example 2023-03-16 14.45.11.excalidraw]]

Since $IC_2$ binds:
$$
\begin{aligned}
\overline \theta V(\overline q) - \overline t &= \overline \theta V(\underline q) - \underline t\\
\overline t &= \overline \theta V(\overline q) - \overline \theta V(\underline q) + \underline t\\
&= \overline \theta V(\overline q) - \overline \theta V(\underline q) + \underline \theta V(\underline q)\\
\end{aligned}
$$

In other words, the fact that the constraints bind allows the transformation of the profit-maximizing problem into one of only choosing quantities.

$$\begin{align}
\pi &= \bar p (\overline t - c \overline q) + \underline p (\underline t - c\underline q)\\
&= \bar p (\overline \theta V(\overline q) - \overline \theta V(\underline q)  + \underline \theta V(\underline q) - c \overline q) + \underline p (\underline \theta V(\underline q) - c\underline q)\\
d\pi/d\overline q &= \overline p(\overline \theta V'(\overline q) - c)\\
V'(\overline q) &= \overline p c/\overline \theta \\ 
d\pi/d\underline q &= \overline p (\underline \theta - \overline \theta  )V'(q) + \underline p (\underline \theta V'(\underline q) - c)\\
V'(\underline q) &= \frac{\underline p c}{
\overline p (\underline \theta - \overline \theta  ) + \underline p \underline \theta}
\end{align}$$

## Continuous Form

Suppose now a continuum of types $\theta$ distributed according to df $F$ with support $[\underline \theta, \overline \theta]$. The monopolist chooses $p: Q \to \R$, and the buyer solves 
$$\max_{q \geq 0} \max \{\theta v(q) - p(q),0 \}$$ where $0$ represents an outside option. The [[Mechanism Design 501 III - Revelation Principle|Revelation Principle]] allows the monopolist's problem to become one of inducing type revelation: 

$$ \max_{q: \theta \to \R; \; t: \theta \to \R} \int_{\underline \theta}^{\overline \theta} [t(\theta) - c(q(\theta))] f(\theta) d\theta$$
subject to $IC$ and $IR$ constraints. For convenience, create the following notation:  <font color=#F7B801>Is this interim utility</font>
$$U(\theta): \theta V(q(\theta)) - t(\theta)$$
for the utility of a consumer when they truthfully report their own type. So then the IC constraint is, as before, that no agent wants to pretend to be of another type. 

$$ \forall \theta \;, \forall \theta'\; U(\theta) \geq \theta V(q(\theta')) - t(\theta'))$$
The $IR$ or participation constraint is simply that $U(\theta) \geq 0 \; \forall \theta$. 

This is a very large problem and/or search space. To simplify, employ this lemma: 


### Lemma

$(q,t)$ satisfies $IC$ if and only if: 
1) q is nondecreasing, and 
2) $\forall \theta,\; U(\theta) = U(\underline \theta) + \int_{\underline \theta}^\theta V(q(x)) dx$. This latter is the 'Envelope Formula' of [[Milgrom and Segal 2002 Envelope Theorems for Arbitrary Choice Sets|Milgrom and Segal 2002]]. 

The latter implies that 
$$ t (\theta) = t(\underline \theta) - \theta v(q(\underline \theta)) + \theta v(q(\theta)) - \int_{\underline \theta}^\theta V(q(x)) dx$$
This is a cumbersome formula but lets us say that the transfer schedule is pinned down by the lowest transfer and the quantity schedule, which greatly reduces the dimensionality of the problem.  <font color=#F7B801>What is the intuition?</font>

#### Proof
Conditions imply IC: Suppose we have the conditions. Assume without loss that $\theta > \theta'$. 
$$\begin{align}
U(\theta) - \theta V(q(\theta')) - t(\theta') &= U(\theta) - U(\theta') +(\theta' - \theta)V(q(\theta'))\\
&= \int_{\theta'}^{\theta} V(q(x)) dx + (\theta - \theta')V(q(\theta'))\\
\end{align}$$
Both the integral term and the difference are positive; hence, IC is satisfied. 

$IC$ implies conditions: 
$IC$ implies that $U(\theta)$ is the maximized utility, $\max_{\theta'} \theta v(q(\theta')) - t(\theta')$. Can check that this is convex and absolutely continuous maximization problem. If differentiable, $U'(\theta) = V(q(\theta))$, so $U(\theta) = \int V(q(\theta)) + C$ which establishes the conditions <font color=#F7B801>how?</font>

### Applying Lemma

Returning to the screening problem, the lemma lets us pin down the screening problem more. Recall:

$$ \pi = \int_{\underline \theta}^{\overline \theta} (t(\theta) - c(q(\theta)) f(\theta) d\theta$$ 
such that $q$ is nondecreasing in $\theta$, and $U = U(\underline \theta) + \int \ldots$ as well as $U(\theta > 0$. Note: Given $IC$, $IR$/ participation constraint is satisfied iff $U(\underline \theta) \geq 0$. The $IR$ must bind for the lowest type. If it doesn't, it wouldn't break $IR$ to raise everyone's payment by a tiny amount (also keeping $IC$). So we have $U(\underline \theta) = 0$, simplifying the problem further: 

$$ U(\theta) = \int_{\underline \theta}^\theta V(q(x)) dx$$

In general, this is positive. We can think of this as the consumer managing to retain some of the consumer surplus - or, as the book/class calls it, 'information rent extracted by the buyer'. The tariff becomes 

$$ t(\theta) = \theta v(q(\theta)) - \int_{\underline \theta}^\theta v(q(x))dx$$ as a rearrangement of the lemma condition. Then the seller's problem can be written as a function of $q$ alone: 

$$ \max_{q \text{ non-decreasing}} \int_{\underline \theta}^{\overline \theta} f(\theta) \bigg(\theta v(q(\theta)) - \left[\int_{\underline \theta}^\theta v(q(x))dx \right]- c(q(\theta)) \bigg)d\theta$$
Rearranging finds a term $\int_{\underline \theta}^{\overline \theta} f(\theta) \int_{\underline \theta}^\theta v(q(x))dx d\theta$ which lends itself to integration by parts: let $u = \int v(q(x)) dx$ and $dv = f(\theta) d\theta$. Then 
$$\begin{align}
\int_a^b u dv &= uv\bigg |_{a}^{b} - \int_{a}^b v du\\
&= F(\theta)\int_{\underline \theta}^\theta v(q(x))dx \bigg|_{\theta = \underline \theta} ^{\overline \theta} - \int_{\underline \theta}^{\overline \theta}  F(x)v(q(x))dx\\
F(\theta)\int_{\underline \theta}^\theta v(q(x))dx \bigg|_{\theta = \underline \theta} ^{\overline \theta}&= F(\overline \theta)\int_{\underline \theta}^{\overline\theta} v(q(x))dx - F(\underline \theta)\int_{\underline \theta}^{\underline\theta} v(q(x))dx \\
&= \int_{\underline \theta}^{\overline\theta} v(q(x))dx \\
\int_{\underline \theta}^{\overline \theta} f(\theta) \int_{\underline \theta}^\theta v(q(x))dx d\theta &= \int_{\underline \theta}^{\overline\theta} v(q(\theta))(1- F(\theta))d\theta\\
\end{align}$$

Then: 

$$\begin{align}
\pi(q) &= \int_{\underline \theta}^{\overline \theta} f(\theta) \bigg(\theta v(q(\theta)) - \left[\int_{\underline \theta}^\theta v(q(x))dx \right]- c(q(\theta)) \bigg)d\theta\\
&= \int_{\underline \theta}^{\overline \theta} f(\theta)\bigg(\theta v(q(\theta))- c(q(\theta)) \bigg)d\theta - \int_{\underline \theta}^{\overline \theta}  f(\theta)\left[\int_{\underline \theta}^\theta v(q(x))dx \right]d\theta\\
&= \ldots -\int_{\underline \theta}^{\overline\theta} v(q(\theta))(1- F(\theta))d\theta\\
&= \ldots  -\int_{\underline \theta}^{\overline\theta} f(\theta)v(q(\theta))\left(\frac{1- F(\theta)}{f(\theta}\right)d\theta\\
&= \int_{\underline \theta}^{\overline\theta} f(\theta) \left[ v(q(\theta)) \left(\theta - \frac{1- F(\theta)}{f(\theta} \right)- c(q(\theta) \right] \\
&=  \int_{\underline \theta}^{\overline\theta} f(\theta) \left[ v(q(\theta)) \psi(\theta)- c(q(\theta) \right] \\
&= E_\theta[v(q(\theta)) \psi(\theta)- c(q(\theta)]\\
\end{align}$$

In other words, the monopolist has to maximize considering this $\psi(\theta)$, called the <font color=gree>virtual type</font>. Then we can conceive of this as a social surplus plus a distortion term. In other words, rewriting an equation from above: 

$$\begin{align}
\pi &=  \int_{\underline \theta}^{\overline \theta} f(\theta)\bigg(\theta v(q(\theta))- c(q(\theta)) \bigg)d\theta - \int_{\underline \theta}^{\overline \theta}  f(\theta)\left[\int_{\underline \theta}^\theta v(q(x))dx \right]d\theta\\
&= \underbracket{E_\theta\bigg[\theta v(q(\theta))- c(q(\theta)) \bigg]}_\text{Social surplus} - \underbracket{E_\theta\left[\int_{\underline \theta}^\theta v(q(x))dx \right]}_\text{Distortion Term}\\
\end{align}$$

### Solving the Problem 

To solve this, assume that $\psi(\theta)$, the virtual type, is nondecreasing in $\theta$. In other words, we want $\frac{1 - F(\theta)}{f(\theta)}$ to be nonincreasing, or $\frac{f(\theta)}{1 - F(\theta)}$, the <font color=gree>hazard rate</font>, to be nondecreasing. It turns out this is not so bad of a condition. 