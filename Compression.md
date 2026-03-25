#information #signal #computer_science 

Compression is way of changing data representation to remove redundant or irrelevant [[Information_Theory|Bits]] in it.

## Lossless
Used for text or binary files, where information must be restored exactly.


### Huffman Coding
Assigns shorter code to character that occur more frequently. 

#### Algorithm
1. Sort messages by probability
2. Connect two least frequent nodes with new node of combined probability. 
3. Repeat until tree with all nodes has been created.
4. Assign $0$ to one child of each node, and $1$ to the other.

#### Example
Let:
- $p(m_1) = 0.24$
- $p(m_2) = 0.12$
- $p(m_3) = 0.02$
- $p(m_4) = 0.04$
- $p(m_5) = 0.32$
- $p(m_6) = 0.20$
- $p(m_7) = 0.04$
- $p(m_8) = 0.02$

![[Compression_Huffman-Coding.png]]
## Lossy
Used for images, video, and audio, where loss of some information is not a problem.



## TODO
- examples 
- proofs