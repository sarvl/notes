#math 

A sequence can can be equivalently defined as either
1. a [[Function]] $\mathbb{N} \to A$ 
2. infinitely long [[Tuple]].

For convenience, this document uses first definition.

## Special Cases
### Arithmetic
An arithmetic sequence can be defined with $a_0$ and $r$, then $a_n = a_{n - 1} + r$

#### Sum

### Geometric
A geometric sequence can be defined with $a_0$ and $q$, then $a_n = a_{n - 1} \cdot q$

#### Sum

## Limit

### Finite
A sequence may have a finite [[Limit]] defined as the value the sequence approaches as more and more elements are taken, that is limit $L$ is defined to be a number such that $$\forall_{\epsilon \in \mathbb{R}}\exists_{M \in \mathbb{N}}\forall_{n \geq M} |a_n - L| < \epsilon$$
This is written in short: "as $n \to \infty$ $a_n \to L$" or "$\lim_{n \to \infty}a_n \to L$"

### Infinite


### No Limit
Not every sequence has a limit, for example $a_n = \left(-1\right)^n$ which [[Oscillation|Oscillates]] between $-1$ and $1$.  Being unbounded is <u>not</u> enough to guarantee a limit, consider $a_n = n \left(-1 \right)^n$. 

## TODO
- requirements to have defined notion of a limit - generalize to any set
- infinite limit (divergence
- exercises