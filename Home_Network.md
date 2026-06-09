#networking 


## Setting IP 
Usually it makes sense to have certain services assigned to static addresses. This can be done via either static [[IP_Address|IP]] on PC or via [[DHCP]] reservation. Long term it is better to use DHCP reservation as that provides central system that is easier to modify and maintain, but for quick fixes static IP is much faster to do.

## Cabling
- Label a lot 
- Use as little equipment as possible, upgrade, consolidate
- Lay out first, wire later
- Consider all power cables before wiring anything
- Keep inventory of common cable lengths
- Document

## Rack
You probably do not need a rack, if you do want a rack, get a mini one like https://mini-rack.jeffgeerling.com/.

## Raspberry Pi
### Headless setup 
1. Set up OS with `rpi-imager`
2. Create empty `ssh` file on the boot partition
3. Create `userconf.txt` file with contents `username:password` 
   Where username is in plain text while password is output of `openssl passwd -6`
   for example 
   `rpi:$6$4AVi2Qbdu3nxx3u9$BpKDmsqsNeaVCSrVkmSiciKKmipMgoOKXko5lRXG0B8wJ3G4iqdwsvcKG0AZ/wPmRqDbGCzjQwzj305oCIrSu/`

### USB Booting
1. Update and upgrade the system
2. Run `sudo raspi-config`, select `Advanced Options > Bootloader Version > Latest`, and reboot

## Media 

### Jellyfin

#### Setup
```sh
sudo apt update
sudo apt ugrade -y

sudo apt install apt-transport-https lsb-release

curl https://repo.jellyfin.org/debian/jellyfin_team.gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/jellyfin-archive-keyring.gpg >/dev/null

echo "deb [signed-by=/usr/share/keyrings/jellyfin-archive-keyring.gpg arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/debian $( lsb_release -c -s ) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list

sudo apt update

sudo apt install jellyfin
```

The rest can be easily followed with GUI
### Arr
Section empty until I do something with it 



## Monitoring
Section empty until I do something with it 

One tool I have seen is uptime kuma
## Pi Hole
#### Setup
```sh
sudo apt update && sudo apt upgrade -y

curl -sSL https://install.pi-hole.net | sudo bash
```

Remember to set RPI to have static IP, and to make router's DNS point to RPI.

#### Ad Block
Works basically out of the box. Keep in mind that it will not work properly with sites like youtube where ads are saved from the same domain as videos. It might be possible to use some regex to block ads, see https://discourse.pi-hole.net/t/how-do-i-block-ads-on-youtube/253. 
Local ad block is still recommended.
#### DNS
It is possible to use pi hole as DNS server, though I have not yet found a particular need for that.

#### DHCP
It is possible to use pi hole as DHCP server, though I have found my router to be more reliable than RPI and so I use my router directly for that.


## NAS
Section empty until I do something with it 

For now links I have gathered:
- https://www.openmediavault.org/


%%

## TODO
- organize for everything to form something cohesive