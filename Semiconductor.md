#material #physics #semiconductor 

Semiconductor material is material which [[Resistance#Resistivity|Resistivity]] is between [[Insulator]] and [[Conductor]] - between about $10^{-6}$ to $10^6$. This resistivity is heavily dependent on [[Temperature]], [[Light]], or Dopants. Simple semiconductor materials are composed out of [[Element|Elements]] found in 4th group of [[Periodic_Table|Periodic Table]] (eg [[Silicon]] while Complex ones are formed from 3rd and 5th group (eg [[Gallium]]-[[Arsenic]]).


## Theory of Operation
For simplicity, this section uses Silicon atom.   
As [[Atom|Atoms]] form larger structures, [[Electron|Electrons]], which have to occupy distinct energy levels (see [[Pauli_Exclusion_Principle|Pauli Exclusion Principle]]), create [[Energy_Band|Energy Bands]]. In semiconductors these gaps are separated by at most $3eV$ ($1.1eV$ for silicon), but they are separated. This relatively small gap means that due to random variations, electrons can jump to almost empty band with higher energy, which leads to creation of electron-whole pair which are now free too move and so to conduct electricity. At higher energies these jumps are more likely to happen and so resistivity decreases, similarly at lower energies these jumps are less likely to occur.  
This is different than behavior of [[Conductor]], where resistivity *increases* with temperature, importantly the same process takes place in semiconductors but it is much smaller than band gap jumps.  
As electrons are [[Fermion|Fermions]] the exact probability is given by [[Fermi-Dirac_Statistics|Fermi-Dirac Statistics]] 

Due to the generation process, it is always the case that $n_i = n = p$ where $n$ is number of negatively charged carriers (electrons), $p$ is number of positively charged carriers (holes), and $n_i$ is total number of charge carriers. In general this leads to law of mass $n_i = \sqrt{np}$, valid not only for intrinsic semiconductors. (why?)  
During recombination process, energy is lost by electrons and so energy is emitted as light - creating [[Semiconductor_Diode#Light_Emission|Light Emitting Diode]], the same process dissipates heat.

## Doping
Doping is a process of introducing impurities to semiconductor to change its behavior. There are 2 types of doped semiconductor: N-type where electrons are majority carriers ($n \approx N_D = \text{Number of donor atoms}$) and P-type where holes are majority carries ($p \approx N_P = \text{Number of acceptor atoms}$).  
The impurities with more electrons bond with silicon atoms and leave 1 electron unmatched, this electron is then free to move, similarly impurities with less electrons leave 1 hole unmatched which is then free to move.  
For donor semiconductors: $n \approx N_D$, for acceptor semiconductors: $p \approx N_A$, from that it is now possible to find $p$ carriers, knowing $n_i$ for intrinsic semiconductor (which remains unchanged).  
This affects resistivity-temperature curve such that resistivity becomes stable at room temperature semiconductor.   
Note that despite introducing more positive/negative charge carriers, doping process does not affect total charge of the material as all electrons are balanced out by protons and all holes are balanced by lack of protons.

## Drift Current
When voltage is applied to semiconductor, electric field is created inside, and the free charge carriers *drift* in the direction of current.  (Equation ED3p13) $\sigma = e(n \mu_n + p\mu_p)$. 

## Diffusion of Carriers
When there is imbalance in semiconductor material and carrier concentration becomes heterogeneous. Carriers move from area of high concentraation to low concentration. (ED3p13-14) 

## PN-Junction
A PN junction is created when P doped region and N doped regions are connected together, in the connecting region electrons from N region fill holes in P region, this leads to excess positive charge on N side and excess negative charge on P side. Excess charge creates electric field from N to P and blocks further recombination from happening, this takes place when the voltage created is about $0.7V$.   
Drift currents are always present and are very small, thus they are not much affected by external voltage applied. In equilibrium drift and diffusion currents balance out and no current is flowing.  
When the junction is in reverse polarization - positive voltage applied from N to P - then depletion region is extended and only small drift currents flow.  
When the junction is in forward polarization - positive voltage applied  from P to N - depletion region shrinks and diffusion currents grow exponentially.  

All of the above gives rise to equation $I = I_{drift} \left( \exp\left(V/\phi_T\right) - 1\right)$, $-1$ is often negligible and thus ignored.

## PN-Junction Creation

### Breakdown
#### Zener

#### Avalanche

## TODO
- verify
- drawings
- write about mechanism of decreasing conductance in conductors
- incorporate curiosities from ED3
- incorporate more statistics
- doping details
- ensure theory of operation is correct
- not 100% certain about what is drift current, will have to reread, it may be independent of external voltage but it may depend on internal 0.7V which makes it appear independent
- more detailed equation derivation once I better understand semiconductor physics, something with maxwell boltzmann statistics
- energy band models ED4p10
- even more about how to actually create a junction, read a book about semiconductor process,  slides suck for this