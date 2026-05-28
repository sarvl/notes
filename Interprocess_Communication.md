#operating_systems 

Interprocess Communication comprise variety of methods to communicate between [[Process|Processes]]. 
On [[Linux]] these tools can be viewed with `ipcs`. To use a semaphore, shared memory, or message queue a key is needed, it can be created with `ftok`
## Pipes 
Pipes are special files that act as [[Queue|queues]] for input and output data. They can either be unnamed and must be shared with `fork` or can be named. If there is unpaired `read` or `write` then pipe blocks.

## Semaphores
Semaphores are used for synchronization, see [[Atomic_Operation#Semaphore|Semaphores]].
## Shared Memory
Memory regions that can be accessed by several processes.

## Message Queue
Similar to Pipes but allow for more than one chunk of data to be in flight at once.

## Socket
Generally [[Computer_Network|Network]] thing
## Files

## Signals
Software interrupts.