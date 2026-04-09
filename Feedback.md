#electronics #signal 

System with a feedback is any system that adjusts itself based on its output. Lack of feedback leads to poorly controlled [[Electrical_Circuit|Circuits]] and [[System|Systems]].

## Positive


## Negative
Negative feedback is used to remove any deviations from the desired output.

### General System
![[Feedback_General-Negative-Feedback-Network.png]]
The feedback is negative, because it is subtracted from original [[Signal]]. The signal flows in a loop. The error signal must be minimized.

By solving the system we get 
$$Y = A(X - U)$$
$$Y = A(X - KY)$$
$$Y + AKY = AX$$
$$Y = X \frac{A}{1 + AK}$$
For $AK \gg 1$
$$Y \approx \frac{X}{K}$$

When $K = 0$ we call it **open loop system** and 
$$Y = AX$$

The system generally increases the stability of the system, at the cost of reduced gain.
In a well designed system, feedback signal is a good replica of the input signal.

Generally, $K$ is not as sensitive to environment as $A$, for example if [[Resistor]] ratio is used, then both resistors change by the same percentage due to [[Temperature]] (especially on [[Integrated_Circuit|Integrated Circuit]]) and so $K$ does not depend much on temperature.


Finding Loop Gain $AK$:
1. Set input $X = 0$
2. Break the loop anywhere
3. Apply test voltage $V_T$ on one side of broken loop
4. Check feedback voltage $V_F$ on the other side of broken loop
5. $AK = -{V_F \over V_T}$

![[Feedback_Loop-Gain-Procedure.png]]

### Properties
- Desensitization of gain to temperature 
- Bandwidth expansion
  Gain-Bandwidth product is constant
- Modification of [[Input_Output_Impedance|Input and Output Impedances]]
- Higher [[Linearity]]
  Linear over wider range of voltage


### Sensing and Return Mechanisms
![[Feedback_Sense-Mechanism.png]]

![[Feedback_Return-Mechanisms.png]]

![[Feedback_Current-Return.png]]

### Topologies

![[Feedback_Topologies.png]]


### Impedance
![[Feedbac_Voltage-Input-Impedance.png]]

![[Feedback_Impedance-Voltage-Out.png]]

![[Feedback_CS-Imedanece.png]]
![[Feedback_CV-Impedance.png]]

![[Feedback_CC-Impedance.png]]
## Lectures
- *Electronics 2* by Behzad Razavi
#lecture_electronics_br

## TODO
- unify images