# System
Set current time manually:
```bash
    date --set="31 May 2020 10:00:00"
```

# Hardware
Mounting cd:
```bash
    lsblk #checking name of device (probably /dev/cdrom)
    mkdir /mnt/cdrom
    mount -t iso9660 -o ro /dev/cdrom /mnt/cdrom
```
# Apt
Show all installed packages:
```bash
    apt list --installed
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

# Files
Find all files containing given filename (not case sensitive) and find all phrase occurences in each of them (color printing with filenames and line numbers):
```bash
    find . -iname "*filename*" -exec grep --color -Hn "phrase" {} \;
```
Watch 10 most recently updated files in current folder:
```bash
    watch -n 0.5 'ls -lhatr | tail -n 10'
```
# Programming

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


# Networking
Check details of all network devices:

Add ip address to network device:

Remove ip address attached to network device:

Restart networking:

# Monitoring

# Logs
```bash

```

# Text

