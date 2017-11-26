# Vagrant
## Prerequisite
- install vagrant: `sudo apt install vagrant`

## Manipulation
- `vagrant up`: launch a VM through `Vagrantfile`
- `vagrant destroy`: stop a VM
- `vagrant box list`: list all vagrant box (VM images)

### Network
- NAT: `config.vm.network "forwarded_port", guest: 80, host: 8884`
- private (virtualbox private + host-only): `config.vm.network "private_network", ip: "88.88.89.3"`
- public (virtualbox bridged): `config.vm.network "public_network", ip: "88.88.88.3"`

### ssh
by default, private key authentication
change to password authentication, in `Vagrantfile`:
- `config.ssh.username = "vagrant"`
- `config.ssh.password = "vagrant"`

## TP
Create an apache2 server in a VM through `vagrant`
- launch vagrant with automatically installation: `vagrant up`
- check the status of vagrant: `vagrant status`
- access the web page through `http://localhost:8884/`