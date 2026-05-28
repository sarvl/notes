#operating_systems #computer_science #computer_architecture 

An atomic operation is one that executes as one and cannot be split. Most instructions using memory are not atomic.

## Problem

Imagine a sequence of [[x86]] instructions implementing
```C
volatile int a = 1;
volatile int b = 5;

a = a + b;
```

```x86
mov DWORD [a], 1
mov DWORD [b], 5


mov ebx, DWORD [b]   ; 1
add DWORD [a], ebx   ; 2 
```

In C, last line appears to be single operation, but on assembly level it is 2 instructions. Therefore if these variables shared, and another process is scheduled between `1` and `2`,  the result might get unpredictable.
Even more, since `2` is usually 3 micro instructions, if another process executes on another core, this might cause data overwrite.

## Test and Set 
If value at memory is 0, then set it to 1 and return 0.
If value at memory is 1, then leave it at 1 and return 1.

```
value = 0;

acquire()
{
	while(testandset(value))
		;
}

release()
{
	value = 0;
}
```

This unfortunately is busy waiting which consumes CPU resources.
## Semaphore 
Non negative integer with two operations: `down()` or `p()` which waits until semaphore becomes positive, then decreases it by one  and `up()` or `v()` which increments semaphore by one, waking up waiters, if any.

Semaphore can be used to create mutual exclusion sections or to signal information to other thread.