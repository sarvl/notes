#electronics #analog

Opamp is fundamentally [[Amplifier#Differential|Differential Amplifier]] with very large internal gain, for this reason they are not by themselves used as such.
## Intuitive analysis
Opamp has essentially no input current, and it tries to keep the inputs the same voltage in [[Feedback#Negative|Negative Feedback]] configuration.

## Configurations
- non inverting amplifier
  ![[Opamp_noninverting.png]]
- inverting amplifier
  ![[Opamp_inverting.png]]
- differential amplifier
  ![[opamp_differential.png]]
- Integrator
  ![[Opamp_Integrator.png]]
## Limitations
Real opamps usually are not rail-to-rail, meaning that their range is smaller than its power supplies. This can be solved with bias.
![[opamp_bias-offset.png]]


## Chopper
A particular variant of opamp with very low offset voltage.

![[Opper_Chopper.png]]

During phase 1 (pictured), $B$ opamp measures its own offset voltage and stores it onto capacitor $C_1$ which is then fed back and offsets that opamp. 
During phase 2 (switches in alternate state), $B$ opamp measures offset voltage of $A$ and stores its value onto $C_2$ (its own offset has been removed in previous stage). 

## Noise
The noise is typically specified in $nV/\sqrt{Hz}$. 

At low frequencies, $1/n$ noise dominates, at high frequencies white noise dominates.

## Videos
- [EEVblog 24 - Chopper Operational Amplifiers](https://www.youtube.com/watch?v=oibJUt6QkwI)
- [EEVblog 528 - Opamp Input Noise Voltage Tutotorial](https://www.youtube.com/watch?v=Y0jkPLuFdnM)
- [EEVblog 600 - OpAmps Tutorial - What is an operational amplifier](https://www.youtube.com/watch?v=7FYHt5XviKc)

%% 
## TODO
- verify opamp, the description seems odds