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


## TODO
- fact check
- explain filtering
- create diagram images