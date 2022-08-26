# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "zabbix-box" do |vm_config|
    vm_config.vm.box = "ubuntu/focal64"
    vm_config.vm.network "private_network", ip: "192.168.18.10"
    vm_config.vm.hostname = "zabbixbox"

    vm_config.vm.provider "virtualbox" do |vb|
      vb.name = "zabbix-box"
    end

    vm_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "zabbix-install.yml"
    end
  end

  config.vm.define "haproxy-box" do |vm_config|
    vm_config.vm.box = "ubuntu/focal64"
    vm_config.vm.network "private_network", ip: "192.168.18.11"
    vm_config.vm.hostname = "haproxybox"

    vm_config.vm.provider "virtualbox" do |vb|
      vb.name = "haproxy-box"
    end

    vm_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "haproxy-install.yml"
    end
  end
end
