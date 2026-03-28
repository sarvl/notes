#electronics #digital 

A branch of [[Electronics]] operating on discrete values, usually via [[Boolean_Algebra|Boolean Algebra]], a concrete implementation of [[Computer_Architecture|Computer Architecture]].

**Digital** means that the allowed voltage levels are quantized, in contrast to [[Analog_Electronics|Analog Electronics]] which operates on continuous range of values.

Two types are **Synchronous** and **Asynchronous**, the latter circuit is always a pure [[Function]] of inputs, the former also has some internal state and can be realized as a [[State_Machine|State Machine]]. The main advantage of async circuit is its speed - it always operates not slower than synchronous equivalent. The main advantages of sync circuit is resistance to [[Noise]] and simpler design by introducing [[Clock]]. 

[[Signal|Signals]] are often grouped into **Buses**.
![[Digital_Electronics_Grouping.png]]

Notice that compared to software, it is impossible to single step changes, during single clock transition (marked as dashed line), several things change at once. In this case they are related but in general they need not be.

Modern digital circuits are based on [[Transistor|Transistors]].

## Circuit Design

### Asynchronous 
First, create a [[Boolean_Algebra#Truth Table|Truth Table]], matching inputs to outputs. Then use one of 
1. [[Boolean_Algebra|Boolean Algebra]]
2. [[K-Map]]
To find the minimal function.

In practice, this is always done by automatic tools.

## Synchronous
Synchronous Digital systems consist of [[Digital_Electronics#Circuit Design#Asynchronous|Combinational Logic]] blocks and Sequential Logic blocks.

Sequential Logic blocks are various [[Register|Registers]] and [[Memory|Memories]].

Some circuits - like accumulator - are only possible as Synchronous logic.

![[Digital_Electronics_Synchronous-Example.png]]


![[Digital_Electronics_General-Model-of-Synchronous-System.png]]

![[Digital_Electronics_Accumulator_1.png]]
![[Digital_Electronics_Accumulator_2.png]]

![[Digital_Electronics_Frequency.png]]

**Critical Path** is the path with longest total delay.

![[Digital_Electronics_Pipelining.png]]

[[Pipelining]] introduces more latency but it might reduce overall clock frequency, it does not need to however because at some point extra delay from [[Register|Registers]] becomes  the dominating part.


The design can be done with [[Finite_State_Machine|Finite State Machines]].
1. Draw the FSM
2. Assume state transitions are on clock edge
3. Create Combinational Logic for each stage

## Example Circuits
- [[Binary_Adder|Binary Adder]]


## Timing Requirements
As all circuits are physical things, they take time to propagate data from inputs to outputs.

![[Digital_Electronics_Propagation-Delay.png]]

**Setup Time** is How long data has to be set up before clock edge.
**Hold Time** is How long data has to be hold still after clock edge.
**CLK-to-Q Delay** is how long from clock change to data output.


## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb

## TODO
- threshold voltages
- calculation of maximum frequency