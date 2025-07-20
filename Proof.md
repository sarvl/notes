#math #logic





## Structure
While usually a proof is expressed as a sentence, a proof structure constructed in a way similar to [[Structured_Programming|Structured Programming]] - decomposing it into basic building blocks, each proving a certain [[Logic#Sentence|Sentence]].

For example to prove 
$$\forall_x P(x) \implies Q(x)$$
The structure would be
```
Let x be arbitrary
	Suppose P(x) is true
		*proof of Q(x)*
	Thus P(x) is true
Thus for all x, P(x) implies Q(x)
```


## Techniques

### Counterexample
For proofs of the form $$\forall_x P(x)$$ It is sufficient to find a single $x$ such that $\lnot P(x)$. Note that lack of counterexample *does not* prove a statement, see [[#Exhaustive Search]].

#### Example
$$\forall_{n \in Primes} 2^n - 1 \in Primes$$
The inner statement is to true for $n \in \{2; 3; 5; 7\}$ but fails for $n = 11$, therefore the entire statement is false.

### Exhaustive Search
For proofs of the form $$\forall_x P(x)$$ it is sufficient to show that every single $x$ satisfies $P(x)$, this is viable only for relatively small [[Set|Sets]].

#### Example
$$\forall_{x \in \{2\}} x \in Primes$$
$2 \in Primes$ and so entire statement is true because that is *the only* value $x$ can take.

## Books
- *How To Prove It - A structured Approach* by Daniel J. Velleman

#book_htpi_dv