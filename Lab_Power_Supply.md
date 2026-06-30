#electronics 

Lab power supply is a [[Power_Supply|Power Supply]] designed for lab, it can produce constant [[Charge|Current]] and [[Voltage]], and it has protection against short circuit.

This document describes design process.

## Specification
- Voltage Range
- Current Range
- Type of control 
- Noise toleration (probably should be low)
- Single Supply Input 


## Design

![[Lab_Power_Supply_LM317.png]]

Initial attempt with LM317 works well but does not satisfy the requirement of 0V output.
If we were to set reference voltage externally, we are forced to set minimum load.

Solving this limitation can be started by seeing how LM317 operates underneath.
![[Lab_Power_Supply_Underneath.png]]

![[Lab_Power_Supply_Attempt2.png]]

Integrating LM317 without internal reference circuitry solves the problem of offset, but is not very stable.

![[Lab_Power_Supply_Constant-Current.png]]

One [[Opamp]] can be eliminated.

![[Lab_Power_Supply_Attempt3.png]]

The above can be somewhat replaced with LT3080.

![[Lab_Power_Supply_Attempt4.png]]


Again, this works, but is a bit wasteful in number of components.

![[Lab_Power_Supply_Attempt5.png]]

Look into datasheet of LT3080 can reveal design for variable voltage output supply.

It is very important to realize that ambient temperature in datasheet corresponds to *junction* temperature.

![[Lab_Power_Supply_Final-Schematic.png]]
## Testing

AC coupling to test noise.

## PWM
Good quality knobs are generally expensive, however rotary encoders and microcontrollers are very cheap. By doing [[Pulse_Width_Modulation|Pulse Width Modulation]] and then filtering it through [[Analog_Signal_Processing#Low Pass Filter|Low Pass Filter]], analog signal is generated.
However, the power to the controller has to be very stable, otherwise high/low levels change and the PWM quality decreases.


## Shunt Resistor

It is difficult to get high precision high power dissipation resistor, instead, 10 resistors can be put in parallel.

## Component Consolidation

Wide range of components increases cost of the project because components get cheaper in larger quantities and the manufacture price depends on how many components there are (due to PCB fabrication steps). 
Therefore wherever possible, components should be consolidated into ones already used. For example instead of $5k$ resistor, use $2 \times 10k$ resistor in parallel.

## Reverse Protection

When powering external circuit with a battery, and disconnecting input power, the regulator might blow up because of backfeeding voltage. To solve this, simply add a diode.
![[Lab_Power_Supply_Reverse-Protection.png]]

## Pin Extension
In case of limited pins on microcontroller, IO extenders are available, but as they use some serial interface, they can only be used for noncritical and slow pins.

## PCB
Start with an outline which comes from the case.  Ensure your grid matches your components - metric or imperial system.  Start with fixed components that cannot be moved - connectors. Group together functional blocks. Separate analog and digital parts.  Usually, signals first, then buses, then power. Sometimes you have to remove the feature to make routing possible.
## Videos
- [EEVblog 221 - Lab Power Supply Design p1](https://www.youtube.com/watch?v=CIGjActDeoM)
- [EEVblog 222 - Lab Power Supply Design p2](https://www.youtube.com/watch?v=6Otr1I0OR18)
- [EEVblog 224 - Lab Power Supply Design p3](https://www.youtube.com/watch?v=8-qar5vgnbc)
- [EEVblog 225 - Lab Power Supply Design p4](https://www.youtube.com/watch?v=YaRDbw38x7Q)
- [EEVblog 232 - Lab Power Supply Design p5](https://www.youtube.com/watch?v=Lg6oYFerUlA)
- [EEVblog 233 - Lab Power Supply Design p6](https://www.youtube.com/watch?v=jGF5p8GjzFM)
- [EEVblog 238 - Lab Power Supply Design p7](https://www.youtube.com/watch?v=s8b4h_UybLE)
- [EEVblog 240 - Lab Power Supply Design p8](https://www.youtube.com/watch?v=UUsMMioipDE)
- [EEVblog 244 - How to Lay Out a PCB - PSU Design Part 9](https://www.youtube.com/watch?v=2b1UdOmxVrw)   
- [EEVblog 245 - PSU Design Part 10 - PCB Layout Editing](https://www.youtube.com/watch?v=9pFal1lgFl0)
- [EEVblog 258 - PSU Housing Design Part 11](https://www.youtube.com/watch?v=xa9Lyb45oJM)
- [EEVblog 259 - PSU Rev C Schematic Part 12](https://www.youtube.com/watch?v=XroH4X78qTY)
- [EEVblog 260 - Tracking Pre-Regulator Simulation in LTspice - PSU part 13](https://www.youtube.com/watch?v=iTxKCQYMHbY)

#video_eevblog 


%%

## TODO
- actually design it