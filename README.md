# k3s-vagrant

Creates three virtual machines in virtual box:

1. Master: k3s server with 1GB RAM and 1 vCPU
2. 2xNode: k3s agents with 2GB RAM and 1 vCPU each

Requeriments:

1. Vagrant
2. Virtualbox


## Usage

```
vagrant up
cd provisioning
ansible-playbook playbook.yml
```