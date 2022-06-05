---
aliases:
creation date: 2022-06-05 13:20
date updated: Sunday, June 5th 2022, 1:21 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/analysis'
- '#status/🚧'
---

# [[Su 5 Complex Numbers, Euclidean Space]]
[[Real Analysis Su and Rudin]]


Reiterating the first part of the proof, we know that 
$$|z + w|^2 = (z + w)\overline{(z + w)} = (z + w)(\bar z + \bar w) = z \bar z + w \bar w + w\bar z + z \bar w$$
The last two steps are conjugates - so we replace the:
$$ |z + w|^2 = z\bar z + w \bar w +  2 \text{Re}(zw)$$
To get inequality, the crucial step is that $2 \text{Re}(zw) \leq 2|zw| = 2|z||w|$. Suppose that this is equal. Then we have 
$$ |z + w|^2 = z\bar z + w \bar w +  2 \text{Re}(zw) = |z|^2 + |w|^2 + 2|z||w| = (|z| + |w|)^2$$
$$|z + w| = |z| + |w|$$
So: when is $\text{Re}(a) = |a|$? This happens when $a$ is entirely real: then $a = (x,0)$, and $|a| = (a \bar a)^{1/2} = [(x,0)(x,0)]^{1/2}$  $= x$. 

<font color=#F7B801>turns out I was distracted and proved the triangle inequality...</font>

The Schwarz inequality is obviously equality when both vectors are $0$.  Are there other times?

The Schwarz inequality is a transformation of the general fact that $0 \leq \langle a,a \rangle$ for all $a \in \mathbb C ^n$. 
$$0 \leq \langle a - yb , a - yb \rangle = \sum (a_i - y b_i)\overline{(a_i - y b_i)}= \sum [a_i \bar a_i  - a_i \bar y \bar b_i - \bar a_i y b_i + y \bar y b_i \bar b_i)]$$
$$0 \leq \langle a,a\rangle - \bar y \langle a, b\rangle - y \overline{\langle a,b \rangle} + y \bar y \langle b,b \rangle   $$
This reduces to the CS inequality when $y = \frac{\langle a,b \rangle}{\langle b,b \rangle}$.

Then:

$$\begin{align}
0 &\leq  \langle a,a\rangle - \overline{\frac{\langle a,b \rangle}{\langle b,b \rangle}} \langle a, b\rangle - \frac{\langle a,b \rangle}{\langle b,b \rangle} \overline{\langle a,b \rangle} + \frac{\langle a,b \rangle}{\langle b,b \rangle} \overline{\frac{\langle a,b \rangle}{\langle b,b \rangle}} \langle b,b \rangle \\
&\leq  \langle a,a\rangle - \frac{\overline{\langle a,b \rangle} \langle a, b\rangle}{\langle b,b \rangle}  - \frac{\langle a,b \rangle \overline{\langle a,b \rangle}}{\langle b,b \rangle}  + \frac{\langle a,b \rangle}{\langle b,b \rangle} \frac{\overline{\langle a,b \rangle}}{\langle b,b \rangle} \langle b,b \rangle \\ 
& \leq  \langle a,a\rangle - \frac{\overline{\langle a,b \rangle} \langle a, b\rangle}{\langle b,b \rangle}  - \frac{\langle a,b \rangle \overline{\langle a,b \rangle}}{\langle b,b \rangle}  + \frac{\langle a,b \rangle \overline{\langle a,b \rangle}}{\langle b,b \rangle} \\ 
&\leq  \langle a,a\rangle - \frac{\overline{\langle a,b \rangle} \langle a, b\rangle}{\langle b,b \rangle}\\
\langle a,b \rangle \overline{\langle a, b\rangle} &\leq \langle a,a \rangle \langle b,b \rangle \\
\end{align}
$$
