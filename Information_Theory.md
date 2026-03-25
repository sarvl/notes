#math #information #computer_science #networking #telecom 

Information Theory is a probabilistic description of information.  Bit is the most basic unit of information. Amount of information is expressed by the probability of sending a given message by a source. If a source  sends a symbol which appears with probability $p$ then the symbol carries $- \log_2 p$ amount of information.

Entropy is a measure of uncertainty.

Theoretical maximum data rate over a communication channel is $$C = B  \cdot \log_2\left(1 + \frac{S}{N}\right)$$ where 
	$C$ is channel capacity in $b \over s$
	$B$ is channel bandwidth in $Hz$
	$\frac{S}{N}$ is [[Signal#Parameters|SNR]]



## Entropy
Entropy of random variable $X$, with $|X| = N$ with discrete [[Probability]] distribution $p$ is defined to be 
$$H(X) = - \sum_{i} p_i \log_2{p_i}$$
- $\lim_{p \to 0}\left(p \cdot \log_2{p}\right) = 0$
- $0 \le H(x) \le log_2(N)$
- If a message $i$ has $p_i = 1$ then $H(X) = 0$
- If a distribution is uniform then $H(x) = \log_2{N}$

## Transmission Channels
A transmission channels transforms a set of input messages $X$ with $|X| = N$ into set of output $Y$ with $|Y| = M$ with some probability of each transition

**Total Entropy** is defined as ..
**Mutual Information** is defined as ..
**Conditional Entropy** is defined as ..
### Discrete Memory-Less Channel
Fully described by $M \times N$ matrix of probabilities of transition $X[i] \to Y[j]$

### Binary Symmetric Channel
A special case of [[Information_Theory#Transmission Channels#Discrete Memory-Less Channel|Discrete Memory-Less Channel]] where $X = Y = \{0; 1\}$ and $P(0|1) = P(1|0) = p_{err}$

 ## TODO
- organize
- images
- explain where the formulas comes from