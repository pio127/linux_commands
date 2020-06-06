# Apt and dpkg
Show all installed packages:
```bash
apt list --installed
dpkg --list
```

# Files
Find all files containing given filename (not case sensitive) and find all phrase occurences in each of them (color printing with filenames and line numbers):
```bash
find . -iname "*filename*" -exec grep --color -Hn "phrase" {} \;
```
Watch 10 most recently updated files in current folder:
```bash
watch -n 0.5 'ls -lhatr | tail -n 10'
```

# Hardware
Mounting cd:
```bash
lsblk #checking name of device (probably /dev/cdrom)
mkdir /mnt/cdrom
mount -t iso9660 -o ro /dev/cdrom /mnt/cdrom
```

# Monitoring
Watch bandwith of a chosen network interface:
```bash
iftop -i eth0
```
# Networking
Check details of all network interfaces:
```bash
ip addr
ifconfig
```
Add ip address to network device:
```bash
ip addr add 192.168.1.50/24 dev eth0
```
Remove ip address attached to network device:
```bash
ip addr delete 192.168.1.50/24 dev eth0
```
Restart network interface:
```bash
ifdown eth0
ifup eth0
```
Restart all network inerfaces:
```bash
/etc/init.d/networking restart
systemctl restart networking.service
```
Ping all addresses in range defined by netmask:
```bash
nmap -sP 192.168.1.0/24
```
Print all opened ports:
```bash
netstat -tulpn
```

# Programming
Check all load-time dependecies of executable or dynamic library:
```bash
ldd executable
ldd shared_library.so
```

List all symbols of a binary file in demangled form (C++):
```bash
nm -C library
objdump -C -t library
```

Disassemble binary file and mix with source code:
```bash
objdump -S -C -d library
```
Read binary object file header:
```bash
readelf -h library
```

Track all system calls made by process:
```bash
strace executable
```

Change runpath of shared library or executable:
```bash
patchelf --set-rpath path
```

# SSH
Generate public key and share it with remote host:
```bash
ssh-keygen -t rsa
ssh-copy-id name@host_ip
```

Send a copy of local directory to remote host over SSH:
```bash
scp -r local_directory/ name@host_ip:~/
```

Get a copy of local file from remote host over SSH:
```bash
scp name@host_ip:~/remote_file ./
```

Using sftp:
```bash
sftp name@host_ip
# when connected: 
get remote_file ~/local_folder/ # copying file
bye # ending connection
```

# System
Set current time manually:
```bash
date --set="31 May 2020 10:00:00"
```

# Systemd
Services boot time:
```bash
systemd-analyze blame
```

Listing all active services:
```bash
systemctl --type=service --state=active

```

# Text