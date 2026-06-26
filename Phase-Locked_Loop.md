#electronics #analog 

PLLs are used where controlled and precise frequency is needed.

By taking two points from the sine waves and measuring difference of their values, difference of phase can be obtained, even if their actual frequencies are different. If this difference stays constant, then the sine waves have the same frequency (taking into account [[Sampling]] limitations).

PLLs are composed out of 
- [[Phase_Detector|Phase Detector]] - produces voltage proportional to phase difference
- [[Voltage_Controlled_Oscillator|Voltage Controlled Oscillator]] - to produce different frequencies, increase in voltage must increase increase in frequency
- [[Analog_Signal_Processing|Loop Filter]] - attenuates reference signal on output and determines the loop stability

This by itself is not very useful, but combined with frequency multiplier/dividers it can be used to produce wide range of precise frequencies.

![[PLL_Schematic.png]]


One problem is when the frequency is so different than the VCO output falls outside loop filter, there is no phase detector input which might make it impossible for the loop to be locked. This is generally solved by making sure the oscillator is close to reference frequency.

The reference frequency can be created with

Locked state is when phase error is small and small perturbations of the phases and filters lead to the same state.

Hold in range is largest range where locked range exists.

Pull in range is largest range where PLL achieves lock  for arbitrary initial phase, frequency, and filter state.

Lock in range is largest range where PLL achieves lock immediately after abrupt change.

## Links
- https://www.electronics-notes.com/articles/radio/pll-phase-locked-loop/tutorial-primer-basics.php
## Videos
- [https://www.youtube.com/watch?v=A9qt0JYdvFU](https://www.youtube.com/watch?v=A9qt0JYdvFU)