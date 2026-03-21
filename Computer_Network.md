#networking


Computer Network is any group of computers that communicates together. Within such network, computers are organized by some addresses needed to identify particular hosts.


## Topologies


## Reference Models
Division into such models simplifies implementation of networking devices, each layer has an abstraction of directly talking to another device in the same layer, despite actual communication happening on top of much lower level protocols. The act of passing data from higher to lower level and adding appropriate headers is called **encapsulation**.

### OSI
1. Physical 
   [[Binary|bits]]
   [[Switch]]
   [[Ethernet]], [[WiFi]]
2. Data Link
   frames 
   [[Switch]]
   [[Ethernet]], [[WiFi]]
3. Network  
   packets/datagrams  
   [[Router]]
   [[IP_Address||IP]], [[ICMP]]
4. Transport  
   segments
   [[TCP]], [[UDP]]
5. Session  
   data/[[File|files]]/[[Stream|streams]]
6. Presentation  
   data/[[File|files]]/[[Stream|streams]]
7. Application  
   data/[[File|files]]/[[Stream|streams]]

### TCP/IP
1. Link (Physical + Data Link)
   [[Binary|bits]] and frames
   [[Switch]]
   [[Ethernet]], [[WiFi]]
2. Internet (Network) 
   packets/datagrams 
   [[Router]]
   [[IP_Address||IP]], [[ICMP]]
3. Transport (Transport) 
   segments
   [[TCP]], [[UDP]]
4. Application (Session + Presentation + Application) 
   data/[[File|files]]/[[Stream|streams]]


## Range
- LAN
  Local Area Network
- WAN
  Wide Area Network

## TODO
- history 
- links to reference models
- topologies