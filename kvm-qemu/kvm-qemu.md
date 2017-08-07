# KVM and QEMU
## Prerequisite
- install: `sudo apt install qemu-kvm`
- check: `sudo lsmod | grep kvm`

## KVM
- launch VM: `kvm -hda debian-mini.img -boot c -m 1024 -net user -net nic -redir tcp:8880::80 -redir tcp:2222::22`
- access VM: `login: vagrant, password: vagrant`
- create an apache2 server in the VM
- show the web page through: `http://localhost:8880/`

## QEMU
- launch VM: `qemu-system-x86_64 -hda debian-mini.img -boot c -m 1024 -net user -net nic -redir tcp:8881::80 -redir tcp:2222::22`
- access VM: `login: vagrant, password: vagrant`
- create an apache2 server in the VM
- show the web page through: `http://localhost:8881/`
