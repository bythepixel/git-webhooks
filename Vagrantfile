# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"

  config.vm.network "private_network", ip: "192.168.51.100"
  config.vm.network "forwarded_port", guest: 80, host: 4000

  config.vm.synced_folder ".", "/vagrant", type: "nfs"

  config.vm.provision :docker
  config.vm.provision :docker_compose, run: "always", yml: "/vagrant/docker-compose.yml"
end
