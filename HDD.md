#computer_architecture #hardware

HDD is a type of [[Computer_Storage|Computer Storage]] that organizes data as magnetic field changes on a circular disk.

Head moves in circular track around the disk, where information is encoded. Head can switch tracks. A cylinder is a collection of tracks on different disks above each other. A sector is smallest addressable element.
This head moves on a very thin gas cushion, usually helium.

Old disks used Cylinder-Head-Sector CHS addressing, modern disks have decoupled physical addressing from actual addressing and they use Logical Block Addressing LBA.

Contrary to [[SSD]], data in blocks can be modified in place. 

Random access time consists of 
1. seek time to find proper cylinder
2. rotational time to get to desired sector 

Performance is often increased by [[RAM]] buffers and access queueing and reordering.



%% 

## TODO
- schematics