# Hardware
Mounting cd:
```bash
    lsblk #checking name of device (probably /dev/cdrom)
    mkdir /mnt/cdrom
    mount -t iso9660 -o ro /dev/cdrom /mnt/cdrom
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
# Programming


# Networking

# Monitoring

# Logs

# Text

