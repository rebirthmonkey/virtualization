# Vagrant
## Prerequisite
- install vagrant: `sudo apt install vagrant`

## Manipulation
- `vagrant up`: launch a VM through `Vagrantfile`
- `vagrant destroy`: stop a VM
- `vagrant box list`: list all vagrant box (VM images)

### Network
- NAT: VirtualBox NAT
  - `config.vm.network "forwarded_port", guest: 80, host: 8884`
- private: VirtualBox NAT + VirtualBox host-only
  - `config.vm.network "private_network", ip: "88.88.89.3"`
- public: VirtualBox NAT + VirtualBox bridge
  - `config.vm.network "public_network"`

### ssh
by default, private key authentication
change to password authentication, in `Vagrantfile`:
- `config.ssh.username = "vagrant"`
- `config.ssh.password = "vagrant"`

## TP
### TP1: Apache Web Server
Create an apache2 server in a VM through the [Vagrantfile](Vagrantfile)
- launch vagrant with automatically installation: `vagrant up`
- check the status of vagrant: `vagrant status`
- access the web page through `http://localhost:8884/`

### TP2: Frontend Backend Framework
Create a frontend and a backend VM through the [Vagrantfile](tp/Vagrantfile)
- `cd tp`
- `vagrant up`
