#computer_architecture 

Central Processing Unit is a unit that executes the instructions in the computer, it is the main control device.


## Simplest Design

![[CPU_Simplest-Design.png]]

This design is somewhat unrealistic as it has separate instruction and data [[Memory]], but it serves as good learning model.

Example instruction walkthrough for `add R3, R1, R2`
1. Fetch instruction and increment [[Instruction_Pointer|PC]]
2. Decode to determine it is `add` and read `R1` and `R2`
3. Add `R1` and `R2`
4. Nothing in memory
5. Write results to `R3`


## Pipelined Design
Exploiting [[Pipelining]] much higher clock frequency can be achiveved.

![[CPU_Pipelined.png]]


## Lectures
- CS61C - UCB 
#lecture_cs61c_ucb