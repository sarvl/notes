#operating_systems #computer_science 

There is no universally accepted precise definition, but generally, OS is software that controls the given hardware and provides layer of abstraction for [[Program|Programs]] to work on.

Most often, operating system includes
- [[Memory_Management|Memory Management]]
- [[IO_Management|IO Management]]
- [[Scheduling|Scheduling]]
- [[Interprocess_Communication|Interprocess Communication]]
- [[File_System|File System]]
- [[UI|User Interface]]
- [[Multitasking]]
- [[Multiprogramming]]
- Resource Management
- [[Error_Management|Error Management]]
- Standard Libraries
- [[Wiindowing_System|Windowing System]]
- [[Proccess_Protection|Protection]]

The main problem is that hardware is different, and so the OS has to be designed with standard interfaces in mind.

The OS uses [[Computer_Storage#Non Volatile|Non-volatile Storage]] to store [[Program|Programs]]. 

In the case of simple OS supporting only one Program at once, the  OS becomes essentially set of standard libraries. [[Multitasking|Multitasking]] is what introduces most interesting concepts.

Each OS requires some interface, most interfaces can  be categorized as [[UI#GUI|GUI]] or [[UI#CLI|CLI]].

Operating systems often maintain cache of copies, for example on access files are copied from storage to memory. 