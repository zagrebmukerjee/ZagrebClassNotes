---
aliases:
  - Elasticity
creation date: Wednesday, September 14th 2022, 2:34 pm
date updated: Monday, September 25th 2023, 11:20 am
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
---

# [[Micro Theory IIa - Elasticity]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

## Elasticity Basics

In utility maximization and other calculus problems we'll have quantities like $\frac{\partial x_i(p,w)}{\partial p_k}$. This tells you: if the price of good $k$ increases a tiny amount, how much more good $x_i$ will you demand? For normalization reasons, we might want this in percentage terms: If the price of good $k$ increases by $q \%$, by what percentage will demand for $x_i$ increase? 

We can get this by turning our 'tiny amounts' into 'tiny percentages':
$$\epsilon_{ik} = \frac{\partial x_i(p,w)}{x_i(p,w)} \big/ \frac{\partial p_k}{p_k} = \frac{\partial x_i(p,w)}{\partial p_k} \cdot \frac{p_k}{x_i(p.w)}$$Observing that $\frac{\partial}{\partial x} \log a(x) = a'(x)/a(x)$, we can transform this:

$$\epsilon_{ik} = \frac{\partial \log x_i(p,w)}{\partial \log p_k} $$
$\epsilon_{ik}$ is the <font color=gree>price elasticity</font> of good $i$ with respect to price $k$. If $i \neq k$, we can call this a cross-price elasticity of demand. 

With the same tool we can construct $\epsilon_{iw}$, the <font color=gree>income elasticity</font> of any given good: 

$$\epsilon_{iw} = \frac{\partial x_i(p,w)}{\partial w}\cdot \frac{w}{x_i(p,w)} = \frac{\partial \log x_i(p,w)}{\partial \log w} $$
## Marginal Rate of Substitution

Define the <font color=gree>marginal rate of substitution</font> as the number of units of $i$ required to compensate for a unit loss in good $j$. This is simply:

$$MRS_{ij} = \frac{MU_i}{MU_j}$$
the ratio of the marginal utilities of $i$ and $j$. We can think of this as the (negative) slope of the indifference curve. Thus, a concave indifference curve arises if $MU_i$ falls as $i$ rises, and/or $MU_J$ rises as $j$ falls (diminishing marginal utility); then as $j \to 0$, more and more of $i$ is required to substitute for $j$. 


## Elasticity of Substitution

Construct an <font color=gree>elasticity of substitution</font> by asking: 'how much does the ratio of goods demanded change when the relative prices change'? In other words, 

$$E_{ik} = \frac{\partial (x_i(p,w)/x_j(p,w))}{\partial(p_i/p_j)} \cdot \frac{p_i/p_j}{x_i(p,w)/x_j(p,w)} = \frac{\partial \log [x_j(p,w)/x_i(p,w)]}{\partial \log (p_1/p_2)}$$

The first-order conditions for utility maximization tell us that $p_1/p_2 = MU_i/MU_j = MRS_{ij}$. So we can also write: 

$$ E_{ik} = \frac{\partial \log [x_j(p,w)/x_i(p,w)]}{\partial \log MRS_{ij}}$$

The income elasticity can, I think, be expressed as a special case of the elasticity of substitution between good $i$ and the numeraire good/'money' with price $1$. 
