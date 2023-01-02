---
aliases: 
tags: 
creation date: Monday, November 14th 2022, 10:02 am
date updated: Monday, November 14th 2022, 11:16 am
---

## Sperner's Lemma

Fix an n-simplex T and a labelled simplicial subdivision $T_i$, $i \in I$. (label each vertex of $t \in T_i$ with $1, \ldots, n$ such that the label corresponds to a vertex with positive weight).
Then there exists a completely labelled $T_i$; i.e. one with all $n$ labels. 

### Proof

Suffices to show set of simplices $t \in T_i$ that are completely labelled has odd # of elements. By induction. 

Start with $n =1$. Any simplicial subdivision with $k$ members is pairs of points $(x_1, a_1), \ldots, (a_{k-1}, x_2)$. Label $x_1 = 0$, $x_2 = 1$. 
1) Let $a$ be the number of segments with $0$ at both endpoints
2) Let $b$ be the ones that are $0$ and $1$. 

For each segment: how many endpoints labelled $0$? add it up. This is $2a + b$ - with lots of double counting.  

Let $c$ be the number of $0$ labelled vertices that are not in the original simplex. These were not double counted. Others must have been. So the with-double-counting number is $2c + 1$ which is odd. But then $2a + b$ is odd; since $2a$ is even, $b$ must be odd. 

Sort of like the idea that curve that goes from + to - must intersect x axis an odd number of times (without tangencies).

Now, induction step. 

Suppose statement is true for $n$. Then WTS it is true for $n+1$. Want to count the # of faces of $T_i$ that carry labels $0,1, n-1$. 

Count these two ways. 
Let $a$ be simplices whose vertices are labelled $0,1,\ldots, n-1$. 
let $b$ be members of $T_i$ whose vertices are labelled $0, 1, \ldots, n$. Completely labelled.
how many faces of $T_i$ are labelled $0$ thru $n-1$: 
- each simplex in $a$ has 2 faces labelled $0, \ldots, n-1$ and has one repeated vertex. 
- Face opposite that repeated vertex is labelled with $0, \ldots, n-1$ (the set of points in that simplex that have no weight on the repeated vertex). 


So for each of $0, n-1$ there are $2a$. 
For each of $b$ there is just one face: the face opposite $n$. Then we have our $2a + b$ again. 


Now we will count with the generalization of interior and exterior. 

Let $c$ be the faces of some $t \in T_i$ that are not included in the face of $T$ labelled $0, \ldots, n-1$ - ie opposite to vertex $n$. 
Let $d$ be the other faces labelled $0, \ldots, n-1$ that are included in that face. 
$d$ is an $n-1$ simplex. So by induction, $d$ is odd. 


Every face in $c$ is counted twice by the defn of simplicial subdivision (since it's not on the outside). So this is $2c + d$ where $d$ is odd. $2c + d = 2a +b$; so $b$ must be odd also. 


## KKM Lemma

Knaster Kuratowski Mazuskewicz. 
Let $T$ be an $n$ simplex. Consider sets $C_0, \ldots, C_n$ closed; $C_i \subseteq \overline T$ the closure of $T$; for all elements $x$ in $\overline T$, $x \in C_i$ for some $i$ such that $\lambda_i(x) > 0$ (ie. each point is in a set whose index corresponds to a vertex with positive weight in $x$). 

So for example, if triangle is labelled $0,1,2$, a point on $1,2$ edge must be in either $C_1$ or $C_2$.

Then the intersection of the $C_i$ is nonempty. 

Proof: 

Sperner's lemma. Consider a sequence of simplicial subdivisions $T_i^n$ such that the mesh $T_i^n$ goes to $0$ as $n \to \infty$; and such that each vertex of $T_i^n$ has a label $j$ where $j$ is such that $v \in C_j$ and $\lambda_j(v)>0$. We know some such $C_j$ exists from the condition in the theorem.  

So eg in my triangle the point on $1,2$ edge must be labelled $1$ or $2$. 

Then we can use Sperner's Lemma: for all $n$, $T_i^n$ has an odd number of completely labelled simplices, ie. at least one $t \in T_i^n$. So there is some $t_n$ that is a convergent subsequence of completely labelled subsimplices. so there is some $v \in \overline T$ such that $v_j^n \to v$ for every vertex of the completely labelled simplices. 

Sequence of vertices labelled $0$ all belong to $C_0$ so by closure their limit is in $C_0$. But all the vertices with different laels converge to the same point, since mesh goes to $0$. This point is in the intersection of all $C$ which therefore is nonempty. 



## Brouwer's Fixed Point Theorem

Pick $f: \overline T \to \overline T$. $f$ is continuous. Then there exists some $x \in \overline T$ such that $f(x) = x$. 
(here, I care that $\overline T$ is nonmepty convex compact). 

### Proof

Consider $C_i = \{x \in \overline T | \lambda_i(f(x)) \leq \lambda_i(x) \}$. 
Then $C_i$ is closed because $f$ is continuous, and $\lambda_i$ is continuous 

$1 = \sum_i \lambda_i(x)$. So $1 = \sum_{i|\lambda_i(x) > 0} \lambda_i(x)$; and that is $\geq \sum_{i|\lambda_i(x)>0} \lambda_i f(x)$, because the nonconditional sum is $1$ and so when conditioned it must be less. 

So there exists some $i$ such that $\lambda_i(x) > 0$ and $\lambda_i(x) \geq \lambda_i(f(x))$ meaning $x \in C_i$


So the $C_i$ are closed, and so satisfy conditions of the KKM lemma. So $\exists x \in \bigcap C_i$. 

Hence $\forall \; i$, st $\lambda_i(f(x)) \leq \lambda_i(x)$. But $\sum \lambda_i(f(x)) = \sum \lambda_i(x)  =1$. So $\lambda_i(f(x)) = \lambda_i(x)$, and so $f(x) = x$. 