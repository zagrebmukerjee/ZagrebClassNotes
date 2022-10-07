---
aliases:
creation date: Monday, September 26th 2022, 10:58 am
date updated: Thursday, September 29th 2022, 4:00 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Micro Theory V - Welfare]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]


We've defined indirect utility in terms of parameters $p,w$. I might then want to ask: does a change in price make someone better or worse off? How much? comparative statics on $v$ will only get me ordinal or directional results: after all, utility functions are only unique up to strictly increasing transformations. 

Fortunately I have something else that's both measurable and an expression of utility (of sorts) - the expenditure function. Suppose price change from $p$ to $p'$. I can then ask: what is the expenditure associated with $v(p,w)$ vs with $v(p',w)$?

Annoyingly, that requires that I pick some $\bar p$ so I can compare $e(\bar p', v(p,w)) - e(\bar p, v(p,w))$. Even more annoyingly, picking different values results in different assessments. Two natural values are $p$ and $p'$. These produce two different measures:

## Compensating and Equivalent Variation, Consumer Surplus
### Equivalent Variation

The first measure is <font color=gree>Equivalent Variation</font>, which uses the old prices $p$. Define this as: 
$$ e(p, v(p',w)) - e(p, v(p,w)) = e(p, u') - e(p,u) = e(p, u')- w$$
In other words: how much less money would I spend to get the new utility under the old prices? Suppose the price of my favorite good has increased 10%. Then I will lose utility by having been made poorer, and mitigate that by substituting away from my favorite good.  

Use the new indifference curve, and find the point with the same slope as the old budget set. Draw the new budget set and then look at the impllied change in $w$.

### Compensating Variation

More intuitively there is <font color=gree>Compensating Variation</font>: 
$$ e(p', v(p',w)) - e(p', v(p,w)) = e(p', u') - e(p', u) = w - e(p', u_0)$$
Under the new prices how much more money do I need to get the old utility? If the price of my favorite good goes up by 10%, this will be less than that, because I can reach the old utility by a mix of increasing the income and substituting away. Alternatively, how much would I have to pay you to accept this change?  

Use the old IC, and find the point with the same slope as the new budget set. Draw that budget set and then look at implied change in $w$. 

### Relationship to Hicksian Demand
Suppose prices rise $p' > p$ for some good. Then my EV is:

$$\begin{align}
EV(p, p', w) &= e(p, u') - e(p, u) \\
&= e(p, u') - w \\
&= e(p, u') - e(p', u')\\
&= \int_p^{p'} h(t, u') dt
\end{align}$$
that is, the area under the Hicksian demand for that good given the new utility. 

My CV is 
$$\begin{align}
EV(p, p', w) &= e(p', u') - e(p', u) \\
&= w - e(p',u) \\
&= e(p, u) - e(p', u)\\
&= \int_p^{p'} h(t, u) dt
\end{align}$$
Note - since $p < p'$ and $e(p,u) \leq e(p',u)$ I've done a double sign flip on this one. 

Since $v(p,w)$ is weakly decreasing in price, we know $u' < u$. Suppose this good is normal; then $h(t, u')$ is less than $h(t, u)$ for all $t$. So the CV is less than the EV. 

### Consumer Surplus

In practice, nobody is compensating consumers for price changes, and so $h$ tends to be hard to observe ("economists are measuring the unmeasurable with units that don't exist"). We are stuck instead with observing the Marshallian demand $x$. So we can create a measure of convenience, the <font color=gree>consumer surplus</font>. Define this as:

$$ \int_p^{p'} x(t, w) dt$$ 
### Relationship of the Three

The Slutsky equation lets us bring these into relation with each other. Intuitively, the Marshallian falls more steeply with price rises for normal goods than the Hicksian, since the Marshallian drop is the Hicksian drop plus a negative income effect. 


For a normal good I know that $x\frac{dx}{dw} > 0$. So $\frac{dx(p,w)}{dp} = \frac{dh(p, v(p,w))}{dp} - x\frac{dx}{dw}$; so $\frac{dx(p,w)}{dp_i} < \frac{dh(p, v(p,w))}{dp}$. So as price rises by $dp$, $x(p,w)$ falls more than $h(p,v(p,w))$, and thus lies below it. 

We could reason backwards about $x(p', w)$ and $h(p', v(p',w))$. Before the price change $x(p, w)$ was higher than $h(p, v(p', w))$ since it captured both that good $\l$ was more attractive than other goods, and that the lower price made the consumer in effect wealthier. 

Since this is true for all price rises $dp$ we can establish that $$ \int_{\Delta p} h(p, u') dp \geq \int_{\Delta p} x(p, e(p,u')) dp \geq \int_{\Delta p} h(p, u) dp $$ with $\Delta p > 0$. So $CV < CS < EV$ (for price rise of a normal good). 

As the income effect becomes $0$ these quantities converge.


## Aggregation

When can we talk about aggregate $x(p,w)$ and aggregate CV, EV etc? The aggregate social demand is $x_1(p, w_1) + x_2(p, w_2) \ldots$. 

We want to say that there exists some "representative consumer" - a mega-consumer with demand function $x(p,w^*)$. We want this demand function to be identical to the aggregation of the individual demand functions. 

When can I do this?

Suppose I use $\sum w_i = w$. A natural candidate. For this to work requires that changes in the wealth distribution don't change aggregate demand. 

#status/section/🚧 


## Scratch

When I can have representative consumer

conditions:
- identical homothetic
- u_i(x) = u_i(x_{-l}) + x_l
- parallel, linear, wealth expansion paths - beware corner solns. 

also necess and suff: vi = ai p + bpw_i. Sufficiency follows from roy's identity. 


Suppose there is some rule, $w \to w_i$, ex weighted average $\lambda_iw_i$. Fix income shares, assume constant. THen, what happens as total income varies. 

Create $W$ that evaluates vectors of utilities $u_i$ for everyone. A bergson-samuelson social welfare fn - some function expressing your (analysts/planners/god's) preferences across aggregate utilities. <font color=#F7B801>whatever happened to social choice theory</font>



Result: 

If for all pw we have w(pw) \in arg max W(v_1 \ldots) 

then there is some representative consumer whose preference rationalizes x -db ie a marshallian demand function that is reasonable and depends only on aggregate income 
and whsose indirect utility is maximization of W

normative and psoitive interpretation (given norms in W)

Proof

first fix ui and xi of each i
then show v(pw) has properties of indirect utility:
- clearly h of d0 b/c vi are
- increasing in w, decreasing in p - requires that W be increasing
- quasiconvex - if W increasing
- continuous - obvs if w is continuous
