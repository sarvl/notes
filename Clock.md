#electronics #digital #computer_architecture #fpga #electronics #clock

Clock is a particular synchronization signal in [[Digital_Electronics|Digital Electronics]], which guides when changes in state are committed.


![[Clock_Clock.png]]

## Clocking Methodology
Generally use a single clock, using more clocks leads to [[Clock#Clock_Domain_Crossing|Clock Domain Crossing]].
Determine max frequency by examining critical path.


## Clock Distribution


## Clock Domain Crossing
All real world circuits of interesting size use more than one clock domain due to:
- different speed of operations within circuit
- established communication protocols
- asynchronous inputs

The process of communicating across domains with difference clocks is called **Clock Domain Crossing**. Even if two clocks are nominally the same, CDC methods should be implemented because small frequency difference in clocks will lead to drift in phase. 

Proper crossing is necessary to have [[Reliability]] of a circuit.

### Source

[[Flip_Flop#Timing|Timing]] requirements of [[Flip_Flop|Flip Flops]] force the signal to be stable for certain periods, this stability cannot be guaranteed without synchronizing circuit to a particular clock - something which not always is possible. 
When timing requirements are violated, the value that Flip Flop senses may be during transition and outside valid input range, this leads to output also possibly being incorrect.
The above is called **Metastability** and it is theoretically unbounded state however, in practice it usually is reasonably short, because the probability of it occurring is exponentially decaying.

see also [[Flip_Flop#Metastability|Metastability]]

### Problems Appearing
- [[Flip_Flop#Metastability|Metastability]]
  May further lead to physical damage, high  power consumption, and functional issues.
- Data Loss
  Either metastability or not waiting long enough in fast -> slow domain transition, there usually is no cycle-cycle correspondence between different domains.
  This is solved by forcing source to wait long enough via [[Finite_State_Machine|FSM]], [[First_In_First_Out|FIFO]], or handshaking.
- Data Coherence
  Data corruption when crossing domains with separate synchronizations, generally solved by not doing that. Though it can be also solved with [[Gray_Code|Gray Code]].
- Re-Convergence
  Convergence is when two signals coming from one clock domain are separately synchronized in second clock domain and they start interacting
  Divergence is when signal splits in clock domain and goes through CDC separately
%%to be read%%

### Solutions

#### Multi Flop Synchronizer

At least two flip flops, one clocked in one CD, the rest clocked in the other CD.

It is impractical to increase number of [[Flip_Flop|Flip Flops]] indefinitely. The main concern is increased latency for CDC, but eventually [[Power]] limitations may become important. Larger number of elements leads to decreased [[Reliability]], so there is a spot that maximizes reliability.

![[CDC_MF-Synchronizer.png]]


##### Process
![[CDC_MF-Synchronizer-Waveform.png]]

##### Considerations
Only works for single bit data because different flip flops may behave slightly differently, leading to data incoherence.
Synchronization circuit should be as tight as physically possible, this reduces signal propagation time.  Similarly, avoid all [[Digital_Electronics#Asynchronous|Combinational Circuits]] as they as it can introduce glitches.
It does require than clock of synchronizer is fast enough to clock few instances of source pulse, this can be done by for example extending the length of the source pulse.
##### Handshaking
Open Loop design (above) does not have any way to indicate that data is now stable. This is fine as long as the proper frequency relationship is ensured. To be extra safe, especially with [[Dynamic_Frequency_Scaling|Dynamic Frequency Scaling]], handshaking is introduced.

![[CDC_MF-Handshaking.png]]

There are 2 ways for handshaking
1. 4 phase 
	 1. req is raised by sender
	 2. ack is raised by receiver
	 3. data is sent
	 4. req is lowered by sender
	 5. ack is lowered by receiver
2. 2 phase
    1. req is changed 
    2. ack is changed 
    3. communication occurs
in 2 phase handshake, acknowledgement is bringing it to the same state as request, regardless of what that state is. This reduces the number of states but also requires more wires in full duplex communication, because there is no way to know whether the bus will soon be used by the other party. Though the 2 phase protocol imposes tighter restriction on timing in async communication, in order to not miss a request.

#### Toggle Synchronizer

For sparse pulses.
![[CDC_MF-Toggle.png]]

No need to worry about frequency relationship.

### Reset Synchronizer
A special case of 2FF synchronizer is reset synchronizer.
![[CDC_Reset.png]]

#### Mux-Recirculation

![[CDC_Mux-Recirculation-2.png]]

![[CDC_Mux-Recirculation.png]]

Also called Multi-Cycle Path Strategy. A solution for multi bus systems where data changes rarely.

First, source signals request. This request enables reading of data and is also used to change value of acknowledgement, signaling done with reading.

When enable is high, data must be held constant.

#### Asynchronous FIFO
![[CDC_AFIFO.png]]


### Decision Tree

![[CDC_Decision-Tree.png]]

### Verification
Traditional simulation and timing analysis are not sufficient.

- Structural
  Check for long known and verified techniques used in synchronizers
- Functional
  Simulate worst case scenario
- Analog simulation

1. Check for the presence of valid synchronizers in all spots with clock domain crossing
2. Check reconvergence
3. Check for data loss (fast to slow and async transitions)
4. Functional
   - check handshake protocols
   - check FIFO synchronization
   - check mux recirculation

![[CDC_Verification.png]]



### Misc
for two identical clocks with the same frequency and same phase, there is no CDC.

for two clocks with same frequency but different phase, a delay of 1 clock cycle may be needed to ensure proper  acquirement.

for two clocks that have n integer ratio of frequency, slower clock should hold the data for n cycles, though this can be minimized by ensuring that data launch point (fast clock) to data receive point (slow clock) is long enough. To eliminate data loss, fast clock must either wait for n cycles or until slow clock transitions.

for two clocks that have p rational ratio of frequency, metastability may occur
- clock edges never getting too close together
  all fine
- clock edges sometimes get close together but only for one cycle
  This can be solved with simple standard CDC methods 
- clock edges get close together and stay like that for many cycles
  This can be solved with standard CDC methods, but they need to force even slow clock to wait long enough.

## Links
- https://thedatabus.in/cdc_complete_guide/
- https://thedatabus.in/metastab_mtbf
- https://thedatabus.in/cdc_interview_question/
- https://vlsiuniverse.blogspot.com/2016/09/reset-synchronizer.html
- https://groups.google.com/g/comp.lang.vhdl/c/P5aezDa5OeA
- https://www.eetimes.com/understanding-clock-domain-crossing-issues/
- https://thedatabus.in/reconvergence/

## Lectures
- CS61C - UCB 

#lecture_cs61c_ucb


%%

## TODO
- diagrams, make custom
- Wording
- VHDL code
- Real Examples
- reorganize
- for clock distribution extract stuff from High Performance Microprocessor Design Alpha, if nothing else is found