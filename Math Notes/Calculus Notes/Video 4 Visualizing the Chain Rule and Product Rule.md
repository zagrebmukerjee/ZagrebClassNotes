---
date updated: 2021-06-22 23:07

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/calculus'
---

### [[Video 4 Visualizing the Chain Rule and Product Rule]]


There are basically three ways of combining two functions: addition, multiplication, and function composition. (subtraction and divison are combinations of these). How do these transform the derivative?

#### Derivative of sums

First, the derivative of the sum $g(x) + h(x)$ turns out to be the sum of the derivatives $g'(x) + h'(x)$ (alternate derivative notation). 

![[Pasted image 20210622231006.png]]


```ad-info
title:Algebraic proof of this property
collapse:true

![[Digression - properties of derivative algebraically#Derivative of a sum]]

```

#### Derivative of product

Once again we can go to a square. Suppose $g(x)$ is $\sin (x)$ and $h(x)$ is $x^2$. Then we have this square:

![[Pasted image 20210622231506.png]]

So what is the change in area $dA$? Again, our outer sides:

$$dA = x^2 d \sin(x) + \sin(x) dx^2 + dx^2 d\sin(x)$$
$$\frac{dA}{dx} = \frac{x^2 d \sin(x)}{dx}\ + \frac{\sin(x) dx^2}{dx} + \frac{dx^2 d\sin(x)}{dx}
$$

$$\frac{dA}{dx} = x^2\frac{ d \sin(x)}{dx}\ + \sin(x)\frac{ dx^2}{dx}
$$

In other words, 
$$ \frac{d}{dx}(g(x) + h(x)) = g(x)\frac{dh}{dx} + h(x)\frac{dg}{dx}$$

Mnemonic - "Left d Right plus Right d Left"

```ad-info
title:Algebraic proof of this property
collapse:true

<font color = "gree"> Honestly, this isn't worth looking at - the geometric intuition is more important and much nicer. </font>

![[Digression - properties of derivative algebraically#Derivative of product of functions]]

```

#### Chain Rule

```ad-quote
title:

“Using the chain rule is like peeling an onion: you have to deal with each layer at a time, and if it is too big you will start crying.”

 \- Anonymous Professor
```

Function composition is applying two functions in sequence. Let $f(x) = g(h(x))$. So if  $f(x) = \sin(x^2)$, then $g(a) = \sin(a)$ and $h(b) = b^2$. So what's the derivative of that?

We can think of mappings between successive number lines. 

![[Pasted image 20210622235358.png]]

So if $x$ is $1.5$, then that maps to $2.25$, and then to $\sin(2.25)$ - some decimal or whatever

What happens when we change $x$ by $dx$? We can reason backwards. We're applying $\sin()$ to something - call it $h$. And $h$ is changing by $dh$.

![[Pasted image 20210622235738.png]]

Thus we know that $d\sin(h) = \cos(h) dh$. 

But we know what $h$ is, and we know what $dh$ is - $h$ is $x^2$ and $dh$ is $2xdx$. So we can substitute into the above: 
$$ d\sin(x^2) = \cos(x^2)(2xdx)$$

$$ \frac{d}{dx} sin(x^2) = 2x\cos(x^2)$$

More generally, this is the Chain Rule. Let $f(x) = g(h(x))$. Then

$$ f'(x) = h'(x)g'(h(x))$$

Exercises here: [[Digression - Chain Rule Practice]]