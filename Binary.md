#math 

A bit is the most basic unit of information and the type of data computers usually operate on. Numbers composed out of bits are called to be **Binary**.

**Overflow** is when a magnitude of a number is **too big** to be represented in available bits.
**Underflow** is when a magnitude of a number is **too small** to be represented in available bits.
It is impossible to have integer underflow, it only can happen with [[Floating_Point_Number||Floating Point Numbers]].

## Arithmetic
Binary arithmetic works just like decimal arithmetic with reduced maximum value of a single symbol.

### Example 
```
1101 + 0101 = 

carry 11010
       1101
+      0101
------------
      10010    

```

## Negative Numbers
There are 3 ways to represent negative numbers
- Sign bit - works analogous to typical representation of negative decimal numbers
- Ones' complement - negate all bits to represent negative numbers, this keeps the problem of negative zero but simplifies arithmetic 
- Two's complement - negate and add one, this both removes the problem of negative zero and simplifies arithmetic


Two's complement resembles [[P-Adic_Numbers|P-Adic Numbers]].

## TODO
- prettify
- elaborate on negative number explanation
## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb


