# Storage Virtualization

## VM1
### In VirtualBox
- create Virtual Hard Disk in VM1: Setting --> Storage --> Controller SATA --> Add

### In VM1
- check new disk: `sudo /dev/sdb`
- partition new disk: `sudo dfisk /dev/sdb`
- check new partition: `sudo /dev/sdb1`
- format /dev/sdb1: `sudo mkfs -t ext4 /dev/sdb1`
- check mounts: `sudo df`: not yet mounted
- mount /dev/sdb1: `sudo mount /dev/sdb1 /mnt`
- check mounts: `sudo df`

### Manipulation
- `cd /mnt`
- `touch toto.txt`
- `echo xxx toto.txt`

## VM2
### In VirtualBox
- Attack the Virtual Hard Disk to VM2: Setting --> Storage --> Controller SATA --> Add (existing)

### In VM2
- check mounts: `sudo df`: not yet mounted
- mount /dev/sdb1: `sudo mount /dev/sdb1 /mnt`
- check mounts: `sudo df`

### Manipulation
- `cd /mnt`
- `cat toto.txt`
