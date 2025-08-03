#electronics 

Voltage Source is an abstraction of a device producing constant [[Voltage]], regardless of [[Current]] drawn. It provides [[Power]] to [[Electrical_Circuit|Electrical Circuits]].
Real voltage sources can be modeled by adding [[Resistor]] in series - this produces larger voltage drop the larger current is drawn, effectively limiting maximum current - and thus Power.


## Symbols

## Illegal Configuration
Two ideal voltage sources, sharing [[Ground]], connected with $0\Omega$ [[Wire]] does not mean anything in regular circuit abstraction (excluding the case of perfect match). With real voltage sources (resistor in series), some current flows from one VS to the other and nothing else happens.
In reality, the behavior depends on what these sources represent, eg [[Battery]] may be charged or one of the sources may explode.


## Maximum Power 

The power delivered by real VS to the resistor circuit is limited and equal to $P = V_LI = V_L^2/R_L$ where $V_L$ is voltage across the load and $R_L$ is load resistance.
The circuit is [[Voltage_Divider|Voltage Divider]], so $V_L = \frac{R_L}{R_{internal} + R_L} V$
From that $P = V^2 \frac{R_L}{\left(R_{internal} + R_L\right)^2}$
As $R_L \to \infty$ $P \to 0$, similarly as $R_L \to 0$ $P \to 0$ therefore there is some maximum in the middle, using [[Mathematical_Optimization|Mathematical Optimization]] we find that to be $R_L = R_{internal}$. 
And so maximum power delivered is $P = V_{open}^2/R_{internal}$. 

In general, maximum power is unlimited due to storing of energy in [[Capacitor|Capacitors]] and [[Inductor|Inductors]], nonetheless, maximum [[Energy]] delivered can never exceed $\int P dt = \int V_{open}^2/R_{internal} dt$
Note that it is possible to alter maximum momentary power with use of [[Resonance]] but total [[Energy]] must stay within $\int P = V_{open}^2/R_{internal} dt$

## TODO
symbols
illegal configurations, verify
schematics