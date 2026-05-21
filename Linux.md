#operating_systems 

Linus is an [[Operating_System|Operating System]].

## Commands
syntax
`command options arguments`

List
- `cd` - change of directory
- `man` - view manual
- `ls` - list directory
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
- `md5sum` - calculate[[[md5]] checksum
- `sha256sum` - calculate [[sha256]] checksum
## File System

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
	- `s` - modification of effective group id 
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
If the `s` bits are set, then during execution the user or group id are changed to that of a process.
If the `t` bit is set, then the file cannot be deleted by others.

Default access rights depend on mask, set by `umask`, which determines  which permissions are **disabled** by default.
Though, by default, execute permissions are always disabled.\


### Sparse Files
Sparse files may contain holes which result in only `0` and does not take any space on storage.

## Special files
These files are used to represent different devices like
- [[Computer_Storage|Drives]], and partitions
- [[CD|CDs]]
- [[Sound_Card|Sound Cards]]
- [[USB]] and [[COM]] ports
- virtual devices  (eg [[Random_Number_Generator|Random Number Generators]])

### Interactions
All files are interacted with via file descriptors. There are few default file descriptors: `stdin`= 0, `stdout` = 1, and `stderr`  = 2.

Input/output can be redirected to files with 
- `program < file` read from `file` to stdin
- `program << text` read from keyboard until "text" appears as input
- `program > file` stdout is redirected into `file`, completely overwriting file
- `program >> file` stdout is redirected into `file`, appending to it
- `program1 | program2` stdout of program2 is redirected to stdin of program2
stderr can be redirected with `2>` and `2>>`
%%

## TODO
- verify
- organize