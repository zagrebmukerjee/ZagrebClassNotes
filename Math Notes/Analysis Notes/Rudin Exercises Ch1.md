---
aliases:
creation date: 2022-06-01 19:55
date updated: Sunday, June 5th 2022, 2:04 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/analysis'
---

# [[Rudin Exercises Ch1]]
[[Real Analysis Su and Rudin]]

1) ![[Pasted image 20220601195746.png]]

a) Suppose $r + x = q$ is rational. We write that $x = q - r$. But since the rationals are closed under addition, this would mean that $x$ is rational - a contradiction. 
b) Suppose $rx = q$ is rational. Then $r\inv q = x$.   But since the rationals are closed under multiplication, this would mean that $x$ is rational - a contradiction. 

2) ![[Pasted image 20220601200454.png]]

Suppose that $q \in \mathbb{Q}$ and $q^2 = 12$. Let $q = m/n$ with $m$ even and $n$ odd, or vice versa; Then $12 = m^2/n^2$; $12 n^2 = m^2$. Thus $m^2$ is even. Dividing by $4$ we find that $m^2/4 = 3n^2$; LHS is still even, RHS thus implies $n^2$ even, so a contradiction. 

3) prove 1.15:

![[Pasted image 20220601201116.png]]

a) Multiply: $x\inv x y = y$. Since $xy = xz$ then $x\inv xz = y$, but $x\inv x z = 1z = z$ so we have $y = z$
b) From above we have $xy = xz \to y = z$. Let $z = 1$; then $xy = x$ implies $y = 1$. 
c) $xy = 1$ means that $x\inv \cdot 1 = x\inv xy$, and from a) we have that  $x\inv$.
d) We know that $x\inv x = 1$. Then multiply by $x^{-1^{-1}} = 1/(1/x)$ to get that $x^{-1^{-1}} x\inv x = x^{-1^{-1}}$. But $x^{-1^{-1}} x\inv = 1$, so $x = x^{-1^{-1}}$. 

4) ![[Pasted image 20220601202526.png]]

4) Let $x \in E$ by nonemptyness. By definitions we have $\alpha \leq x \leq \beta$. 
5) Let $p = \inf A$. Then for all $x$ in $A$, $x \geq p$, which means $x - p \geq p - p = 0$. 

Suppose that there exists $x \in A$ such that $-p < -x$. Then $xp < x - x$, a contradiction. It follows that for all $x$ in $A$, $-p \geq -x$ 

Now suppose $-p$ is not the supremum of $-A$ - so there is a  $-q$ is such that $-q > -p$ and $-q \geq -x \; \forall x \in A$. 
Now we can say that $x - q \geq x - x = 0$, so then $x \geq q$ for all $x$ in $A$. 
From $-q > -p$ it follows that  $p - q > 0$, which means $q < p$. But combined with the above that means $p$ is not the infimum of $A$ - a contradiction. 

Since $-p$ is the supremum of $-A$, it follows that $\inf A = - \sup -A$. 


6) ![[Pasted image 20220601202725.png]]

a) We can write $m/n = k(p/q)$, and thus $m = kp$ and $n = kq$. 

Then write the LHS $(b^{kp})^{1/kq}$, which by the corollary to 1.21 we can write as $(b^{1/kq} )^{kp}$. Raise the LHS to the power of $q$ - from the commutativity of multiplication we can write this as $(b^{1/kq} )^{kpq}$, or $[b^{1/kq} )^{kq}]^p$. But we know that $(b^{kq})^{1/kq} = b$, by the definition and uniqueness of the roots (since $kq$ is an integer). So we have shown that the LHS raised to the power of $q$ is the RHS, which is the same as writing that $(b^m)^{1/n} = (b^p)^{1/q}$.

b) Let $r = a/b$, $s = c/d$ with $a,b,c,d$ integers. We can write $r + s$ then as $(ad + bc)/bd$. 
Then $\beta^{r + s}$ = $\beta^{(ad + bc)/bd}$. Then we can write $(\beta^{r+s})^{bd}$ as $\beta^{ad + bc}$. Since $ad$ and $bc$ are integers this is $\beta^{ad}\beta^{bc}$. So, using part a) and the corollary to 1.21:

