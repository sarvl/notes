#networking 

A network is a general term for a set of connected things that communicate. Important consideration is [[Traffic_Engineering|Traffic Engineering]].

This includes
- [[Computer_Network|Computer Network]], in the context of Telecommunication and the Internet
- [[Chip_Network|On Chip Network]], in the context of [[Computer_Architecture|Computer Architecture]]
- [[Board_Network|On Board Network]], in the context of [[Computer_Architecture|Computer Architecture]]

A particularly interesting example is [[Clock_Distribution|Clock Distribution Network]]. Where the signal must arrive uniformly to all components, its Interconnect must be specifically designed for that.

This note contains general information regarding design of various structures.

## Terminology
Note that within a particular stack (like TCP/IP), some terms may be given different meaning


- **Network Interface** - connects endpoints to a network, decouples computation from communication
- **Link** - thing that carries the signal
- **Switch/Router** - connects fixed number of input channels to fixed number of output channels, they might perform some sort of operation on data, for example fetch&add
- **Channel** - single logical connection between routers/switches
- **Node** - Router/Switch/Endpoint within network
- **Message** - unit of transfer for clients
- **Packet** - unit of transfer for network
- **Flit** - unit of flow control within network
- **Direct Network** - When endpoints are inside network (that is, they also act as switches/routers)

## Design Considerations
- Capacity planning
- Quality of Service: Traffic prioritization
- Reliability and redundancy: fail over, replication
- Security:  [[Cryptography|Encryption]], authentication, secure management
- Scalability: Addressing, routing, distributed systems, how easy it is to add more nodes
- Resource Sharing
- Cost Efficiency

## Transmission
*Duplexing* is the ability to talk and listen simultaneously. 

- Simplex
  Only in one direction 
- Half-duplex
  In two directions, but only one at a time
- Full-duplex
  In two directions, simultaneously

*Frequency Division Duplexing* (FDD) is using separate channels for duplexing.
*Time Division Duplexing* (TDD) is using separate time frames for duplexing.


- Serial
  sending bits one by one
  long distance
- Parallel
  send group of bits 
  short distance

- Baseband
  Digital pulses directly on medium
- Broadband
  Signals modulate the carrier


- Synchronous
  Bits in data stream transferred in sync with a clock
- Asynchronous
  Bits in stream transferred at random intervals
  Start and end bit
- Isosynchronous
  Async blocks but within blocks certain bandwidth required

## Structures
- Point-to-Point
  Each connection has separate link
  Devices can receive/transmit simultaneously
- Multi-point (Multi-Access, Broadcast)
  Multiple nodes share a transmission medium
  Devices can receive but not transmit simultaneously 
- Polling
  Master station polls devices and determines who transmits/receives
- Selection
  When master receives data, it informs destination stations that there is data for them

## Components
- Hosts (End devices)
- Transmission Medium (Links)
- Network Devices (Devices conducting the communication)
- Protocols (Form of communication)

## Topologies
Specifies the way devices are wired together

### Properties
- Regular/Irregular
  Regular when a regular graph
- Routing Distance
  Number of links/hops along a route
- Diameter
  Maximum routing distance
- Average Distance
- Bisection Bandwidth
  Bandwidth measured by cutting network in half and measuring the bandwidth of cut links
- Blocking
  If connecting any permutation and destinations and sources, the network is non blocking

### Types
Multistage networks has more restrictions on concurrent pairs than mesh or crossbar, but they are way more scalable.

- Bus
  All nodes connected to single cable
  ![[Network_Bus.png]]
  
  
  +simple
  +cost effective
  +easy to implement coherence
  -not scalable due to electrical loading
  -high contention, very fast saturation
  -difficult to arbitrate
- Point to Point
  All nodes connected to each other
  
  +lowest  contention
  +lowest latency
  +ideal if no cost issues
  -very costly
  -not scalable
  -hard to lay out
  
  ![[Network_Point-To-Point.png]]
- Crossbar
  Every node connected to every other with shared link for destination
  
  Can, but does not need to, have a buffers, but buffer do improve overall throughput
  
  +concurrent transfer to non conflicting destinations
  +low latency
  +high throughput
  -no scalable
  -expensive
  -difficult to arbitrate
  
  ![[Network_Crossbar.png]]
- Ring
  Each node connected to two neighbors, can be uni or bidirectional
  
  +cheap
  -high latency
  -hard to scale
  
  ![[Network_Ring.png]]
- Hierarchical Ring
  Connect rings with rings
  
  +more scalable
  +lower latency
  -more complex
  
  ![[Network_Hierarchical-Rings.png]]
