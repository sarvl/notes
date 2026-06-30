#physics #electromagnetism #electricity #magnetism 

Electromagnetism is a branch of [[Physics]] describing interactions of magnetic and electric [[field|fields]] and charges via the Maxwell's Equations and Lorentz's Force Law.

## Lorentz's Force Law
$$\vec{F} = q(\vec{E} + \vec{v} \times  \vec{B}) $$

The [[Force]] acting on a particle is equal to charge multiplied by [[Electric_Field|Electric Field]] 
## Maxwell's Equations

### Integral Form
|           Name            |                                                                                                                       Equation                                                                                                                       |
| :-----------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|        Gauss's Law        |                                                     $$\underset{\text{closed surface}}{\iint} \vec{E} \cdot d\vec{A} = \frac{1}{\epsilon_0} \underset{\text{enclosed volume}}{\iiint}{\rho}dV$$                                                      |
| Gauss's Law for Magnetism |                                                                                        $$\underset{\text{closed surface}}{\iint} \vec{B} \cdot d\vec{A} = 0$$                                                                                        |
|       Faraday's Law       |                                             $$\underset{\text{closed loop}}{\int} \vec{E}\cdot d\vec{L} = -\frac{\partial}{\partial t} \underset{\text{enclosed surface}}{\iint} \vec{B}\cdot d\vec{A}$$                                             |
|   Ampere-Maxwell's Law    | $$\underset{\text{closed loop}}{\int} \vec{B}\cdot d\vec{L} = \mu_0 \underset{\text{enclosed surface}}{\iint} \vec{J}\cdot d\vec{A} + \mu_0 \epsilon_0 \frac{\partial}{\partial t} \underset{\text{enclosed surface}}{\iint} \vec{E}\cdot d\vec{A}$$ |

### Differential Form
|          Name           |                                               Equation                                                |
| :---------------------: | :---------------------------------------------------------------------------------------------------: |
|       Gauss's Law       |                        $$\vec{\nabla}\cdot\vec{E} = \frac{\rho}{\epsilon_0}$$                         |
| Gauss Law For Magnetism |                                   $$\vec{\nabla}\cdot\vec{B} = 0$$                                    |
|      Faraday's Law      |                $$\vec{\nabla}\times \vec{E} = - \frac{\partial}{\partial t} \vec{B}$$                 |
|  Ampere Maxwell's Law   | $$\vec{\nabla} \times \vec{B} = \mu_0 \vec{J} + \mu_0 \epsilon_0 \frac{\partial}{\partial t}\vec{E}$$ |

### Description

In each equation:
- $\vec{E}$ stands for Electric Field
- $\vec{B}$ stands for Magnetic Field
- $\vec{A}$ is 
- $\vec{L}$ is
- $\rho$ is charge density
- $\epsilon_0$ is Vacuum Permittivity
- $\mu_0$ is Magnetic Permeability
- $\vec{J}$ is [[Charge|Current]] density

## Charge

Charge is a unit of 

## Wave
A special case arises when there is no charge, Maxwell's equation in differential form are then

|          Name           |                                       Equation                                        |
| :---------------------: | :-----------------------------------------------------------------------------------: |
|       Gauss's Law       |                           $$\vec{\nabla}\cdot\vec{E} = 0$$                            |
| Gauss Law For Magnetism |                           $$\vec{\nabla}\cdot\vec{B} = 0$$                            |
|      Faraday's Law      |        $$\vec{\nabla}\times \vec{E} = - \frac{\partial}{\partial t} \vec{B}$$         |
|  Ampere Maxwell's Law   | $$\vec{\nabla} \times \vec{B} = \mu_0 \epsilon_0 \frac{\partial}{\partial t}\vec{E}$$ |

The first 2 happen to be irrelevant but the last 2 can be manipulated to obtain [[Wave]] equation. (see Derivation below)

$$\nabla^2 \vec{E} = \frac{1}{\epsilon_0 \mu_0} \frac{\partial}{\partial t} \vec{E} $$
$$\nabla^2 \vec{B} = \frac{1}{\epsilon_0 \mu_0} \frac{\partial}{\partial t} \vec{B} $$
From this it follows that electromagnetic waves  propagate at the speed of light $c = \frac{1}{\sqrt{\epsilon_0 \mu_0}}$

### Derivation

## Applications
- [[Electrical_Circuit|Electrical Circuits]]

## TODO
- fill sections
- add more applications
- add some basic questions/exercises