$$\beta^{r+s} = [(\beta^{r+s})^{bd}]^{1/bd} = [\beta^{ad}\beta^{bc}]^{1/bd} = (\beta^{ad})^{1/bd}(\beta^{bc})^{1/bd} = \beta^{a/b}\beta^{c/d} = \beta^r\beta^s$$

c) 
- Let rational $\alpha > \beta$, with $\alpha = m/n$ and $\beta = p/q$, which means $mq > np$. Then $b^\alpha = b^{m/n} = b^{qm/qn} = (b^{qm})^{1/qn}$, so $(b^\alpha)^{qn} = b^{qm}$. Now $(b^\beta)^{qn} = (b^{p/q})^{qn} = b^{pn}$. So $(b^\beta)^{qn} = b^{pn} < b^{qm}$. Thus, if $\alpha > \beta$, $b^\alpha > b^\beta$ where $b > 1$.  So it follows that $b^r \geq B(r)$.  
- Suppose $q \geq B(r)$. Since $b^r \in B(r)$, and $b^r \geq x \in B(r)$, then it follows that $q \leq b^r$. 
- Therefore $b^r$ is a supremum of $B(r)$. 
d) From (c) we write that $b^{x + y} = \sup B(x + y)$. $b^x b^y$ similarly is $\sup B(x) \sup B(y)$. 
$B(x + y)$ is all $b^t$ where $t \leq x + y$. Let $b^q = \sup B(x + y)$, which means that, we can create $b^{s+t}$ with $s, t$ rational, and $s \leq x$ and $t \leq y$,. Then this is $b^sb^t = \sup B(x) \sup B(y) = b




8) ![[Pasted image 20220601202802.png]]


8) Suppose there is an ordering of the complex field. We have $0 = (0,0)$. 
Let $(0,1) >0$ be positive; then $(0,1)(0,1) = (-1,0)$. So then this must be positive also. 
Then $(0,1)(-1,0) = (0, -1)$, also positive. But $(0,1) + (0,-1) = 0$. 
So then $0-(0,-1) <0$ means $(0,1) < 0$.

The reverse argument applies if $(0,1)$ is defined as negative. 

9) Does this have the properties of an order? 
Let $z,w,y \in \mathbb C$, and $a,b,c,d,e \in \R$. Suppose that neither $z > w$ nor $z < w$. Then none of the conditions of inequality hold.:
- $!(a < c) \land !(a > c)$
- $![(a = c) \land (b > d)] \land ![(a = c) \land (b < d)]$

From the first we can conclude that $a = c$; then we can use that in the latter to demonstrate that $b = d$.  So this is total. 

Suppose $z < w$ and $w < y$. Let $y = e + fi$. From the two assumptions we have:
- $(a < c) \lor [(a =c) \land (b < d) ]$, and 
- $(c < e) \lor [(c = e) \land (d < f) ]$

So we can work through the four cases:
- If $a < c$ and $c< e$, then $a < e$ and so $z < y$.
- If $a < c$ and $c = e$, then $a < e$ and so $z < y$.
- If $a =c$ and $c < e$, then $a<e$ and so $z < y$. 
- If $a = c$ and $c = e$, then the first implies that $b < d$, and the second that $d < f$, so $b < f$. 

So this is transitive. 
It is an order. 

Does it have the least upper bound property? 

Suppose $E \subset \mathbb C$, $E \neq \emptyset$, and $E$ is bounded above. 

Then


12) ![[Pasted image 20220601202843.png]]


15) ![[Pasted image 20220601202852.png]]


Equality obviously holds when both vectors are $0$. Equality also holds, intuitively, when $\langle a,a\rangle \langle b,b \rangle = \langle a,b \rangle^2$. This is the condition of linear dependence, or being parallel, in an inner product space. 



20) ![[Pasted image 20220601202903.png]]

