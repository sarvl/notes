#math #function 

A function is defined to be a map from one [[Set]] to another, a type of [[Relation]], such that each element from first set - Domain, has one and only one element from the other set - Codomain, the set of values is called the Range. 

## Formal Definition
Let $D$ be domain and $C$ be codomain.
$f$ is defined to be a function from $D$ to $C$ ($f: D \rightarrow C$) if
$$f \subseteq D \times C$$ 
$$\forall_{x \in D} \exists_{y \in C} (x, y) \in f$$

$(x, y) \in f$ is equivalent to $f(x) = y$.

$f$ is injection means 
$$\forall_{x_1,x_2 \in D} x_1 \neq x_2 \implies f(x_1) \neq f(x_2)$$

$f$ is surjection means 
$$\forall_{y \in C} \exists_{x \in D} y = f(x)$$

$f$ is bijection means $f$ is injection and $f$ is surjection.


## TODO
- applications of formalism
- definition of mapsto
- visualization