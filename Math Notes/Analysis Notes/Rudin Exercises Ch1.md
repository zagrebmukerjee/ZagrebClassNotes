---
aliases:
creation date: 2022-06-01 19:55
date updated: Friday, June 3rd 2022, 9:10 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math'
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

c) If $b>1$, it follows that $b\cdot b > b\cdot 1$, or more generally with integers $c,d$ if $c >d$ then $b^c > b^d$. This extends to rational numbers: suppose $x,y \in Q$, and 


8) ![[Pasted image 20220601202802.png]]



12) ![[Pasted image 20220601202843.png]]


15) ![[Pasted image 20220601202852.png]]



20) ![[Pasted image 20220601202903.png]]