So we have the neo-cut $\alpha$, which has these properties:
1) $\alpha \subset Q$, $\alpha \neq Q$, $\alpha \neq \emptyset$
2) $p \in \alpha \land q < p$ means $q \in \alpha$. 

But no more!

Let $R'$ be the set of neo-cuts. 

$R'$ is an ordered set:
Define its order as folllows: $\alpha < \beta$ if all the elements of $\alpha$ are in $\beta$, and $\beta$ has elements not in $\beta$. Is this an order?
1) It's clearly transitive. If $\alpha < \beta$, and $\beta < \gamma$, everything in $\alpha$ is in $\beta$, which means it's in $\gamma$ - and from nonemptyness we know there's something in $\alpha$.
2) It's total. Suppose neither $\alpha > \beta$ nor $\beta < \alpha$. We know each has some element(s). But from the definition of the order, neither has elements not in the other. Therefore, $\alpha = \beta$. 

It has the LUB property:
Let $A$ be a set of cuts, nonempty, that contains proper subsets of $Q$. Then let $\gamma$ be the union of all the subsets of $A$ - everything which is in a cut which is in $A$. $\gamma$ is a cut:
- $\gamma$ is nonempty since $A$ has at least one $\alpha$ which has at least one element. Since $A$ has only proper subsets of $Q$, every $p \in \alpha \in A$ is in $Q$, and so $\gamma \subset Q$;  there is some $q \in Q$ that is not in any $\alpha$ in $A$, so it is not in $\gamma$, so $\gamma \neq Q$.
- Suppose $p \in \gamma$ and $q < p$, We know there's an $\alpha_p$ that has $p$ in it, and so from property 2 it has $q$ in it, so $q$ is in $\gamma$.

For any $\alpha \in A$, every element of $\alpha$ is in $\gamma$, meaning $\alpha \leq \gamma$: gamma is an upper bound.

Now suppose $\delta < \gamma$. From inequality we know that there is some $p$ in $\gamma$ that isn't in $\delta$. But from the definition of $\gamma$ we know there is a set $\alpha_p$ such that $\alpha_p \in A$ and $p \in \alpha_p$, so $\alpha_p > \delta$, which means that $\delta$ cannot be an upper bound. So $\gamma$ is the least upper bound. 

Addition:
Define $\alpha + \beta$ over $R$ as the set of all $r + s$ where $r \in \alpha$ and $s \in \beta$. 
Axiom (A1) Closure: $\alpha + \beta$ is in $R$.
- It's clear that $\alpha + \beta$ is nonempty; since $r + s \in Q$, it is a subset of $Q$. Since $\alpha$ and $\beta$ are proper subsets of $Q$, there is a $q_1 \in Q$ that is not in $\alpha$, and a $q_2$ that is not in $\beta$. From Property 2 we know that $q_1 > r$ for all $r$ in $\alpha$, and $q_2 > s$ if $s$ is in $\beta$, so $q_1 + q_2> r+ s$, which means $q_1 + q_2 \notin \alpha + \beta$.  
- Suppose $r + s$ in $\alpha + \beta$. Suppose $q < r + s$. Then $q - s < r$; so $q - s \in a$; and adding $s$ from $\beta$ gets us that $q \in \alpha + \beta$.
Axiom (A2) Commutativity. Follows from commutativity of rational addition.
Axiom (A3) Associativity. Ditto
Axiom (A4) Identity. We want some $I$ such that $\alpha + I = \alpha$. Suppose $I$ is the set of negative rationals and zero
- Then for $s \in I$, $r + s < r$, so $r + s \in \alpha$, so $\alpha + I \subset \alpha$. 
- Suppose $p \in \alpha$; then $p - p = 0 \in I$; and $p + 0 \in \alpha + I$. So $\alpha \subset \alpha + I$. 

Axiom (A5) Inverse
Suppose $\alpha$ is all negative rationals. Then $\beta$ is the set of rationals $s$ such that $r  + s \leq 0 \; \forall\,  r \in \alpha$. But if $x = r + s$ then there exists $t > r$ such that $t + s > x$. So $\alpha + \beta$ has no largest element, but $I$ does. 
