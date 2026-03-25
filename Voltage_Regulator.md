#analog #electronics  

A voltage regulator is a unit that converts variable input [[Voltage]] (within some range) to stable output voltage.


## Parameters
- Line Regulation
  How good a regulator is at maintaining constant voltage despite changing input?
  $LR = \frac{\Delta V_o}{\Delta V_i}$
  sometimes also  $LR = \frac{\Delta V_o}{V_o \cdot \Delta V_i}$
- Load Regulation
  How good a regulator is at maintaining constant voltage despite changing load?
  $LR = \frac{V_{no load} - V_{full load}}{V_{load}}$
  

## Shunt Regulators
![[Voltage_Regulator_Shunt.png]]

Controls its current flow.


### Zener Diode
An ideal [[Semiconductor_Diode|Zener Diode]] with a specific voltage drop over it, when placed on as a Shunt Regulator, will pass any current with set voltage. A realistic diode makes the voltage dependent on current passing through diode.

![[Voltage_Regulator_Zener_Diode.png]]


Its advantage is cheapness, but it uses a lot of power passing through series resistance and it is limited by how much current can pass through diode.

## Series Regulators
![[Voltage_Regulator_Series.png]]

Controls its voltage drop.


### Basic Regulator
![[Voltage_Regulator_Basic_Series.png]]

[[Semiconductor_Diode|Zener Diode]] sets reference voltage, as [[BJT|BJTs]] have around $0.7$ voltage drop at base-emitter junction, the output voltage is $V_{dz} - 0.7$. In reality, this setup does depend on load current.

![[Voltage_Regulator_Basic-Series-Regulator-Example.png]]

### Negative Feedback
![[Voltage_Regulator_Series-Negative-Feedback.png]]

![[Voltage_Regulator_Series-Negative-Feedback-Opamp.png]]

By using [[Feedback#Negative|Negative Feedback]] it is possible to reduce variations in output voltage.

![[Voltage_Regulator_Over-Current-Protection.png]]
## Videos
-  [Voltage Regulators by Aaron Danner](https://www.youtube.com/playlist?list=PLXb3r5ny8_1VGu4f8FoKp4ZkdEyd8CF1a)

## TODO
- unify images
- examples


