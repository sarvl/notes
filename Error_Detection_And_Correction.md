#signal #information #math #telecom #networking 


## Error Detection

### Parity Check
Add a single [[Binary|Bit]] that makes total count of $1$s even or odd. For example $10101$ with even parity is $10101'1$. When the sum of $1$s is not even/odd on the receiver end, there must have been odd number of errors.

### Checksum
Add several bits denoting total sum of [[Binary|bits]]. For example $1011$ will turn into $1011'10$.

### Cyclic Redundancy Check
Polynomial division used to detect burst errors.

#### Algorithm
1. Select some generating polynomial $G$ of order $r$
2. Divide (modulo 2) the bit sequence by the sequence representing $G$, otherwise move to the right 
3. Append the remainder to the original sequence

#### Example
Let $G = x \mapsto x^2 + 1$
Let input be $11001$

```
 11001 : 101
 101
 ----
  110
  101
  ----
   111
   101
   ----
    10
```

The transmitted sequence is $11001'10$

## Error Correction

### Automatic Repeat Request ARQ

Repeat particular set of transmitted blocks.

#### Stop and Wait

#### Go-Back-N

#### Selective Repeat


## Combined Error detection and Correction

## Repetition
Send each bit odd number of times, if any difference => error, use the majority vote to determine proper bit.

## Parity for Columns and Rows
Arrange bits in a rectangle. Each row and column has a parity bit, if an error occurs in a block => parity error in row/column points to position. If an error occurs in parity => singular parity disagreement.

### Hamming Code

### Redd-Solomon Code




## TODO
- examples
- advantages
- figure out better description of CRC