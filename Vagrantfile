# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box"
  config.vm.network "private_network", type: "dhcp"

  config.vm.define "web1" do |web|
      web.vm.box = "https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box"
      web.vm.network "forwarded_port", guest: 80, host: 8080
      web.vm.network "forwarded_port", guest: 22, host: 2020, id: "ssh"
  end

  config.vm.define "web2" do |web|
      web.vm.box = "https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box"
      web.vm.network "forwarded_port", guest: 80, host: 8081
      web.vm.network "forwarded_port", guest: 22, host: 2021, id: "ssh"
  end

  config.vm.define "loadbalancer" do |loadbalancer|
      loadbalancer.vm.box = "https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box"
      loadbalancer.vm.network "forwarded_port", guest: 80, host: 8085
      loadbalancer.vm.network "forwarded_port", guest: 22, host: 2022, id: "ssh"
  end
end
