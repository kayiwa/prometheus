# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # create some web servers
  # https://docs.vagrantup.com/v2/vagrantfile/tips.html
  (1..4).each do |i|
    config.vm.define "web#{i}" do |node|
        node.vm.box = "ubuntu/xenial64"
        node.vm.hostname = "web#{i}"
        node.vm.network :private_network, ip: "10.0.15.2#{i}"
        node.vm.network "forwarded_port", guest: 80, host: "808#{i}"
        node.vm.provider "virtualbox" do |vb|
          vb.memory = "2048"
        end
    end
  end

end
