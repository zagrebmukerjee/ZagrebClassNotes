---
aliases:
creation date: Thursday, March 16th 2023, 2:10 pm
date updated: Thursday, March 16th 2023, 2:43 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
---

# [[Mechanism Design 501 Ia - Motivating Example]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

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
\overline t &= \overline \theta V(\overline q) - \overline \theta V(\underline q)  + \underline t\\
&= \overline \theta V(\overline q) - \overline \theta V(\underline q)  + \underline \theta V(\underline q)\\
\end{aligned}
$$

In other words, the fact that the constraints bind allows the transformation of the profit-maximizing problem into one of only choosing quantities.

$$\begin{align}
\pi &= \bar p (\overline t - c \overline q) + \underline p (\underline t - c\underline q)\\
&= \bar p (\overline \theta V(\overline q) - \overline \theta V(\underline q)  + \underline \theta V(\underline q) - c \overline q) + \underline p (\underline \theta V(\underline q) - c\underline q)\\
d\pi/d\overline q &= \overline p(\overline \theta V'(\overline q) - c)\\
V'(\overline q) &= \overline p c/\overline \theta \\ 
d\pi/d\underline q &= \overline p (\underline \theta - \overline \theta  )V'(q) + \underline p (\underline \theta V'(\underline q) - c)\\

\end{align}$$