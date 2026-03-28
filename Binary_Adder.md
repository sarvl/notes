#digital #electronics #computer_architecture 

Binary Adder adds at least 2 [[Binary]] numbers. The simplest configuration is by chaining [[Binary_Adder#Full Adder|Full Adders]], this however is very slow and not generally used.

Due [[Binary#Negative Numbers|Two's Complement]] behavior, to subtract it is enough to negate the second number and add 1 with carry-in.

## Full Adder

| $A$ | $B$ | $C_{in}$ | $S$ | $C_{out}$ |
| --- | --- | -------- | --- | --------- |
| $0$ | $0$ | $0$      | $0$ | $0$       |
| $0$ | $0$ | $1$      | $1$ | $0$       |
| $0$ | $1$ | $0$      | $1$ | $0$       |
| $0$ | $1$ | $1$      | $0$ | $1$       |
| $1$ | $0$ | $0$      | $1$ | $0$       |
| $1$ | $0$ | $1$      | $0$ | $1$       |
| $1$ | $1$ | $0$      | $0$ | $1$       |
| $1$ | $1$ | $1$      | $1$ | $1$       |
$$S = A \oplus B \oplus C_{in}$$
$$C_{out} = MAJ\left(A, B, C_{in}\right)$$



![[Binary_Adder_Full-Adder-Subtractor.png]]

## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb