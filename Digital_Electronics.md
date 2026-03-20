#electronics #digital 

A branch of [[Electronics]] operating on discrete values, usually via [[Boolean_Algebra|Boolean Algebra]], a concrete implementation of [[Computer_Architecture|Computer Architecture]].

**Digital** means that the allowed voltage levels are quantized, in contrast to [[Analog_Electronics|Analog Electronics]] which operates on continuous range of values.

Two types are **Synchronous** and **Asynchronous**, the latter circuit is always a pure [[Function]] of inputs, the former also has some internal state and can be realized as a [[State_Machine|State Machine]].


Modern digital circuits are based on [[Transistor|Transistors]].


## Circuit Design

### Asynchronous 
First, create a [[Boolean_Algebra#Truth Table|Truth Table]], matching inputs to outputs. Then use one of 
1. [[Boolean_Algebra|Boolean Algebra]]
2. [[K-Map]]
To find the minimal function.

In practice, this is always done by automatic tools.


## Example Circuits
- [[Binary_Adder|Binary Adder]]


## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb

## TODO
- threshold voltages