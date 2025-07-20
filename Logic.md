#math #logic

In [[Mathematics]], logic is formalization of deductive reasoning, it focuses on arriving on conclusion from premises. 
An Argument is a premises and conclusion together. 
An argument is said to be valid if when premises are true, the conclusion must also be true.

For specific methods of arriving at conclusion see [[Proof]].

Formulas that are always true are called *Tautologies*, while always falls one are *Contradictions*.
A statement may have a variable $x$ in which case it is often denoted $P(x)$, its truth depends on value of $x$,.The [[Set]] of values that make $P$ true is called *Truth Set*.

## Symbols
|symbol | meaning |
|:---:|:---:|
| $$\land$$ | and |
| $$\lor$$ | or (inclusive) |
| $$\lnot$$ | not |
| $$\forall$$ | for all  |
| $$\exists$$ | there exists |
| $$\Rightarrow$$ | implies (if) |
| $$\Leftarrow$$ | left implication |
| $$\Leftrightarrow$$ | equivalent (iff, if and only if)|
| $$\downarrow$$ | not or, negation of result of $\lor$|
| $$\vert$$ | not and, negation of result of $\land$|

### Precedence


## Truth Tables
A Truth Table represents value of an operation given its operands and operator.

### NOT
| $P$ | $\lnot P$ |
|:---: | :---: |
| $0$ | $1$ |
| $1$ | $0$ |

### AND
| $P$ | $Q$ | $P \land Q$ |
|:---:| :---: | :---: |
| $0$ | $0$ | $0$ |
| $0$ | $1$ | $0$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $1$ |

### OR
| $P$ | $Q$ | $P \lor Q$ |
|:---:| :---: | :---: |
| $0$ | $0$ | $0$ |
| $0$ | $1$ | $1$ |
| $1$ | $0$ | $1$ |
| $1$ | $1$ | $1$ |

note the disagreement from common meaning of `or`, this is called *inclusive* or - the default in Mathematics, the other option is called *exclusive* or.

### IMPLICATION
| $P$ | $Q$ | $P \Rightarrow Q$ |
|:---:| :---: | :---: |
| $0$ | $0$ | $1$ |
| $0$ | $1$ | $1$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $1$ |

### EQUIVALENCE
| $P$ | $Q$ | $P \iff Q$ |
|:---:| :---: | :---: |
| $0$ | $0$ | $1$ |
| $0$ | $1$ | $0$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $1$ |

### Combining Expressions
Complex expressions can be combined step by step to form complete truth tables 

for example for statement $(P \land Q) \lor (Q \land R)$ the truth table below can be easily constructed from left to right

| $P$ | $Q$ | $R$ | $P \land Q$ | $Q \land R$ | $(P \land Q) \lor (Q \land R)$ |
|:---:|:---:|:---:|:---:|:---:|:---:|
| $0$ | $0$ | $0$ | $0$ | $0$ | $0$ |
| $0$ | $0$ | $1$ | $0$ | $0$ | $0$ |
| $0$ | $1$ | $0$ | $0$ | $0$ | $0$ |
| $0$ | $1$ | $1$ | $0$ | $1$ | $1$ |
| $1$ | $0$ | $0$ | $0$ | $0$ | $0$ |
| $1$ | $0$ | $1$ | $0$ | $0$ | $0$ |
| $1$ | $1$ | $0$ | $1$ | $0$ | $1$ |
| $1$ | $1$ | $1$ | $1$ | $1$ | $1$ |

This is a useful method for checking equivalence between statements, if two statements have *the same* truth table, then they are equivalent

For example statements $P \lor P$ and $\lnot \lnot P$

| $P$ | $P \lor P$ | $\lnot P$ | $\lnot \lnot P$|
|:---: |:---: |:---: |:---: |
| $0$ | $0$ | $1$ | $0$|
| $1$ | $1$ | $0$ | $1$|

As first, third, and fourth column have the same truthness, they are 
equivalent.


## Laws
All of the laws below can be proven via [[#Truth Tables]]
Given the laws below, statements can be simplified like [[Alebra|Algebraic]] expressions, in fact they lead to [[Boolean_Algebra|Boolean Algebra]]. Another byproduct are [[Set#Laws|Set Laws]]

### De Morgan's Laws
$$\lnot (P \land Q) \iff \lnot P \lor \lnot Q$$
$$\lnot (P \lor Q) \iff \lnot P \land \lnot Q$$

note that full law is more general and applies to [[Set|Sets]] too, to get a version for arbitrary many premises a [[Recursion|Recursive]] argument can be used, demonstrated below for first law
1. Let there be statement $\lnot (P_1 \land P_2 \land \ldots \land P_n)$ for any $n \geq 3$ (the cases with $n = 1$ and $n = 2$ are proven with truth tables)
2. Let $Q = (P_1 \land P_2 \land \ldots \land P_{n-1})$
3. Original statement is now $\lnot (Q \land P_n )$  which is known to be equivalent to $\lnot Q \lor \lnot P_n$
4. $\lnot Q \iff \lnot (P_1 \land P_2 \land \ldots \land P_{n-1})$ which is the same as `1.` but with smaller $n$
5. This process then continues until $n = 2$ where the statement is $\lnot (P_1 \land P_2) \lor \lnot P_3 \lor \ldots \lor \lnot P_n$
6. And so by first Law there is $\lnot P_1 \lor \lnot P_2 \lor \ldots \lor \lnot P_n$

### Commutative Laws
$$P \land Q \iff Q \land P$$
$$P \lor Q \iff Q \lor P$$

### Associative Laws
$$P \land (Q \land R) \iff (P \land Q) \land R$$
$$P \lor (Q \lor R) \iff (P \lor Q) \lor R$$

### Idempotent Laws
$$P \land P \iff P$$
$$P \lor P \iff P$$

### Distributive Laws
$$P \land (Q \lor R) \iff (P \land Q) \lor (P \land R)$$
$$P \lor (Q \land R) \iff (P \lor Q) \land (P \lor R)$$

### Absorption Laws
$$P \lor (P \land Q) \iff P$$
$$P \land (P \lor Q) \iff P$$

### Double Negation Law
$$\lnot \lnot P \iff P$$

### Tautology Laws
$$P \land Tautology \iff P$$
$$P \lor Tautology \iff Tautology$$
$$\lnot Tautology \iff Contradiction$$

### Contradiction Laws

$$P \land Contradiction \iff Contradiction$$
$$P \lor Contradiction \iff P$$
$$\lnot Contradiction \iff Tautology$$
## Argument Forms







## Applications
- [[Logic_Gate|Logic Gate]] - direct implementation of logic, a core component of all [[Digital_Circuit|Digital Circuits]]


## Books
- *How To Prove It - A structured Approach* by Daniel J. Velleman

#book_htpi_dv 

## TODO
- add info about precedence
- scrap some cool exercises from HTPI
- ensure correct usage of *statement*