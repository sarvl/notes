#networking 

A network is a general term for a set of connected things that communicate. Important consideration is [[Traffic_Engineering|Traffic Engineering]]]].

This includes
- [[Computer_Network|Computer Network]]
- [[Chip_Network|On Chip Network of Cores]]


## Design Considerations
- Capacity planning
- Quality of Service: Traffic prioritization
- Reliability and redundancy: fail over, replication
- Security:  [[Cryptography|Encryption]], authentication, secure management
- Scalability: Addressing, routing, distributed systems
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
- Bus
  All nodes connected to single cable
- Star
  All nodes connected to central device
- Ring
  Each node connected to two neighbors
- Mesh
  Nodes interconnected
- Tree
  Hierarchical structure