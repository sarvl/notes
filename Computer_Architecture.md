#computer_architecture 

Computer Architecture focuses on organization and, to some extent, implementation of various [[Processor|Processors]] designed to process data in a specific way.  It is a study of how to most efficiently reach certain design goals - for example increasing throughput of [[Graphical_Processing_Unit|GPUs]].

Example objects of interest include
- [[Central_Processing_Unit|Central Processing Units]]
- [[Graphical_Processing_Unit|Graphical Processing Units]]
- [[Digital_Signal_Processing|Digital Sound Processors]]

Everything is a number, such number is composed out of individual [[Binary|Bits]]. 

The organization and implementation often mean
- [[Digital_Electronics|Digital Circuit]] level implementation
- [[Network|Interconnects]]

Ultimately, the topic is very broad with many different goals and requirements, and so this document is abstract in nature. Many links are provided for more detailed topics. 

## Main Ideas
- Abstraction
  Create a specific interface such that higher level constructs can be created regardless of implementation, the prime example is [[Instruction_Set_Architecture|Instruction Set Architecture]]
- Moore's Law
  The most important trend in the development of computers, significant increase in the number of [[Transistor|Transistors]] available, despite numerous advancement in [[Transistor#Fabrication|Fabrication]] technology the trend has been slowing down
- [[Locality]]
  Data in similar space tends to be accessed in similar time
- [[Parallelism]]
  A lot of stuff can be done at once 
- [[Speculative_Execution|Speculation]]
  Speculating on results allows to break through various performance limits
- [[Performance_Measurement|Performance Measurement]]
  The only way to improve is to know what is wrong
- [[Redundancy]]
  The easiest way to be dependable is to provide alternative in case of failure

## Structure of a Computer
![[Computer_Architecture_Computer-Structure.png]]

**Control** is the component responsible for directing how the computer works, **Datapath** is the component that actually executes. In modern CPUs Control generally dominates datapath. 

Instruction is a basic way of interacting within any processor, it is defined by [[Instruction_Set_Architecture|ISA]]. Generally all instructions can conceptually be split into 4 execution stages. These stages can be then used to either create [[Central_Processing_Unit#Multicycle|Multicycle]] design or  to [[Pipelining|Pipeline]] it.
1. Fetch 
   Read [[Binary|Bits]] from [[Memory]], change [[Instruction_Pointer|Instruction Pointer]]
2. Decode 
   Figure out what has to be done
3. Execute
   Do what needs to be done 
   [[Arithmetic_Logic_Unit|ALU]], [[Floating_Point_Unit|FPU]], [[Memory]]
4. Writeback
   Save results from computation, usually into [[Register_File|Register File]]
## Organization
It is in general impossible to simply classify all different kinds of processors there are, different categories exist based on different goals.

### RISC vs CISC
This classification is obsolete and was never properly defined in the first place, refer to [[RISC]] for detailed criticism.

### Program Location
- **Stored Program**
  Data and program are stored in the same kind of [[Memory]] and can be used interchangeably 
  This allows for machine reprogramming on the fly
- **Harvard**
  Data and program are stored in separate memories, usually program is in some kind of [[ROM]]
  Allows for much faster and simpler execution
- **Mixed**
  Nowadays, virtually all [[Instruction_Set_Architecture|ISAs]] are Stored Program, but high performance hardware have separate [[Cache|Caches]] for data and instructions
  Combines perks of both with minimal complications

## Design
Design can be somewhat separated into two parts - [[Instruction_Set_Architecture|ISA]] and implementation. However one cannot be properly created without some general view of  the other.

### General Considerations

### ISA

### Implementation

Small units can be designed directly with [[Boolean_Algebra|Boolean Algebra]] minimization techniques, but this quickly gets out of hand. Designing more complex devices requires using standard functional units:
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
- some specific design process? could take one from CS61C L12 but seems way too specific
-  better design specifiation


## Lectures
- CS61C - UCB 
- Onur Mutlu - ACA


#lecture_om_ACA #lecture_cs61c_ucb