---
aliases:
creation date: Thursday, September 1st 2022, 5:23 pm
date updated: Sunday, September 11th 2022, 12:35 pm

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

If $x \in C(\{x,y\})$, then write $x \succsim_C y$. 
- By FNE, we can say this exists for every pair $x,y$. So it is complete. 
- For transitivity: Suppose $x \succsim_c y$ and $y \succsim_c z$. Then a) $x \in C(\{x,y\})$ and b) $y \in C(\{y,z\})$. Consider now $R = C(\{x,y,z\})$. From applying coherence on b) we know that $z \notin R$. From coherence and a), we know that $y \notin R$. So by FNE it follows that $x\in R$. Now, we can use coherence once more to say that since $\{ x,z\}$ is a subset of $\{x,y,z\}$, $x$ must be in $C(\{x,z\})$. So it follows that $x \succsim_C z$. 


Then create $C'$, with $C'(A) = B$, defined as: $x \in B \iff (y \in A \implies x \succsim y)$. We now can show $C(A) \subseteq C'(A)$ and vice versa. 
- Suppose $x \in C(A)$. Then $\forall \; y \in A$, for each pair $\{x,y\}$, we know that $x \in C(\{x,y\})$ by coherence. So then $x \succsim_C y$, and thus $C(A) \subseteq C'(A)$. 
- Now, choose $A$ and $x \in C'(A)$. Then we know that $\forall \; y \in A$, $x \succsim_C y$. Choose some $y \in C(A)$ (by nonempty). By definition of $C'$, $x \succsim_C y$. So $x \in C(\{x,y\})$. Since $x$ is chosen from $\{x,y\}$, a subset of $A$, and since $y$ is chosen from $A$, $x \in C(A)$. So $C'(A) \subseteq C(A)$. 


OK. But what about utility functions? 

One direction is straightforward: turning utility functions into our desiderata. The other one is sufficiently complex to merit the label of "representation theorems". But it's important to pin this down, because we'll want to use utility functions a lot, and we want them to have very solid foundations. In particular, we want to do this in an infinite choice space, which maks things more complex. 


## Representation Theorems

### Conditions

Let's say $\R^2$ is our consumption space. We're working with preferences that are complete, transitive, weakly monotonic. 

#### Continuity
We add the condition that they are continuous: i.e. $\forall x \; \{ y \in X: y \succsim x \}$ is a closed set, as is $\{ y \in X: x \succsim y\}$. 

In other words, there are upper and lower contour sets of $x$: all the bundles at least as good as $x$, and the bundles than which $x$ is at least as good. These are closed sets - intuitively, that means they contain their boundaries (which are indifference curves). 

Continuity is sometimes called a 'technical' assumption, in that we just use it for math simplification. Though people sometimes say 'this is a technical condition' to mean 'this is useful but I don't understand it'. So watch out for that. It can mean: I need it for math and it's either empirically contentless, or meaningless in finite land. 

An example of noncontinuous preferences: lexicographic $\succsim$. If $x \succ y$, then either $x_1 > y_1$, or $x_1 = y_1$ and $x_2 > y_2$, or so on. This is noncontinuous. Consider the 2 dimensional case. Some bundle $x_1$ is preferred to all sets with $x_1 > y_1$. But also all sets with $x_1 = y_1$ and $x_2 > y_2$. In other words, the set $y : x \succsim y$ is all points to the right of $x$ and also all the points directly below $x$, but not the points directly above. So the point $x_1, x_2 + 1$ is preferable to $x$, but it is a limit point of $y: x \succsim y$. 

In fact, there exists no function representing lexicographic preferences. 


#status/section/🚧 
```ad-note
title: Lexicographic Preference Representation 


```

So continuity is not 1000% technical. But we do want it. 

#### Monotonicity 

This one is simple. Strong monotonicity is that $x \geq y \implies x \succ y$. Weak monotonicity is that $x > y \implies x \succ y$. In this case, given vectors $x$ and $y$, $x \geq y$ means that 'every element of $x$ is at least equal to its corresponding element in $y$, and one is greater;