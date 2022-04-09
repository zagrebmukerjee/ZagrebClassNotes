---
date updated: 2021-06-10 22:43

notetype: "Math Class Note"
cssclass: math-class-note

tags:
- '#classnotes/math/linalg'
---

#### [[Digression - LinAlg SemiProof 1]]


Theorem: Let  $v , w$ be vectors  in $\mathbb{R^2}$. For all $x$ in $\mathbb{R^2}$, there exist scalars $a$ and $b$ such that $x = av + bw$ if and only if
$$\{k \in \mathbb{R}|kv = w\} = \emptyset$$

Semiproof:
$$\begin{array}{lcl}
av_1 + bw_1 &=& x_1\\
av_2 + bv_2 &=& x_2
\end{array}$$

$$ a= \frac{x_1 - bw_1}{v_1}$$
$$\frac{x_1 - bw_1}{v_1}v_2 + bw_2 -x_2  = 0$$
$$x_1v_2  -x_2v_1  = bw_2v_1- bw_1v_2$$
$$ b= \frac{x_1v_2  -x_2v_1}{w_2v_1 - w_1 v_2}$$

Suppose $\exists \, k$ such that $kv = w$. Then $b$ does not exist.
$$ b = \frac{x_1v_2  -x_2v_1}{kv_2v_1 - kv1 v_2}$$
$$ b = \frac{x_1v_2  -x_2v_1}{0}$$

$a$ follows similar logic.