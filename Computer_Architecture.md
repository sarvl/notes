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

**Control** is the unit responsible for directing how the computer works, **Datapath** is the unit that actually executes. In modern processors Control generally dominates datapath. 

An instruction generally has 5 stages of execution
- Fetch 
  Reads bits from [[Memory]]
  increments [[Instruction_Pointer|Instruction Pointer]]
- Decode
  Figure out control signal
  Read data from [[Register_File|Register File]]
- Arithmetic
  Arithmetic and Logic Operations with [[Arithmetic_Logic_Unit|ALU]]
  Calculate address
- Memory
  Load and Store data from and to [[Memory]]
  Thanks to [[Cache]] this stage is fast
- Writeback
  Save the results to [[Register_File|Register File]]
This naturally leads to [[Classic_Risc_Pipeline|Classic RISC Pipeline]]. 

Even though not all simple instructions use all these stages, some (like Load) do, and so it is necessary to make hardware that supports all of them.

## Organization
The main types of organization are 
- Stored Program Computer
  Data and Program are stored in the same region of [[Memory]] 
  Lets user easily reprogram the machine
- Harvard Architecture
  Data and Program are stored separately
  Is much faster and simpler at hardware level

Nowadays, a mix is used, internally the machine is implemented as Harvard Architecture but the interface from [[Memory_Controller|Memory Controller]] works like Stored Program Computer.

## Design
Small units can be designed directly with [[Boolean_Algebra|Boolean Algebra]] minimization techniques, but this quickly gets out of hand. To design more complex devices, heavily rely on abstraction, standard functional units are employed
- [[Multiplexer]]
- [[Arithmetic_Logic_Unit|Arithmetic and Logic Unit]]
- [[Binary_Adder|Adder/Subtractor]]
- [[Register_File|Register File]]
- [[Memory]]
- [[Comparator]]


1. Analyze required [[Instruction_Set_Architecture|ISA]] to determine datapath requirements
   Meaning of each instruction is given by [[Register]] transfers
   It is important to think very ahead, it would be very hard to implement core processor feature (like [[Interrupt|Interrupts]] or [[Virtual_Memory|Virtual Memory]]) into processor that was not designed with it in mind
2. Select datapath components and establish [[Clock]] methodology
3. Assemble datapath
4. Analyze implementation of each instruction to determine setting of control points
5. Assemble the control logic





## TODO
- more examples
- generalize to remove RISC bias
- some specific design process? could take one from CS61C L12 but seems way too specific


## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb