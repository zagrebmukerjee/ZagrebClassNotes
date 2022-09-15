---
aliases:
- 'quasiconcave'
- 'strictly quasiconcave'
- 'convex'
- 'strictly quasiconvex'
- 'hemicontinuous'
creation date: Thursday, September 15th 2022, 9:31 am
date updated: Thursday, September 15th 2022, 9:35 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#types/classes/math'
---

# [[Micro Theory IIb - Concave, Convex, Quasi; Hemicontinuity]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

### Convexity Definitions
- A <font color=gree>convex combination</font> of $x,y$ is $\lambda x + (1- \lambda) y$. 
- A set $A$ is convex if for any $x,y \in A$, the convex combo of $x,y$ is also in $A$.
- Preferences $\succsim$ are convex if the upper contour sets are convex, i.e. if $\forall x \in X$ the set $y \in X: y \succsim x$ is convex.
- Preferences are strictly convex if $y \succsim x$ and $z \succsim x$ with $y \neq z$ means that all convex combinations of $y, z$ are strictly preferred to $x$. 

### Quasiconcavity Definitions

- $u$ is quasiconcave (QCV) if the upper contour sets are convex: $\forall x$, $y: u(y) \geq x$ is convex. 
- $u$ is strictly QCV (SQCV) if $u(y) \geq u(x)$ and $u(z) \geq u(x)$ implies that all convex combinations of $y,z$ have strictly higher utility than $x$. This is the satisfaction of [[Jensen's inequality]].

Simpler conditions: 
- $u$ is QCV if $\forall x, y$, $u(\lambda x + (1-\lambda) y) \geq \min \{ u(x), u(y) \}$
- $u$ is SQCV if $\forall x, y$, $u(\lambda x + (1-\lambda) y) > \min \{ u(x), u(y) \}$

### Quasiconvexity 