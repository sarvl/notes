
Any LTI [[System]] has a property that for input $x[n] = z^n$, where $z \in \mathbb{C}$, $y[n] = H(z) z^n$. In other words, [[Exponential_Function|Exponentials]] input retains its shape after passing through LTI system. Z-Transform is a [[Function#Transform|Transformation]] allowing to translate any signal as sum of exponentials, such sum can then be easily then passed through such system, and the output can be inversely transformed to find the actual output.

Mathematically speaking, complex exponentials are [[Eigenvalue|Eigenfunctions]] of LTI system.

If $x[n] = \sum c_k z_k^n$ then $y[n] = \sum c_k H(z_k) z_k^n$.  If some $H(z_k) = 0$ then we say that $z_k^n$ is filtered out, providing basis for [[Digital_Signal_Processing#Filter|Filtering]].


Z-Transform of sequence $x[n]$ is a function $X(z)$ defined by
$$X(z) = \sum_{n=-\infty}^{n=+\infty} x[n] z^{-n}$$

The [[Series]] may or may not be convergent for all values of $z$, the series for which it is convergent is called Region of Convergence.
$z$ for which $X(z) = 0$ are called zeros and $z$ for which $X(z) = \pm \infty$ are called poles.  By definition, ROC does not include poles.

For example, the unit sample sequence has 
$$ X(z) = \sum \delta[n] z^{-n} = z^0 = 1$$
With ROC being all $z$.

The square pulse has 
$$ X(z) = \sum_{n=0}^{n=M} z^{-n} = \frac{1-z^{-M - 1}}{1 - z^{-1}}$$
for nonzero $z$ and $X(0) = 0$.

The exponential pulse has 
$$ X(z) = \sum_{n=0}^{n=M} a^n z^{-n} = \sum_{n=0}^{n=M} (az^{-1})^n = \frac{1-a^{M+1}z^{-M - 1}}{1 - az^{-1}}$$
for nonzero $z$ and $X(0) = 0$.

The decaying causal exponential sequence has 
$$ X(z) = \sum_{n=0}^{n=\infty} a^n z^{-n} = \sum_{n=0}^{n=\infty} (az^{-1})^n = \frac{z}{z - a}$$
with ROC for $|z| > |a|$

![[Z_Transform_Pairs.png]]

ROC properties
- ROC cannot include any poles
- ROC is connected region
- For finite duration sequences, ROC is the entire $z$-plane, possibly excluding $z=0$ and $z=\infty$
- For finite duration there are 3 possible shapes
  ![[Z_Transform_ROC-Shapes.png]]

Z-Transform of a sequence consists of a formula and associated ROC, both are needed to specify a sequence $x[n]$.
$X(z)$ is not defined outside ROC, even when formula yields values.

The inverse transform is given by 
$$x[n] = \frac{1}{2\pi i} \oint_C X(z) z^{n-1}dz$$
Which formally requires [[Integration#Complex|Complex Integration]] with residues.  
Though for most sequences the inverse can be done by decomposing $X(z)$ into [[Function#Rational|Rational  Functions]], then doing [[Fraction_Decomposition|Fraction Decomposition]], and finally using lookup-table.
This may lead to few possibilities, but there is only one possibility where all sequences are causal.


Properties
-  [[Linearity|Linear]]
- Time shifting
  $x[n-k] \leftrightarrow z^{-k}X(z)$
- [[Convolution]]
  $x_1[n] * x_2[n] \leftrightarrow X_1(z)X_2(z)$
- Multiplication by exponential sequence
  $a^n x[n] \leftrightarrow X(z/a)$
  with ROC = $|a| R_x$
- [[Differentiation]]
  $nx[n] \leftrightarrow -z \frac{dX(z)}{dz}$
  with ROC = $R_x$
- [[Complex_Number|Conjugation]]
  $x^*[n] \leftrightarrow X^*(z^*)$

![[Z_Transform_Properties.png]]

Finding response of the system $y[n] = x[n] * h[n]$ is as simple as $Y(z) = X(z)H(z)$

For system to be stable, the necessary condition is ROC = $|z| > r \in \mathbb{R}$
LTI system is stable, if and only if the ROC of the system includes $|z| = 1$

LTI system is both stable  and causal, if and only if the ROC of the system includes $|z| = 1$ and all its pole are inside this unit circle

For [[DIfference_Equation|Linear Constant-Coefficient Difference Equation]] of the form
$$y[n] = \sum_{k=0}^{M} b_k x[n-k] - \sum_{k=1}^Na_ky[n-k]$$
The equation can be Z-Transformed into
$$Y(z)\left(1 + \sum_{k=1}^Na_kz^{-k}\right) = X(z)\sum_{k=0}^{M} b_k z^{-k} $$

$$H(z) = \frac{Y(z)}{X(z)} = \frac{\sum_{k=0}^{M} b_k z^{-k}}{1 + \sum_{k=1}^Na_kz^{-k}} $$
RHS can be converted into [[Function#Rational|Rational Function]], of which poles and zeros can be found. 

Based on parameters of LCCDE, LTI system can be classified depending on 
- Length of impulse response
  When at least one nonzero pole of $H(z)$ is not canceled by a  zero, there  will be a term of the form $A_k(p_k)^nu[n]$. Which leads to $h[n]$ having infinite duration and system being called [[System#Infinite Impulse Response|Infinite Impulse Response]].
  When $N=0$ then system function becomes polynomial and the system is called [[System#Finite Impulse Response|Finite Impulse Response]]. 
- Feedback
  If  $N \ge 1$ the system is [[Recursion|Recursive]]. Otherwise it is nonrecursive.
- Poles and Zeros
  If $a_{1 \le k \le N} = 0$ then the system has M zeros (all zero system) 
  If $b_{1 \le k \le M} = 0$ then the system has N poles (all pole system) 

System with all coefficients real can be split into the form 
$$H(z) = \sum_{k=0}^{k=M-N} C_k z^{-k} + \sum_{k=1}^{K_1} \frac{A_k}{1-p_kz^{-1}} + \sum_{k=1}^{K_2} \frac{b_{k0} + b_{k1}z^{-1}}{1+a_{k1}z^{-1} + a_{k2}z^{-2}}$$
Where $K_1 + 2K_2 = N$
In words, $H(z)$ is a parallel combination of FIR system, $K_1$ first order systems with real poles, and $K_2$ second order systems with complex conjugate poles.

![[Z_Transform_First-Order-System-Response.png]] 

![[Z-Transform_Second-Order-System-Response.png]]


One sided Z-Transform is  defined as 
$$X^+(z) = \sum_{n=0}^{n=+\infty} x[n] z^{-n} = \mathcal{Z}\{x[n]u[n]\}$$
Almost all properties stay the same except for time shift
$$Z^+\{x[n-k]\} = z^{-k}X^+(z) + \sum_{m=1}^{m=k}x[-m]z^{m-k}$$

%% 
## TODO
- verify ROCs
- sections
- add ADSP reference
