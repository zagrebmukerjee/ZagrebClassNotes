---
aliases:
creation date: Monday, December 5th 2022, 1:59 pm
date updated: Monday, December 5th 2022, 5:19 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium V - Limitations]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

We found certain conditions under which we can have existence and uniqueness of Walrasian equilibria. Can I say anything more? The main result here is no. Specifically, any demand function meeting the described assumptions can be represented as the excess demand of some economy. This result is the Sonneschein-Mantel-Debreu Theorem and is demonstrated in several steps. 

#status/section/🚧 



How can we extend what we've said about excess demand? Specifically, can we restrict $D_z(p)$, the matrix of derivatives of $z$ with respect to prices? We will use the old tricks of totally differentiating some things

First, we have the property that $z$ is homogeneous of degree $0$ in prices. In other words, 

$$\begin{align}
z(\alpha p) &= z(p) \\
z(\alpha p_1, \alpha p_2, \alpha p_3, \ldots) &= z(p_1, p_2, \ldots)\\
dz/d\alpha &= 0\\
&= \sum_{i=1}^L p_i \frac{dz}{dp_i}\\
&= D_z(p) \cdot p
\end{align}$$

So $D_z(p) p = 0$. 

We also have an identity in Walras' Law: 
$$\begin{align}
\sum_{\l = 1}^L p_\l x_{\l i}&= \sum_{\l = 1}^L p_\l \omega_{\l i} \\
0 &= \sum_{\l = 1}^L p_\l x_{\l i} - \sum_{\l = 1}^L p_\l \omega_{\l i} \\ 
0 &= \sum_{\l = 1}^L p_\l \left[ x_{\l i} - \omega_{\l i} \right]\\
0 &= \sum_{\l = 1}^L p_\l z_\l(p)\\
\end{align}$$

This holds for all $p$. So we can fix some $\l$ in particular and totally differentiate: 
$$
\begin{align*}
0 &= z_\l(p) + \sum_{k \neq \l} p_k \frac{dz_k}{dp_\l}\\
-z_\l(p) &= \sum_{k \neq \l} p_k \frac{dz_k}{dp_\l}\\ 
\end{align*}
$$

We also have the definition of $z(p)$:
$$\begin{align}
z(p) &= \sum_i (x_i(p, p\omega_i) - \omega_i)\\
Dz(p) &= \sum_i \frac{d}{dp}x_i(p, p\omega_i)\\
&= \sum_i D_px(p)+ D_wx(p) \omega_i '\\
&= \sum_i [S_i(p, p \omega_i) - D_w x_i(p,p\omega_i) x_i(p, p\omega_i)']+ D_wx(p) \omega_i '\\
&= \sum_i [S_i(p, p \omega_i) - (D_w x_i(p,p\omega_i) x_i(p, p\omega_i)']- D_wx(p) \omega_i')\\
&= \sum_i [S_i(p, p \omega_i) - D_w x_i(p,p\omega_i) (x_i(p, p\omega_i) - \omega_i)']\\
&= \sum_i [S_i(p, p \omega_i) - D_w x_i(p,p\omega_i) z_i(p)']\\
\end{align}$$

from the usual Slutsky result. 

So $Dz(p)$ is 'almost' negative semidefinite, since $S_i$ is. How big of a deal is $-D_w x_i z_i(p)'$? Writing out the matrix for one consumer reveals linear dependence: 

$$\begin{bmatrix} 
\frac{dx_1}{dw}z_1(p)& \cdots &\frac{dx_1}{dw}z_L{p}\\
\vdots \\
\frac{dx_L}{dw}z_1(p)& \cdots & \frac{dx_L}{dw}z_L{p}\\
\end{bmatrix} $$

First row is different multiples of $dx_1/w$, second of $dx_2/w$, and so on. Alternatively, first column is multiples of $z_1$, second of $z_2$. This makes sense: we took the product of a column vector and a row vector, so we cannot have rank > 1. 

What can we learn from this? It means that for $I < L$ (why) there will be NSD ish properties. 

### Proposition 1: I < L

If $I < L$ then for $p \in E$ (set of equilibria) there will be some vector of price changes $dp$ such that $p\cdot dp = 0$. 

#### Proof
$\sum z_i(p) = 0$; so the $I$ $z$ values and $p$ have only $I$ linear independent vectors. So, since $I < L$ there must be some $dp \in \R^L$ such that $p \cdot dp = 0$, and $dp Dz(p) dp \leq 0$, which is NSD enough for us. 

Then, using the above, we have that 

$$\begin{align}
z(p) dp &= 0\\
Dz(p) &= \sum_i [S_i(p, p \omega_i) - D_w x_i(p,p\omega_i) z_i(p)']\\
dp Dz(p) dp &= \sum_i [dp S_i(p, p \omega_i)dp' - dp D_w x_i(p,p\omega_i) z_i(p)'dp ]\\
dp Dz(p) dp &= \sum_i [dp S_i(p, p \omega_i)dp' - dp D_w x_i(p,p\omega_i) (0)]\\
&= \sum_i dp S_i(p, p\omega_i) dp' \\
\end{align}$$


### Proposition 2: I $\geq$ L

If $I \geq L$ this is no good. If $z \in \R^L$ an arbitrary vector, and $A$ an arbitrary $L \times L$ matrix, with $pz = 0, Ap = 0, pA = -z$. Then there are $L$ consumers generating aggregate excess demand $z$ such that $z(p) = z$ and $Dz(p) = A$. 

#### Proof

We can find one with the restriction that $S_i(p, p\omega_i) = 0$. Write $A = \sum e'a'$, where $e'$ are unit vectors, and $a'$ are the rows. 

We can then make $L$ consumers that have, given $p$, $z_i(p) = -p_i (a_i)'$ (the row corresponding to that customer). Wealth effects are $(1/p_i)e_i'$, and $S_i = 0$. Then $z(p) = \sum z_i(p) = -\sum p_i (a_i)'$. 

What does that look like? 

$$ -\sum p_i a_i = - \sum p_i \begin{bmatrix} a_{11} \\ \vdots \\ a_{1L}
\end{bmatrix} = -\begin{bmatrix} p_1 a_{11} + p_2 a_{21} + p_3 a_{31} + \ldots \\
\vdots \\
p_L a_{1L} +p_L a_{2L} + p_3 a_{3L} + \ldots
\end{bmatrix} =- A'p = -pA = z$$
