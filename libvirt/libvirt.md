# Libvirt
## Prerequisite
- install libvirt: `sudo apt install libvirt-bin virtinst virt-manager`

## Libvirt 
Create a VM through `Libvirt`
- copy image to `libvirt` dir: `sudo cp debian-mini.img /var/lib/libvirt/images/`
- create a VM with the configuration file [myvm.libvirt.xml](myvm.libvirt.xml)
- configure the permission in `/var/run/libvirt/libvirt-sock` for `unix_sock_rw_perms` with `0777`
- launch the VM `virsh create myvm.libvirt.xml`
- check the VM: `virt-manager`
- create an apache2 server in the VM
- access the web page through http://localhost:8883/

