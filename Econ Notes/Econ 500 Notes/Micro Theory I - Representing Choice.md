---
aliases:
creation date: Thursday, September 1st 2022, 5:23 pm
date updated: Thursday, September 8th 2022, 3:29 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
- '#status/🚧'
---

# [[Micro Theory I - Representing Choice]]

## 3 Modes of Choice Representation

We will discuss 3 different representations of choices. 
- Preferences: Most primitive. Good axiomatic foundation
- Choice functions: Map most clearly to what's observed
- Utility functions: analytically very useful. 

We'll demonstrate that these are essentially equivalent. 

### Choice Functions

Choice functions and preferences have to have 2 properties. Loosely:
1) "enough information"
2) "no contradictory information"

Together these are often called 'rational'. "Consistent" might be preferable, having less normative content. 

Let $X$ be some set of alternatives. $C()$ is a choice function such that $C(A)$ is a collection of alternatives chosen from $A \subseteq X$. If $P(X)$ is the power set of $X$, $C: P(X) \to P(X)$ s.t. $C(A) \subseteq A$. 

Two conditions. 

- Finite Non-Emptiness
	- "Enough information":. Given non-empty $A$ and finite $A$, $C(A) \neq \emptyset$. 
	- Why must $A$ be finite? Consider $C(A) = \max A$; let $A = [0,1)$; oh no... 
- Coherence
	- Let $x,y$ be in $S \cap T$. $x \in C(S)$. $y \notin C(S)$. Then $y \notin C(T)$. We'll later discuss how this is the same as transitivity. 
	- The intuition here is: In $S$, I had the choice of $y$, I chose $x$ over $y$. Therefore, when looking at $T$: both $x$ and $y$ are choices. I may not choose $x$ - there might be something in $T \cap S^c$ that's better than $x$. But if I choose $y$ from $S$, why didn't I choose $x$? 


### Preferences

Preference is some subset of the set of pairs - a description of which is 'preferred'. We write $x \succsim y$; "$x$ is at least as good as $y$."  

From this, we can create $x \succ y$ - $x$ is strictly better than $y$, which is true when $x \succsim y$ but $\neg(y \succsim x)$. 

I can also make $x \sim y$, or $x$ is indifferent to $y$, which is the case when both $x \succsim y$ and $y \succsim x$. 

I once more have two conditions: 

- Completeness: For every $x,y$ either $x \succsim y$, $y \succsim x$, or both. 
- Transitivity: If $x \succsim y$ and $y \succsim z$, then $x \succsim z$. 


## Equivalences
We will now produce four results showing these things are equivalent. 

### The Easy Ones

Suppose utility function $u(x)$. Define $x \succsim y \iff u(x) \geq u(y)$; and define $C(A) - \underset{x \in A}{\arg \max} \; u(x)$. 
Given some complete and transitive preferences, define $C(A) = \{ x \in A : y \in A \implies x \succsim y\}$. 

Given these definitions, we can write: 

#### Proposition 1
1) $u$ induces a coherent, FNE choice function $C$.
2) $u$ creates complete, transitive preferences, which
3) create a coherent, FNE choice function $C'$
4) $C'(A) = C(A)$ $\forall$ $A \subseteq X$. 
5) If $C$ is FNE/coherent then $\exists$ $\succsim_c$ generating $C'$ such that, if $C(A) \neq \emptyset$ (case of infinite $A$), $C(A) = C'(A)$. 

#### Proof of Prop 1
