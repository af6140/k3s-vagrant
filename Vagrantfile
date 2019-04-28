# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = true

  config.vm.define "master", primary: true do |master|
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "10.7.1.10"

    master.vm.provider "virtualbox" do |vb|
      vb.name = "k3s-master"
      vb.cpus = 1
      vb.memory = "1024"
    end
  end

  num = 2
  (1..num).each do |i|
    config.vm.define "node-#{i}" do |node|
      node.vm.hostname = "node-#{i}"
      node.vm.network "private_network", ip: "10.7.1.2#{i}"

      node.vm.provider "virtualbox" do |vb|
        vb.name = "k3s-node-#{i}"
        vb.cpus = 1
        vb.memory = "2048"
      end
    end
  end
end
