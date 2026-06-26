#analog #electronics 

Buck Converter is a type of [[DCDC_Converter|DC-DC Converter]] that creates higer output current at the cost of output voltage.


![[Buck_Converter_Schematic.png]]
## Operation
It can be thought of as [[Square_Wave_Generator|Square Wave Generator]] connected to [[Analog_Signal_Processing#Low Pass Filter|Low Pass LC Filter]].

We assume that the current changes are linear, which is good enough approximation if we are in continuous conduction mode with small variations. We also assume that we operate in steady state.

Derivations lack that duty cycle $D = \frac{V_o}{V_i}$

In one part of the cycle, when the switch is on, across inductor there is a $\Delta V$ of $V_i - V_o$. From $V = L \frac{dI}{dt}$, and assuming the current does not change much we get $V_i - V_o = L  \frac{\Delta I}{\Delta t}$, equivalent to $L = \frac{V_i - V_o}{\Delta I \cdot \Delta t}$. Now with magic $L = \frac{V_o \left(1 - D\right)}{\Delta I \cdot f_{sw}}$

Maximum peak current is about average current and a half of ripple current.

Output capacitance can be found from (this is general formula) $I = C \frac{dV}{dt}$ or $\Delta V = \frac{1}{C} \int I dt$ again with shenanigans we get $C = \frac{\Delta I}{8 \cdot \Delta V \cdot f_sw}$
## Links
- https://passive-components.eu/buck-converter-design-and-calculation/

%%
## TODO
- Describe Operation
- take real world considerations from the link
- derivations are not fully accurate, they work enough to remember the correct formula though