#math #logic 
A set is collection of any objects where the order and multiplicity do not matter


## Symbols

| Symbol | Name |
|:---:|:---:|
| $$\{\}$$| encloses a list of objects|
| $$\in$$ | is element of |
| $$\notin$$ | is not element of |
| $$\cup$$ | union |
| $$\cap$$ | intersection |
| $$\setminus$$ | difference |
| $$-$$ | difference |
| $$\subset$$ | proper subset |
| $$\subseteq$$ | subset |
| $$'$$ | complement |
| $$\Delta $$ | symmetric difference |


| Symbol | Set |
|:---:|:---:|
| $$\varnothing$$ | empty set |
| $$\mathbb{N}$$| naturals, non-negative integers |
| $$\mathbb{Z}$$ | [[Integer_Number\|Integers]] |
| $$\mathbb{Q}$$ | [[Rational_Number\|Rationals]] |
| $$\mathbb{A}$$ | [[Algebraic_Number\|Algebraics]] |
| $$\mathbb{R}$$ | [[Real_Number\|Reals]] |
| $$\mathbb{C}$$ | [[Complex_Number\|Complex]] |

## Defining a Set

- Full List
The easiest way is to list all elements enclosed in $\{\}$, for example $\{3;14;15\}$.
- Ellipsis
When the pattern of more elements is clear, for example $\{1;2;3;\ldots\}$
- Set Builder Notation
Like ellipsis but with explicit formula, more flexible, for example $\{n \vert n \mod 2 = 0\}$ is a set of all even integers
- Words
The most general but may easily lead to [[Paradox|Paradoxes]], for example `The set of all sets that do not contain themselves`

## Operations

|symbol | name | meaning |
| :---:| :---: | :---:|
| $$A \cap B$$ | intersection | set of all elements in *both* $A$ and $B$|
| $$A \cup B$$ | union | set of all elements in $A$ or $B$|
| $$A \setminus B$$ | difference | set of all elements in $A$ but not in $B$|
| $$A - B$$ | difference | set of all elements in $A$ but not in $B$|
| $$A'$$ | complement | equivalent to $U - A$ where $U$ is universe of discourse |
| $$A \Delta B$$ | symmetric difference | $A \cup B - A \cap B$|

### Laws

All of the laws below can be proven by reverting back to [[Logic#Laws|Logic Laws]]. Note the usage of $=$ instead of $\Leftrightarrow$.

#### De Morgan's Laws
$$(A \cap B)' = A' \cup B'$$
$$(A \cup B)' = A' \cap B'$$

#### Commutative Laws
$$A \cup B = B \cup A$$
$$A \cap B = B \cap A$$

#### Associative Laws
$$A \cup (B \cup C) = (A \cup B) \cup C$$
$$A \cap (B \cap C) = (A \cap B) \cap C$$

#### Idempotent Laws
$$A \cup A = A$$
$$A \cap A = A$$

#### Distributive Laws
$$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$$
$$A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$$

#### Absorption Laws
$$A \cup (A \cap B) = A$$
$$A \cap (A \cup B) = A$$

#### Double Negation Law
$$A'' = A$$

#### Tautology Laws
$$A \cup U = A$$
$$A \cap U = A$$
$$U' = \varnothing$$

#### Contradiction Laws
$$A \cup \varnothing = A$$
$$A \cap \varnothing = \varnothing$$
$$\varnothing' = U$$

## Relations between Sets

### Equality
$$A = B \Leftrightarrow \left(\forall_{x \in A} x \in B \right) \land \left(\forall_{x \in B} x \in A \right)$$

### Subset
$$A \subseteq B \Leftrightarrow \forall_{x \in A} x\in B$$
$$A \subset B \Leftrightarrow \left(\forall_{x \in A} x\in B\right) \land A \neq B$$

The second one is called *proper* subset

## Connection to Logic
Sets are tightly connected to [[Logic]], especially Truth Sets.
Consider a preposition $P(x): x < 3$, its truthness depends on $x$  and so its truth set is $\{x \vert x < 3\}$, in other words $P(y) \Leftrightarrow y \in \{x \vert x < 3\}$.
This naturally gives a rise to the Empty Set, let $P(x): x \neq x$, its truth set is empty.

Similarly all the logic operations give rise to set operations
consider $P(x)$ and $Q(x)$, the truth set of $P(x) \land Q(x)$ is the set of all $x$ such that both $P(x)$ and $Q(x)$, or the set of $x$ that are both in truth set of $P(x)$ and the truth set of $Q(x)$ - an *Intersection* of sets, similarly *union* and *difference* arise.
$$\{x \vert P(x) \land Q(x)\} \Leftrightarrow \{x \vert P(x)\} \cap \{x \vert Q(x)\}$$ 
$$\{x \vert P(x) \lor Q(x)\} \Leftrightarrow \{x \vert P(x)\} \cup \{x \vert Q(x)\}$$ 
$$\{x \vert P(x) \land \lnot Q(x)\} \Leftrightarrow \{x \vert P(x)\} \setminus \{x \vert Q(x)\}$$ 

in a very similar way, the laws for sets can be derived, see [[Logic#Laws|Logic Laws]].

## Venn Diagrams

## Books
- *How To Prove It - A structured Approach* by Daniel J. Velleman

## TODO
- paradoxes
- ZFC axioms
- basis for natural numbers
- visualization

#book_htpi_dv 