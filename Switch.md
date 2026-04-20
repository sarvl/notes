#telecom  

A switch is [[Computer_Network#TCP/IP|Link]] level device operating on [[Ethernet]]. Its main purpose is to *switch* where *frames* go, to redirect them to the proper destination. A switch may operate in [[Computer_Network#TCP/IP|Network]] Layer, combining features of [[Router]] and typical [[Switch]], but generally without access to [[Computer_Network#Range|Wan]]

## Simplified View
A switch transfers a frame from one interface to another based on its [[MAC_Address|MAC Address]]. 
To create and sustain switching table (ST), used to redirect traffic, it uses 5 functions: 
- Learning
  When an incoming packet has **source** not in ST, bind its source to the interface
  Note that more than 1 device may be mapped to an interface
- Flooding
  When an incoming packet has **destination** not in ST, send it to all but the source interfaces
- Forwarding
  When an incoming packet has **destination** in ST, send it to just that interface
- Filtering
  When an incoming packet has the same destination and source, do not send it
  This is useful in configuration like 
  ```
	  Host A -\
	          Hub -- Switch 
	  Host B -/
  ```
  
- Aging
  After set time, the entry is removed
  
## Security
Storm control is launched for all frames addressed to broadcast or multicast and with unknown destination. It prevents network overflow, most notably it prevents attacks.

Detecting storm:
- frames per second (pps, not fps)
- bits per second (bps)
- bandwidth as percentage of the total available bandwidth of the port that can be used

Reaction
- Block traffic on port after threshold
- Block all traffic after threshold


Protected ports are used to disable particular transfer of packets. They disallow exchange of unicast, broadcast, or multicast between these ports.  No communication can happen *between* protected ports.


Port blocking allows to disable flooding onto that port.


Mac flooding is an attack of sending a lot of frames with different source addresses to fully occupy switching table.

Alternatively, someone might change their mac address to pretend to be someone else. In this case, certain range of MACs can be assigned to particular ports.
Defense methods
- Protect
  Drop all with unknown source addresses when more connected than allowed 
- Restrict
  Like protect but also notify
- Shutdown
  Like restrict, but also completely disable port on security violation
- Shutdown VLAN
  Like shutdown, but also disable the entire VLAN


**IEEE 802.1x** defines client-server access control and authentication protocol.

Access Control List is used to filter traffic when it traverses through [[Router]] or [[Switch]]. It is a sequential list of permits or denies, it permits or denies particular packet crossing over interface or VLAN. First mach decides what happens - no match implies rejection.

## TODO
- fact check
- explain filtering
- create diagram images