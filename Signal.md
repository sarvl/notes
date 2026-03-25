#signal #networking #telecom 

A signal is any time changing quantity conveying information. Most often used in the context of [[Electronics|Electronic]] signal as time changing [[Voltage]].

Converting signals from digital to analog domain uses [[Analog_Digital_Converter|Analog Digital Converter]] or [[Digital_Analog_Converter|Digital Analog Converter]], both are limited by [[Sampling|Sampling Theorem]]. [[Sampling]]


## Signal Transmission Model

```
  Source    -> Source Encoder -> Channel Encoder ->   Modulator 
                                                          |
                                                          V
                                              noise -> Channel
                                                          |
                                                          V
Destination <- Source encoder <- Channel Decoder <-  DeModulator 
                                               
```


## Key Concepts
- Data representation 
  Analog vs Digital
- Bandwidth
  Channel capacity
- Latency
  Delay between sender and receiver
- Throughput
  Observed data rate in [[Information_Theory|bits]] per second
- Reliability/Availability


## Parameters
- Frequency
  Meaningful only for signals which do repeat
  Number of complete cycles per unit time
  Symbol: $f$
  Measured in Hertz $[Hz = s^{-1}]$  
- Wavelength
  Distance between successive peaks of a sinusoidal wave
  Symbol: $\lambda$
  Measured in $[{m\over s}]$
  In vacuum, $f \cdot \lambda = c \approx 3E8$
- Decibel
  Logarithmic unit used to express ratios of power
  $[dB] = 10 \cdot \log_{10} \left(P_1 \over P_2 \right) = 20 \cdot \log_{10} \left(V_1 \over V_2 \right)$ 
  $[dBmW] = 10 \cdot \log_{10} \left(P_1 \over 1mW \right)$ 
  $[dBW] = 10 \cdot \log_{10} \left(P_1 \over 1W \right)$ 
- Bandwidth
  A distance between upper and lower frequency limits of a channel
  between the points where signal is attenuated by $3dB$ form its maximum.
- Symbol
  A distinct thing that is being sent, contains certain number of [[Information_Theory|Bits]]
- Bit Rate
  Number of bits transmitted per second
- Symbol Rate
  Number of symbols transmitted per second
  $\text{bit rate} = \text{symbol rate} \cdot \log_2 (\text{symbol count})$
- Signal to Noise Ratio SNR
  Ratio of power of the signal to the power of  the noise in a medium
- Bit Error Rate BER
  Number of errorenous bits received divided by the total number of bits received

## Encoding
Encoding is a way to transform information from one form to another. 

- [[Cryptography]]
- [[Compression]]
- [[Error_Detection_And_Correction|Error Detection and Correction]]


## TODO
- images
- Ordering