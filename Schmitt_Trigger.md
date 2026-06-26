#electronics  #analog 

Schmitt trigger is a name for any [[Buffer]] showing [[Hysteresis]].  It can be constructed from any system exhibiting [[Feedback#Positive|Positive Feedback]].



## Inverting
![[Schmitt_Trigger_Inverting.png]]

Using [[Opamp]] is a way to implement easy to understand schmitt trigger.

As $V_i = V_-$ gets larger than $V_+ = \beta V_o = \beta V_{ss}$, the output goes down, decreasing $V_+$ even further until $V_o$ reaches $-V_{ss}$. The same applies going in the other direction.

Note that $A\beta \gg 1$ in order to prevent instability

The horizontal range between switching voltages may be  referred to as hysteresis.

## Noninverting
![[Schmitt_Trigger_Noninverting.png]]

$V_o$ is given as $\frac{V_o}{A} = \frac{V_o R_1}{R_1 + R_2} + \frac{V_i R_2}{R_1 + R_2}$, that is, it is a weighted arithmetic average between $V_o$ and $V_i$. 
As soon as the arithmetic average gets slightly positive, positive feedback pushes $V_o$ further, the same happens in the other direction.
It gets positive (or negative) when $V_o R_1 = V_1 R_2$ so $V_i = \pm V_{ss} \frac {R_1}{R_2}$, depending on the direction.

In this case $\beta$ comes out to be $\frac{R_1}{R_2}$

## Astable Multivibrator
Astable multivibrator means that a circuit switches between two states continuously.

![[Schmitt_Trigger_Astable-Multivibrator.png]]

This circuit can be thought of as series combination of inverting schmitt trigger and [[Analog_Signal_Processing#Low Pass Filter|LPF]].

The circuit is triggered as soon as output of  LPF reaches $\pm \beta V_{ss}$

The exact formula in steady can be found by solving differential equations and finding that the rise time (or fall time, they are equivalent) is 
$$2\beta V_{ss} = (V_{ss} + \beta V_{ss})\left(1 - \exp\left(\frac{-t}{RC}\right) \right)$$
$$\frac{2\beta}{1 + \beta} = 1 - \exp\left(\frac{-t}{RC}\right)$$

$$\frac{1 - \beta}{1 + \beta} = \exp\left(\frac{-t}{RC}\right)$$
$$t = RC \ln \frac{1 - \beta}{1 + \beta}$$
Since it takes two cycles to go back to initial state
$$\tau = 2RC \ln \frac{1 - \beta}{1 + \beta}$$

## Monostable Multivibrator
![[Schmitt_Trigger_Monostable-Multivibrator.png]]

The circuit is very similar to the [[#Astable Multivibrator|Astable Multivibrator]] but it has two key modifications:
1. Input capacitor to pass trigger signal fr very short time
2. output diode to ensure output voltage is limited below $\beta V_{ss}$ 

The analysis as above yields down time as 
$$\tau = RC \ln \frac{1}{1 - \beta}$$ 
And recovery time as 
$$\tau' = RC \ln \frac{1 + \beta}{1}$$ 
### BJT Schmitt Trigger

![[Schmitt_Trigger_BJT.png]]

First, assume $V_{in} = 0$, transistor $Q_2$ is on and, for simplicity, assume that it is saturated, then $V_{out} = 0$ and $I_{2} = \frac{V_{CC}}{R_3}$, then $V_{R4} =\frac{V_{CC} R_4}{R_3}$ . To turn on $Q_1$ $V_{in}$ has  to be at least $0.7 + V_{R4}$, this makes rising threshold to be around $0.7 + \frac{V_{CC} R_4}{R_3}$.

Now when $Q_1$ is saturated, 

$$V_{\mathrm {HT} }={\frac {R_{\mathrm {E} }}{R_{\mathrm {E} }+R_{\mathrm {C2} }}}{V_{+}}$$
$$\displaystyle V_{\mathrm {LT} }={\frac {R_{\mathrm {E} }}{R_{\mathrm {E} }+R_{\mathrm {C1} }}}{V_{+}}$$

%%
## TODO
- Own schematics
- more explanation for multivibrators