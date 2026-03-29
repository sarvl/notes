#computer_architecture  #cybersecurity

Meltdown is a type of attack exploiting [[Speculative_Execution|Speculative Execution]], it uses [[Side_Channel_Attack|Side Channel]] to exploit information a [[Process]] should not have access to.

## High Level Overview
While the paper talks about [[Out_Of_Order_Execution|Out of Order Execution]], this is more strict than it needs to be, a particular arrangement of [[Pipelining|Pipeline]] stages could lead to the same vulnerability. 

Meltdown exploits [[Speculative_Execution|Speculative Execution]] and existence of [[Cache|Caches]]. By executing code that should not execute and populating Cache in particular way, [[Side_Channel_Attack|Side Channel Attack]] takes place by measuring difference in access times.

This can ultimately lead to reading the full physical memory as [[Kernel|Kernels]] often map entire available RAM into a region within [[Virtual_Memory|Virtual Memory]]. Completely bypassing all security features.

## Attack Description
Meltdown consists of two parts
1. Executing Transient Instructions
2. Transferring microarchitectural state into architectural state
### Executing Transient Instructions
Let there be snippet of code
```c
/*1*/ raise_exception(); 
/*2*/ access(probe_array[data * 4096]);
```
As line `1` leads to an exception, line `2` should never execute, but with [[Speculative_Execution|Speculative Execution]], line `2` does execute. Sensitive `data` is used to access an array which later can be timed to see what is the value of `data`.

There are 2 ways of achieving the line `1`:  Exception Handling and Exception Suppression.
Exception Handling works by setting up a [[Signal_Handler|Signal Handler]] or by [[Fork|Forking]] the [[Process]]. Thereby catching the exception without crashing the Process. 
Exception Suppression works by using [[Transactional_Memory|Transactional Memory]] which allows for grouping of memory accesses into single [[Atomic_Operation|Atomic Operation]]. If an exception occurs within Transaction, nothing is actually executed, but data is put in the [[Cache]].

Similar approach to Exception Suppression is taken by [[Spectre]] which trains [[Branch_Prediction|Branch Predictor]] in a very specific way.

### Transferring Microarchitectural State
Data is extracted with [[Cache#Covert_Channel|Flush and Reload]] method.

First, inside the speculative part, data has to be used to access array such that each different value maps to different cache line - like line `2`. 
Then, inside architectural part, access time to each part of the array is measured. Short access time means the data was cached, and so it was used in the speculative part, leaking sensitive information.

This part is generally the bottleneck, it takes much longer to test  all possible cache lines than to execute memory access.


There is no inherent need to use this particular [[Covert_Channel|Covert Channel]], it is possible to use [[Execution_Units|Execution Units]] and see latency of using particular port. This method has however an advantages of simplicity, reduced noise, and being indifferent to [[Core]] on which the [[Process]] runs (provided cache is inclusive).

### Limitations
Due to implementation details, `0` appears more often than it should. Most likely the core assumes such value if actual value is not available. For this reason, reading `0` leads to a number of retries. [[Transactional_Memory|Transactional Memory]]  drastically reduces the probability of erroneously reading `0`.

Kernel Address Space Layout Randomization varies address used by kernel, but it does  so with some granularity. Thus on all practical machines with limited RAM, relatively few tests are required to figure out the actual data address. 
## Countermeasures
The source of this problem lies in delayed [[Privilege]] check, therefore it is both necessary and sufficient to properly check whether a given [[Process]] has rights to access [[Memory]] before it is accessed. Using permission bit is often too slow, hard split in address space configured in some configuration register is however sufficient.

As software measure, KAISER can be used to unmap most of kernel address space and significantly reducing attack surface. However [[x86]] requires some amount of mapped data and so it is not full Meltdown prevention.


## Papers
- *Meltdown: Reading Kernel Memory from User Space* by Lipp et al.


#paper_meltdown-reading-kernel-memory-from-user-space_ml-ms-dg-tp-wh-af-jh-sm-pk-dg-yy-mh