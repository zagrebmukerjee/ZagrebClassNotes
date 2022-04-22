---
date updated: 2021-06-23 00:11

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/calculus'
---

### [[Digression - Chain Rule Practice]]


Some product and chain rule problems:

1. $\frac{d}{dx} e^x \sin(x)$
2. $\frac{d}{dx} \sin(x)/ \cos(x)$
3.  $\frac{d}{dx}\cos(3x)^2$
4.   $\frac{d}{dx}e^x(x^2 + 3x + 2)$
5.    $\frac{d}{dx} e^{\sin(x)} \cos( x^{-3} + x^{3})$

---
1. $\frac{d}{dx} e^x \sin(x)$
  Product rule: $f'(x)g(x) + g'(x)f(x)$. 
 
$$e^x\sin(x) e^x\cos(x)$$

2. $\frac{d}{dx} \sin(x)/ \cos(x)$
First, the chain rule for $1/\cos(x)$:

$$\frac{d}{dx}1/\cos(x) = \frac{d}{dx} \cos(x)(\frac{d}{dh}\frac{1}{h} ) $$
$$\frac{d}{dx}1/\cos(x) = -\sin(x)(\frac{-1}{h^2} ) $$
$$\frac{d}{dx}1/\cos(x) = \frac{\sin(x)}{\cos(x)^2} $$

Then the product rule:

$$ \frac{d}{dx} [\sin(x)][1/\cos(x)] = (1/\cos(x))\frac{d}{dx} [\sin(x)] + \sin(x) \frac{d}{dx}[1/\cos(x)]$$

$$\frac{d}{dx} [\sin(x)][1/\cos(x)]  = 1 + \frac{\sin(x)^2}{\cos(x)^2} $$
$$\frac{d}{dx} [\sin(x)][1/\cos(x)]  = \frac{\sin(x)^2 + \cos(x)^2}{\cos(x)^2} = \sec(x)^2$$

where $\sec(x)$ is $1/\cos(x)$

3.  $\frac{d}{dx}\cos(3x)^2$
Square of Cosine of 3x

$$\frac{d}{dx} \cos(3x) = -3\sin(3x)$$
$$\frac{d}{dh} h^2 = 2h$$

$$\frac{d}{dx}\cos(3x)^2 = -6\sin(3x)\cos(3x)$$
 
4.   $\frac{d}{dx}e^x(x^2 + 3x + 2)$
$$\frac{d}{dx}(x^2 + 3x + 2) = 2x+ 3$$

Product rule: 

$$ e^x(x^2 + 3x + 2) + e^x(2x+ 3)$$
$$ e^xx^2 + 3e^xx + 2e^x + 2e^xx+ 3e^x$$
$$ e^xx^2 + 5e^xx + 5e^x $$

6.    $\frac{d}{dx} e^{\sin(x)} \cos( x^{-3} + x^{3})$

aaa