# VirtualBox
## Prerequisite
- install: `sudo apt install virtualbox`

## Network
### Bridge Network
Equivalent to host NIC, also get an external IP address
- VM can access to the Internet
- external Internet machine can access to VM

### NAT
Virtualbox does a NAT between external traffic and VM
- VM can access to the Internet
- external Internet machine can't access to VM

### Host-only Network
This only allows the host to access the VM
- create host-only network: `preference` --> `network` --> `host-only network` --> create a host-only network
- VM --> settings --> network --> Attached to `host-only X`: it will take the first IP address in the host-only network
- in the host, we can then access the VM e.g. `ssh vagrant 88.88.88.2`

### Private
Communication between VMs, VM can only access other VMs.
- set NICs of 2 VMs on private mode
- add static configuration for `/etc/network/interfaces`:
```
auto eth0
iface eth0 inet static
    address 10.0.0.41
    netmask 255.255.255.0
    network 10.0.0.0
    broadcast 10.0.0.255
    gateway 10.0.0.1
    dns-nameservers 10.0.0.1 8.8.8.8
```

## TP
- config General: `shared clipboard`
- config Network: `NAT`
- create an apache2 server in the VM
- access the web page through: `http://localhost:8882/`



