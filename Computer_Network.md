#telecom

Computer Network is any group of computers that communicates together. Within such network, computers are organized by some addresses needed to identify particular hosts.

## Reference Models
Division into such models simplifies implementation of networking devices, each layer has an abstraction of directly talking to another device in the same layer, despite actual communication happening on top of much lower level protocols. The act of passing data from higher to lower level and adding appropriate headers is called **encapsulation**.

### OSI
1. Physical
   Binary Transmission
   [[Binary|bits]]
   [[Switch]]
2. Data Link
   Link Control and Medium Access Control, error detection and correction
   frames 
   [[Switch]]
   [[Ethernet]], [[WiFi]], [[MAC_Address]],
3. Network
   Addressing and best path selection 
   packets/datagrams  
   [[Router]]
   [[IP_Address||IP]], [[ICMP]]
4. Transport  
   End-to-end data transfer, error detection and correction, retransmissions, packet ordering
   segments
   [[TCP]], [[UDP]]
5. Session  
   Dialogue between two applications
   sessions, [[Socket|Sockets]], [[Stream|Streams]]
6. Presentation  
   Representation of data, Code conversions,  [[Cryptography|Encryption]], [[Compression]]
7. Application  
   User interface
   data/[[File|files]]/[[Stream|streams]]
   [[HTTPS]], [[FTP]], [[DNS]], [[SMTP]]

### TCP/IP
1. Link (Physical + Data Link)
   Hardware addressing, media access, [[Error_Detection_And_Correction|Error Detection and Correction]]
   [[Binary|bits]] and frames
   [[Switch]], [[Bridge]], [[Hub]], Network Interface Card, Wireless Access Point
   [[Ethernet]], [[WiFi]]
   
	Sub-layers
	- Logical Link Control
	  Data multiplexing, framing, error control, flow control
	- Media Access Control
	  Frame addressing, congestion control
1. Internet (Network) 
   Addressing, routing
   packets/datagrams 
   [[Router]]
   [[IP_Address||IP]], [[ICMP]]
2. Transport (Transport) 
   Connection management
   segments
   [[TCP]], [[UDP]]
3. Application (Session + Presentation + Application) 
   Actual application
   data/[[File|files]]/[[Stream|streams]]
   [[HTTPS]], [[FTP]], [[DNS]], [[SMTP]]


## Communication Example

1. User types URL in a browser (Application)
2. Browser uses DNS to resolve hostname to IP (Application)
3. TCP establishes transport connection (Transport)
4. IP routes packets across networks (Network)
5. Ethernet/WiFi frames carry bits on local links (Link)

## Range
- LAN
  Local Area Network
- MAN
  Metropolitan Area Network
- WAN
  Wide Area Network

## TODO
- communication example
- split into other documents
- reorganize
- Images