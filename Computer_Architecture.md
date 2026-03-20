#computer_architecture 

Computer Architecture focuses on organization and, to some extent, implementation of various [[Processor|Processors]] designed to process data in a specific way. 

Everything is a number, such number is composed out of individual [[Binary|Bits]]. 

Most common types of devices are
- [[Central_Processing_Unit|Central Processing Units]]
- [[Graphical_Processing_Unit|Graphical Processing Units]]

The organization and implementation often mean
- [[Digital_Electronics|Digital Circuit]] level implementation
- [[Interconnect|Interconnects]]

## Main Ideas
- Abstraction
  Create a specific interface such that higher level constructs can be created regardless of implementation, the prime example is [[Instruction_Set_Architecture|Instruction Set Architecture]]
- Moore's Law
  The most important trend in the development of computers, significant increase in the number of [[Transistor|Transistors]] available
- [[Locality]]
  Data in similar space tends to be accessed in similar time
- [[Parallelism]]
  A lot of stuff can be done at once 
- [[Performance_Measurement|Performance Measurement]]
  The only way to improve is to know what is wrong
- [[Redundancy]]
  The easiest way to be dependable is to provide alternative in case of failure

## Structure of a Computer
![[Computer_Architecture_Computer-Structure.png]]


## Organization
The main types of organization are 
- Stored Program Computer
  Data and Program are stored in the same region of [[Memory]] 
  Lets user easily reprogram the machine
- Harvard Architecture
  Data and Program are stored separately
  Is much faster and simpler at hardware level

Nowadays, a mix is used, internally the machine is implemented as Harvard Architecture but the interface from [[Memory_Controller|Memory Controller]] works like Stored Program Computer.
## TODO
- more examples


## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb