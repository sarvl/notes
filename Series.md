#math 	

A series is defined to be progressive sum of a [[Sequence]]. 
More precisely let $\{a_n\}$ be a sequence, then let $s_n = \sum_{i=1}^{n} a_i$, then series is $\lim_{n \to \infty} s_n = \sum_{i = 0}^{\infty} a_n$. Each $s_n$ is called *partial sum*.
If that final exists and is not $\pm \infty$, the series is called *convergent*, otherwise it is *divergent*.

## Convergence
A necessary but not sufficient condition is $$\lim_{n \to \infty}a_n = 0$$

If a series $a_n$ is convergent then $\left(c \in \mathbb{R}\right) \cdot a_n$ is also convergent
If a series $a_n$ is divergent then $\left(c \in \mathbb{R} - \{0\}\right) \cdot a_n$ is also divergent

### Tests
#### Comparison
Let $a_n$ and $b_n$ be sequences satisfying necessary conditions for series convergence, and assume all terms are nonnegative $$\left(\exists_N\forall_{n > N}a_n < b_n\right) \land \sum b_n\text{ is convergent}\Rightarrow a_n \text{ is convergent}$$

Let $a_n$ and $b_n$ be sequences satisfying necessary conditions for series convergence, and assume all terms are nonnegative $$\left(\exists_N\forall_{n > N}a_n > b_n\right) \land \sum b_n\text{ is divergent}\Rightarrow a_n \text{ is divergent}$$

#### Ratio
Let $a_n$ be sequence satisfying necessary conditions for series convergence, then let
$$\exists_N \forall_{n > N} \frac{a_{n+1}}{a_n} = c$$
$$c < 1 \Rightarrow \sum a_n \text{ is convergent}$$
$$c > 1 \Rightarrow \sum a_n \text{ is divergent}$$
$$c = 1 \Rightarrow \text{more tests necessary}$$

note that this $c$ does not need to be the same for each $n$, but its relationship to $1$ has to be unchanged

#### Root
Let $a_n$ be sequence satisfying necessary conditions for series convergence, then let
$$\exists_N \forall_{n > N} \sqrt[n]{a_n} = c$$
$$c < 1 \Rightarrow \sum a_n \text{ is convergent}$$
$$c > 1 \Rightarrow \sum a_n \text{ is divergent}$$
$$c = 1 \Rightarrow \text{more tests necessary}$$

## Special  Types
### Arithmetic
see [[Sequence#Arithmetic]]
No nonzero arithmetic series can have finite sum.

### Geometric
see [[Sequence#Geometric#Sum]]

### Harmonic
see [[Sequence#Harmonic]]

$\alpha$-th order harmonic series is expressed by $$\sum_{n=1}^{\infty} \frac{1}{n^\alpha}$$
It is  convergent for any $\alpha > 1$ and divergent to infinity for any $\alpha \leq 1$




## TODO
- verify
- examples
- exercises
- rieman rearangement theorem 
- organize
- proofs
- write something in geo
- intuition for tests