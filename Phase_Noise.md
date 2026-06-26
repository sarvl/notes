#electronics 

In [[Oscillator|Oscillators]], phase noise is how phase shift deviates from zero. Ideal output of sinusoidal signal is single narrow spectral line, change of phase is equivalent to change of frequency (somewhat adjusted), this causes spectrum to have side bands.
![[Phase_Noise_Sidebands.png]]

These side bands might cause problems with [[Mixer|Mixers]] and frequency shifting.

![[Phase_Noise_Spectral-Regrowth.png]]

Such spectral regrowth might be massive problem when large unwanted signal is to be filtered out, such side bands spread energy from unwanted signal into IF filter.

## Measurement
Dedicated tools are available, but spectrum analyzers do the job.

It is generally measured with respect to carrier power over 1 Hz window.

Often, [[Autocorrelation_Function|Auto correlation Function]] is used to reduce noise introduced by the measurement. At least two separate references are used.
![[Phase_Noise_Autocorrelation.png]]

## Videos
- [https://www.youtube.com/watch?v=hfgaEjf1154](https://www.youtube.com/watch?v=hfgaEjf1154)
- [https://www.youtube.com/watch?v=P5gxNGckjLc](https://www.youtube.com/watch?v=P5gxNGckjLc)
- [https://www.youtube.com/watch?v=pL0pY-t8KWY](https://www.youtube.com/watch?v=pL0pY-t8KWY)