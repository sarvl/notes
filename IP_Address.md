#networking 

IP Addresses are used in [[Computer_Network#Reference Models#OSI|Network Layer]] as a way to identify hosts.

## IPv4

IPv4 is a 32-[[Binary|bit]] address, usually divided into 4 octets and represented in decimal, e.g. 192.168.1.16.

A network address is address of a network, the first address in a range. 
A broadcast address is address which delivers to all computers in a network, the last address in a range.

### Mask
A mask is used to divide networks and hosts. It can be used to further create subnets within particular network. It is always formed by a consecutive string of 1s.

Notation
- Dotted decimal
  eg. 255.255.128.0
- Slash
  eg. /17
### Classes
- A
  from 0.0.0.0/8 to 127.0.0.0/8 
- B
  from 128.0.0.0/16 to 191.255.0.0/16
- C
  from 192.0.0.0/24 to 223.255.255.0/24
- D
  from 224.0.0.0/? to 239.?.?.?/?
- E
  from 240.0.0.0/? to 255.?.?.?/?

### Private Addresses
These addresses are free to use on local networks and they must never be exposed to global network. 
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

### Special Purpose
- 0.0.0.0/8
- 127.0.0.0/8
  loopback (refers to the host)
- 169.254.0.0/16
- 192.0.0.0/24
- 192.0.2.0/24
- 192.88.99.0/24
- 198.18.0.0/15
- 198.51.100.0/24
- 203.0.113.0/24
- 224.0.0.0/4 former class D, multicast
- 240.0.0.0/4 former class E

### Types
- unicast
- multicast
- broadcast
## IPv6



## TODO
- examples
- explain empty sections
- explain class D and E 
- difference between network address and broadcast address
- organize