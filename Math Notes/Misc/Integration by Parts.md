---
aliases:
creation date: Wednesday, September 21st 2022, 3:49 pm
date updated: Thursday, September 22nd 2022, 6:36 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/calculus'
---

# [[Integration by Parts]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


Suppose I have the product rule: 

$$ \frac{d}{dx} f(x) \cdot g(x) = f'(x)g(x) + g'(x)f(x)$$
Integrating both sides can get us

$$ \int \frac{d}{dx} f(x) \cdot g(x) dx = \int f'(x)g(x) dx + \int g'(x)f(x)dx $$
$$f(x)g(x) - \int g'(x)f(x)dx = \int f'(x)g(x) dx $$
Rewriting this result gets us IbP. Suppose I have the integral of a product:
$$\int u(x) v(x) dx$$
Looking at this, I might think that I'd rather integrate $u$ and differentiate $v$. So then I can write $U(x) = d/dx \, u(x)$, and use the rearrangement of the product rule.

$$ \int u(x)v(x)dx = \int U'(x)v(x)dx = U(x)v(x) - \int U(x)v'(x)dx$$
