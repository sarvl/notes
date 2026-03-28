#computer_architecture 

Pipelining is the act of splitting design into several distinct stages. As in single-cycle design, the [[Clock]] frequency is limited by longest instruction, splitting all instructions into stages improves frequency drastically. Not only is the frequency higher, instructions are overlapped.


Pipelining does not improve **Latency**, it improves **Throughput**.

## General Idea
Assume we have to do A, B, C, and D; each letter has 4 stages; each one is independent from each other

By doing them all separately we get
```
A 1 2 3 4
B         1 2 3 4 
C                 1 2 3 4 
D                         1 2 3 4 
```
This one ends in 16 stages.

By overlapping them
```
A 1 2 3 4
B   1 2 3 4
C     1 2 3 4
D       1 2 3 4 
```
This one ends in 7 stages.


## CPU


![[CPU_Pipelined.png]]


## Hazards

- **Structural**
  Resource is busy
  Either stall or duplicate resources
- **Data**
  Data dependency between instructions
  Wait for the data, do some forwarding (passing data between stages)
  See [[Value_Prediction|Value Prediction]]
- **Control**
  Control dependency between instructions 
  Wait for the data, do some forwarding (passing data between stages), possibly flush pipeline
  See [[Branch_Prediction|Branch Prediction]]
  

## Lectures
- CS61C - UCB 
#lecture_cs61c_ucb


## TODO
- write about passing control data thru pipeline registers
- More on bubbles

