---
date updated: 2021-06-11 13:23

notetype: "Math Class Note"
cssclass: math-class-note

tags:
  - '#classNotes'
---

#### [[Video 2 Linear Combinations, Span, and Basis Vectors]]
Part of [[@Review of Linear Algebra Index]]


Suppose $\mathbf{v} = [v_1, v_2]$.  Let $\mathbf{\hat{i}} = [1,0]$ and $\mathbf{\hat{j}} = [0,1]$ (of length 1 - called unit vectors). Then we have:
$\mathbf{v} = v_1 \mathbf{\hat{i}} + v_2 \mathbf{\hat{j}}$

This is a <i>linear combination</i> of  $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$ (involving some composition of addition and scalar multiplication). Because any 2D vector $\mathbf{v}$ can be formed from  $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$, they are called the basis of $\mathbb{R}^2$ - the $xy$ coordinate system.

Any 2 non-parallel vectors $\mathbf{v}$ and $\mathbf{w}$ can be a basis of the $xy$ coordinate system ([[Digression - LinAlg SemiProof 1|Semi- Proof]]).

The set of linear combinations of $\mathbf{v}$ and $\mathbf{w}$ is the <i>span</i> of $\mathbf{v}$ and $\mathbf{w}$. More span facts:

- The span of one vector (or two linearly dependent vectors) is a line.
- The span of 2 3D vectors is a plane in $\mathbb{R}^3$
- The span of 3 3D vectors is $\mathbb{R}^3$, unless they are linearly dependent, in which case it is a line or a plane.
