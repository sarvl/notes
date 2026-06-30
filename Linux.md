#operating_systems 

Linux is an [[Operating_System|Operating System]].



## Commands
syntax
`command options arguments`

List
- `cd` - change of directory
- `man` - view manual
- `ls` `lsblk` `lsusb` - list directory, list block devices, list [[USB]] devices
- `lsof` - list open files, useful for unmounting external drives
- `mount` `umount` - mount or unmount external drive
- `chmod` - change file access rights
- `pwd` - show current path
- `touch` - create empty file or update access time
- `rm` - remove file
- `rmdir` - remove directory
- `mkdir` - create directory
- `cp` - copy file
- `mv` - move or rename file
- `less` - show file contexts in scrollable way
- `cat` - show file contents
- `echo` - print text
- `dd` - copy data block by block
- `tar` - create archive
- `md5sum` - calculate [[md5]] checksum
- `sha256sum` - calculate [[sha256]] checksum
- `fdisk` - manipulate disk partition info, generally use `cfdisk` for manual stuff
- `env` `setenv` - display or set environment variables
- `ps` - list processes
## File System

### Files
Few file types are distinguished
- Regular
- Directories
- Block or character special files
- symbolic links
- named pipes
- domain socket

Each file is represented by an i-node.
Commonly used are file extensions to indicate what kind of file something is, for example `.pdf` for pdf. Its primary purpose is for user to easily associate each file type with purpose.

Several names can point to the same file. Both as a symbolic (path) and hard (actual another name) to another i-node.
Each director (except for root) has at least two hard links: itself (`./`) and its parent (`../dir`).


### Tree
All files are organized in a single directory tree starting with root `/`.

```
/
├── bin -> usr/bin
├── boot
├── dev
├── etc
├── home
├── lib -> usr/lib
├── lib64 -> usr/lib
├── lost+found
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> usr/bin
├── srv
├── sys
├── tmp
├── usr
├── var
```

###  Permissions
Each file has set of info associated with it 
- type 
	- `-` - regular
	- `d` - directory
	- `b` - block special file
	- `c` - character special file
	- `l` - symbolic link
	- `p` - named pipe
	- `s` - domain socket
- user permissions
	- `r` - read
	- `w`  - write
	- `x`  - execute
	- `s` - modification of effective user id 
	- `-` - none
- group permissions
	- `r` - read
	- `w`  - write
	- `x`  - execute
	- `s` - modification of effective group id
	- `-` - none
- others permissions
	- `r` - read
	- `w`  - write
	- `x`  - execute
	- `t` - sticky, restricted deletion 
	- `-` - none
- whether it's a link
- owner id
- group owner id
- size
- time of creation
- time of modification
- name

### Permissions
See above for description for options. Before file is accessed, appropriate permissions are checked for read/write/execute.
If the user id matches, `u` bits are checked, if group id matches, `g` bits are checked, otherwise `o` bits are checked.
If the `s` bits are set, then during execution the user or group id are changed to that of a process. These user and group id are called *effective user/group id*. 
If the `t` bit is set, then the file cannot be deleted by others.

Default access rights depend on mask, set by `umask`, which determines  which permissions are **disabled** by default.
Though, by default, execute permissions are always disabled.\


### Sparse Files
Sparse files may contain holes which result in only `0` and does not take any space on storage.

## Special files
These files are used to represent different devices or operating system like
- [[Computer_Storage|Drives]], and partitions
- [[CD|CDs]]
- [[Sound_Card|Sound Cards]]
- [[USB]] and [[COM]] ports
- virtual devices  (eg [[Random_Number_Generator|Random Number Generators]])


Drives are stored as 
- `/dev/sdX` - for [[SATA]]
- `/dev/hdX` - for [[ATA]]
- `/dev/scdX` or `/dev/srX` - for [[CD]], first one is usually also available as `/dev/cdrom`

### Interactions
All files are interacted with via file descriptors. There are few default file descriptors: `stdin`= 0, `stdout` = 1, and `stderr`  = 2.

Input/output can be redirected to files with 
- `program < file` read from `file` to stdin
- `program << text` read from keyboard until "text" appears as input
- `program > file` stdout is redirected into `file`, completely overwriting file
- `program >> file` stdout is redirected into `file`, appending to it
- `program1 | program2` stdout of program2 is redirected to stdin of program2
stderr can be redirected with `2>` and `2>>`

These file descriptors are local, meaning that two separate processes might have different file descriptor despite refering to the same file.


## Environment Variables

Environment variables are files that store information about the environment and can be accessed by the programs.

## Swap
Swap is a special file or partition used to store unused pages.


## Processes
Processes are created via `fork` to create new process and then `exec` to change child into desired program.

The first process created is called Init.

A daemon is a kind of process that is, by design, long lived and runs in the background. 

## Signals
Signals are asynchronous method of informing about events. Sometimes called software interrupts.

## Memory
Linux does seem to have pretty poor memory management while close to system limit. 
This can be fixed by setting `vm/min_free_kbytes`
```sh
echo "vm.min_free_kbytes=262144" >> /etc/sysctl.conf  
sysctl -p  
```


%%

## TODO
- verify
- organize