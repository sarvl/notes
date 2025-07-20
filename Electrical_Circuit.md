#electronics #circuit 

Electrical Circuit is a collection of components, usually obeying Lumped Matter Discipline, performing a given mathematical function. They are used to design and analyze virtually everything working on electricity.

## Components
Most basic components are
- [[Wire]]
- [[Resistor]]
- [[Capacitor]]
- [[Inductor]]
- Power source - [[Voltage_Source|Voltage]] or [[Current_Source|Current]]

Very often more components are used
- [[Transistor]]
- [[Diode]]
- [[Transformer]]
- [[Transmission_Line|Transmission Line]]

Circuits themselves can be grouped to form subcircuit, this is how [[Integrated_Circuit|Integrated Circuits]] are generally used.

## Circuit Analysis
The purpose of analysis is to find how the circuit will behave and evolve over time. There are methods that apply always and methods that apply only to [[Linearity|Linear]] circuits.

### KCL and KVL
The most basic method, is to write all [[Kirchhoffs_Current_Law|Kirchhoff's Current Law]] and [[Kirchhoffs_Voltage_Law|Kirchhoff's Voltage Law]] equations,  then simply solve the resulting [[System_Of_Linear_Equations|System of Linear Equations]]. This method works as long as 

#### Example

### Mesh Analysis
Based on KVL and KCL, the analysis is
1. Identify all loops in a circuit, the [[Voltage]] across each component in each loop must sum up to 0, otherwise there would not be a single voltage at a given point.
2. In each loop, the current is constant
3. Rewrite equations from `1.` substituting each voltage with corresponding equation based on `2.`

The conditions for this method are the same as for regular KCL and KVL, but it drastically simplifies the solution.

#### Example

### Node Analysis
Based on KVL and KCL, the analysis is
1. Identify all nodes in a circuit, [[Current]] incoming and outgoing must sum up to 0, otherwise the charge would not be conserved
2. On each branch, replace current with [[Voltage]] over [[Impedance]]
3. Rewrite the equations from `1.` with `2.`

The conditions for this method are the same as for regular KCL and KVL, but it drastically simplifies the solution.


### Component Transformation
- [[Resistor|Resistors]] in series -> sum of the resistances $R$
- [[Resistor|Resistors]] in parallel -> sum of the conductances $G = \frac{1}{R}$
- [[Capacitor|Capacitors]] in series -> sum of inverses $\frac{1}{C}$
- [[Capacitor|Capacitors]] in parallel -> sum of capacitances $C$
- [[Inductor|Inductors]] in series -> sum of inductances $L$
- [[Inductor|Inductors]] in parallel -> sum of inverses $\frac{1}{L}$
- [[Impedance]] in series -> sum of impedances $Z$
- [[Impedance]] in parallel -> sum of admittances $Y = \frac{1}{Z}$

Derivations can be found in corresponding articles.
The conditions for this method are the same as for regular KCL and KVL, it is generally the preferred method wherever applicable.

#### Example

### Thevenin's Equivalent Circuit
More of a consequence of previous methods rather than a method by itself, applies only to linear circuits. Each network composed only out of [[Impedance]], [[Voltage_Source|Voltage Sources]], and [[Current_Source|Current Sources]] can be equivalently represented with a network composed out of single [[Impedance]] and [[Voltage_Source|Voltage  Source]] in series.

#### Example

### Norton's Equivalent Circuit
More of a consequence of previous methods rather than a method by itself, applies only to linear circuits. Each network composed only out of [[Impedance]], [[Voltage_Source|Voltage Sources]], and [[Current_Source|Current Sources]] can be equivalently represented with a network composed out of single [[Impedance]] and [[Current_Source|Current  Source]] in series.

#### Example


### Insolvable Circuits
Some circuits make no sense and cannot be achieved, usually appear due to abstractions employed by circuit analysis. 

#### Current Source in Series

#### Voltage Source in Parallel


### Choosing the Method to Solve a Circuit


## TODO
- exercises in circuit analysis
- examples of analysis
- examples of modeling
- questions to ponder
- check CT slides
- conditions for each circuit analysis method
- fill insolvable circuits