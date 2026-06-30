#operating_systems 

Process is an instance of computer program that is currently being executed. It contains the code and its data. Process memory can be divided into: [[Data_Structures#Stack|Stack]], [[Data_Structures#Heap|Heap]], data, and text  (source). Each process is defined by Process Control Block which contains snapshot of the execution environment, used when switching contexts in [[Operating_System|Operating Systems]]. It is possible to limit number of allowed instances to one.cu


A process can be in one of several states:
- `new` - during creation, can switch to being `ready` 
- `ready` - waiting to run, can switch to `running` on [[Scheduling|Scheduler]] dispatch.
- `running` - being executed, can switch to `ready` on [[Interrupt]], to `waiting` on waiting for some event, or to `terminated` on completion
- `waiting` - waiting for some event, can switch to `ready` once that event occurs
- `terminated` - finished execution


Simple Scheduling works with ready queue and several events that can stop the process from execution or that put new process into this queue, these events are:
- io request
- time slice expired
- [[Fork]]
- waiting for interrupt

Processes are generally organized in hierarchical manner

A process is composed out of threads which are  basic unit of CPU utilization, they comprise thread ID, set of registers, and a stack.  Threads within a process share operating system resources.