- Tree
  Hierarchical structure
  
  +good  for local traffic
  +planar
  +cheap
  -root can become a bottleneck
  
  ![[Network_Tree.png]]
- Omega
  multistage indirect
  multistage allows it to improve total throughput while still having somewhat reasonable number of connections
  
  ![[Network_Omega.png]]
- Hypercube
  N dimensional cube
  
  +low latency
  -hard to layout
  
  ![[Network_Hypercube.png]]
- Mesh
  Nodes interconnected
  
  +path diversity
  +easy layout
  ![[Network_Mesh.png]]
- Torus
  Square mesh with ends connected
  
  +higher path diversity
  -higher cost
  -unequal link size
  
  ![[Network_Torus.png]]
- Star
- Butterfly
  
  ![[Network_Butterfly.png]]
- Benes
- Banyan
- Delta
  
  ![[Network_Delta.png]]
  

## Routing
Specifies how message gets from source to destination. It is somewhat independent to topology, but certain topologies benefit more from certain routing algorithms.

Circuit Switching sets up full path before transmission, it is fast and has no buffering but setting it up takes time and noone else can use this path. Packet switching routes per packet in each routing and it is more flexible, any free link can be used, even if full path is occupied, and has no setup/bring down time, but it needs buffering and requires dynamic switches.


### Mechanisms
- Arithmetic
  Calculate cost of each route
- Source based
  Port specified for each route
- Table Lookup


### Algorithms
- Deterministic
  Always the same path
- Oblivious
  Path changes but not based on network state
- Adaptive
  Path changes based on network state



- Dimension-Order routing
  Traverse each dimension in order 
  
  simple
  deadlock freedom
  not good for throughput 
  not good at exploiting various paths
- Valiant's Algorithm
  Randomly choose __intermediate__ node, route from start to it and from it to end

### Deadlock Prevention
Routing must prevent all deadlocks. 

![[Network_Deadlock.png]]


- Pick algorithm that avoids routing, e.g. by restricting the turns
- Add more buffers
- Detect and break 
- Reserve space before sending


## Buffering and Flow Control
specifies what is stored in each router and in each link, and how what to do in case of oversubscription


### Packet Format
Each packet has: 
- Header with routing information
- Payload with actual data
- Footer with usually [[Error_Detection_And_Correction|Error Codes]]

### Handling Contention
- buffer
- drop
- misroute one

### Methods
- Circuit Switching
  Preallocate the path
  
  No buffering
  No contention
  Arbitrary message size
  Low link utilization
  Handshake overhead
- Bufferless
  When two packets want to go enter a node, one is deflected and goes some other way 
  New traffic can be injected only if there is a free output link
  Links are used as buffers
  
  May lead to [[Livelock]]
  Router complexity
  Congestion at high loads
  [[Total_Order|Total Order]] is enough to guarantee progress, but all that matters is that there is a *single* flit is prioritized.
  
- Store and Forward
  Packet copied entirely into network before moving  to the next node
  
- Virtual Cut Through
  Store and forward but packets are forwarded as soon as header is received and resources are allocated
  does not wait until full packet is transmitted
- Wormhole
  Chop packet into smaller allocation units, transfer flits like caterpillar

### Buffer Availability
- Credit based flow control
  Upstream knows how many buffers are downstream
  downstream passes back credits to upstream to signal it is free
- On/Off  flow control
  Downstream has on/off signal to upstream
- ACK/NACK
  upstream sends downstream but  buffer is not freed until ACK/NACK received
- Optimistic
  Just send the data

Note that with some availability communication mechanism, if the buffers are too small, the availability communication may dominate the network.

## Performance

![[Network_Performance-Latency.png]]

Minimum latency is result of network Topology and Routing.

Ideal Latency
$$T_{Ideal} = \frac{D}{v} + \frac{L}{b}$$
where 
- $D$ = Manhattan Distance 
- $v$ = propagation velocity
- $L$ = packet size
- $b$ = channel bandwidth

Actual  Latency
$$T_{actual} = \frac{D}{v} + \frac{L}{b} + H \cdot T_{router}  + T_c $$

where 
- $H$ = Hops
- $T_{router}$ = router latency
- $T_c$ = latency due to contention


### Metrics
- Latency  (avg/max)
- Round Trip Latency (avg/max)
- Saturation throughput
- Application Level Execution Time
- System Level Job Throughput 

## Lectures
- Onur Mutlu - ACA

#lecture_om_ACA