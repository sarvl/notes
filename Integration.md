#math #integration #calculation #sum #calculus 

As part of [[Mathematics]], and more precisely [[Mathematical_Analysis|Mathematical Analysis]], Integration is a way to sum up infinitely small components over a certain range, symbolic integration is achieved by calculating antiderivative while numeric integration is achieved by successive approximations.


## Definition

$$\int_{a}^{b} f(x) dx = \lim_{\Delta x \to 0} \sum_{\substack{i=a \\ \text{step size} = \Delta x}}^{b} f(i) \Delta x$$

For the definition of limit see [[Limit]].

## Antiderivative

Antidifferentiation is a process opposite of [[Differentiation]], and so is equivalent to finding function with given derivative.

### List


### Exercises


## Numerical Integration

### List

### Exercises


## Applications

### Summation
Commonly found in [[Physics]], solving continuous problems can be done by
1. assuming the problem is composed out of discrete (usually $\Delta x$ steps).
2.  setting up equations in discrete way
3.  taking the limit (switching to $dx$)
4.  summing all the infinitelly small elements

#### Example
Let there be uniformly [[Electromagnetism|charged]] rod of charge density $\lambda$ and length $L$.
1. Assume the rod can be divided into finitely many $\Delta l$ chunks. 
2.  Each chunk has $\Delta q = \lambda \cdot \Delta l$.
3.  Then each $dq = \lambda dl$
4.  So finally $q = \int dq = \int \lambda dl = \lambda \int dl = \lambda L$ 

The above is not fully rigorous as it should use definite integrals, but the  result would be the same.

### Area Under the Curve
The above summation can be extended into finding area under the graph.

#### Example
Let there be a function defined for $x \in [-r; r]$ $$f(x) = \sqrt{r^2 - x^2}$$  

![[Integration_Graph_Half-Circle.png]]
The graph above assumes $r = 1$

The area between X axis and red curve is given by 
$$\int_{-r}^{r} \sqrt{r^2 - x^2} dx$$

\star math \start
$$\int \sqrt{r^2 - x^2} dx = \frac{1}{2} \left(x\sqrt{r^2 - x^2} + r^2 tan^{-1} \left( \frac{x}{\sqrt{r^2 - x^2}} \right)\right)$$
Evaluated for $x = r$:
$$\frac{1}{2} \left(r\sqrt{r^2 - r^2} + r^2 tan^{-1} \left( \frac{r}{\sqrt{r^2 - r^2}} \right)\right)$$
$$\frac{1}{2} \left(0 + r^2 tan^{-1} \left( +\infty \right)\right)$$
$$\frac{1}{2} \cdot r^2 \cdot \frac{\pi}{2} $$
Note that strictly speaking there should be a limit for inverse tangent, this is enough for demonstration purposes.
Similarly evaluating $x = -r$ yields
$$- \frac{1}{2} \cdot r^2 \cdot \frac{\pi}{2} $$
and so
$$\int_{-r}^{r} \sqrt{r^2 - x^2} dx = \frac{1}{2} \cdot r^2 \cdot \frac{\pi}{2} + \frac{1}{2} \cdot r^2 \cdot \frac{\pi}{2}$$
$$\int_{-r}^{r} \sqrt{r^2 - x^2} dx = \frac{1}{2} \pi r^2$$

If the original graph was mirrored across the x axis, the curve would make a full circle, but the area of mirrored  path is the same, therefore  full area of the circle is $\pi r^{2}$.  
Interesting observation is that $\frac{d}{dr} area = circumference$, as $\frac{d}{dr} \pi r^{2} = 2\pi r$. This is not an accident, the circumference can be thought of as a change in area while the radius is increasing.  



## TODO
- fill sections
- complete the math derivation
- get into formalism of rieman integration
- be careful about antiderivative and integrals
- take into account definite/indefinite integrals
- fundamental theorem of calculus
- better visualization of rieman integral
- Add exercises
- add questions to ponder