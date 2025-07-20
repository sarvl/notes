#math #differentiation #calculus #calculation 

Differentiation in [[Mathematics]], and more precisely [[Mathematical_Analysis|Mathematical Analysis]], is a process of finding how a function changes <u>locally</u>. Generally this is mechanical and not particularly enlightening  process.

## Definition
$$\frac{df}{dx} = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}$$
For the definition of limit see [[Limit]].

In words, the derivative is defined as a rate of change (rise over run, slope) of the function at a given point, it is a slope of a line tangent at that particular point.

### Example
Let $f(x) = x^2$ 
$$\lim_{h \to 0} \frac{(x + h)^2 - (x)^2}{h} $$
$$\lim_{h \to 0} \frac{x^2 + 2hx + h^2 - x^2}{h}$$
$$\lim_{h \to 0} \frac{2hx + h^2}{h}$$
$$\lim_{h \to 0} (2x + h)$$
$$\frac{d}{dx}(x^2) = 2x $$


## Properties
A derivative is [[Linearity|Linear]] [[Operator]] acting on functions, meaning that it is 
- Additive
- Homogeneous

Additionally derivatives obey chain rule, let $h(x) = g(f(x))$, then $\frac{dh}{dx} = \frac{dg}{df} \frac{df}{dx}$.
Despite what it looks like, this is NOT a fraction, *sometimes* it can be treated like one but this leads to pitfall for multivariable calculus where 
$$\frac{dy}{dx} = - \frac{\frac{\partial F}{\partial x}}{\frac{\partial F}{\partial y}}$$
note the minus sign.

## Table of Functions

| $f$      |  $\frac{df}{dx}$   |
| :---: | :---: |
| $C$     |    $0$             |
| $x^n$    |   $nx^{n-1}$       |
| $e^x$    |   $e^x$           |
| $\sin x$ |   $\cos x$         |
| $\cos x$ | $- \sin x$         |

## TODO
- visualization
- Add exercises
- add questions to ponder
- add more to the table
- example of each rule 
- optimization problems