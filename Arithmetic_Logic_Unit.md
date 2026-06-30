#digital #electronics #computer_architecture 

Arithmetic Logic Unit is the basic execution unit of [[Central_Processing_Unit]]. It performs: [[Arithmetic_Logic_Unit#Binary Adder|Addition/Subtraction]], [[Logic_Gate|Logic Operations]], and sometimes [[Arithmetic_Logic_Unit#Binary Multiplier|Multiplication]] and [[Arithmetic_Logic_Unit#Binary Divider|Division]].  ALU is simply a [[Multiplexer|Mux]] between these operations.

Sometimes these internal computations consume too much [[Power]], in that case  additional logic can be implemented to reduce it, at a cost of reduced speed.

ALUs may output [[CPU_Flag|CPU Flags]].

## Full ALU
<div class="fig">
<img src="./images/ALU.png"><br>
<sup>Simple ALU implementation</sup>
</div>



## Binary Adder
Binary Adder adds at least 2 [[Number_System#Binary|Binary]] numbers. The simplest configuration is by chaining [[Arithmetic_Logic_Unit#Binary Adder#Full Adder|Full Adders]], this however is very slow and not generally used.

Due [[Number_System#Binary#Negative Numbers|Two's Complement]] behavior, to subtract it is enough to negate the second number and add 1 with carry-in.

### Full Adder

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

### Schematic
![[Binary_Adder_Full-Adder-Subtractor.png]]

## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb

%% 
## TODO
- custom schematic for binary adder