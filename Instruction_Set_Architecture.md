#computer_architecture 

ISA specifies the interface between hardware and software. This includes: set of instructions, [[Memory_Model|Memory Models]], [[IO|IO Communication]].

**Word** is often defined as basic unit that the computer manipulates.

## History
It used to be that updates to ISAs meant more complex instructions, this was eventually criticized by the RISC movement which set foremost the simple ISA design, able to be executed much  faster by CPU and which is much easier to [[Compilation|Compile]] the code for.

## CISC vs RISC
Neither of the terms is actually well defined, several definitions have been proposed but neither took off. This led to RISC becoming a loosely thrown term without much meaning. 

Additionally, some of the original RISC talking points are no longer relevant - transistor count on chips is already way beyond what can be interestingly used, most of it is used for [[Cache|Caches]]. 

For these reasons, it rarely makes sense to talk in RISC/CISC terms, it is always better to use more precise terms like *Register-Register Operations*.


## Executing a Program

The simplest abstraction for instruction execution is:
1. Fetch instruction with Instruction Pointer
2. Read and decode this instruction
3. Execute instruction
4. Write back results
By repeating this procedure, entire programs can be executed.

## Examples
- [[x86]]
- [[ARM]]
- [[MIPS]]
- [[RISC-V]]
- [[PowerPC]]
- [[IA64]]

## TODO
- prettify 
- add more history

## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb