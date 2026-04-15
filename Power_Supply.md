#electronics #power #analog 


A power supply is a unit providing [[Power]] to the [[Electrical_Circuit|Circuit]]. Most often it converts [[AC]] to [[DC]] - [[ACDC_Converter]]. 
Power supplies by themselves are very variable to their load and supply, which is why we use [[Voltage_Regulator|Voltage Regulators]].


## Removing Ripple
- [[Analog_Signal_Processing|RC LPF]]
  Very simple, requires proper RC value matching, works well for small current value
- Capacitor Multiplier


## Linear
![[Power_Supply_Linear.png]]

![[Power_Supply_Linear2.png]]

The regulator works as [[Feedback#Negative|Negative Feedback Loop]]. 
## Switch Mode
![[Power_Supply_Switch-Mode.png]]
![[Power_Supply_Switch-Mode2.png]]

The regulator works as [[Feedback#Negative|Negative Feedback Loop]],  
## Videos
- [EEVblog 90 - Linear and LDO regulators and Switch Mode Power Supply Tutorial](https://www.youtube.com/watch?v=cM7t1Mpu7s4)

%%
## TODO
- figure out a reasonable way to distribute power_supply / dcdc / acdc / acac / voltage_regulators
- explain better
- check buck/boost/buck-boost