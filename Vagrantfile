# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # create mgmt vm
  config.vm.define :mgmt do |mgmt_config|
      mgmt_config.vm.box = "ubuntu/trusty64"
      mgmt_config.vm.hostname = "mgmt"
      mgmt_config.vm.network :private_network, ip: "10.0.15.10"
      mgmt_config.vm.provider "virtualbox" do |vb|
        vb.memory = "256"
      end
      mgmt_config.vm.provision :shell, path: "bootstrap-mgmt.sh"
  end

  # create hats_base vm target
  # https://app.vagrantup.com/relativkreativ/boxes/centos-7-minimal
  config.vm.define :target do |target_config|
      target_config.vm.box = "relativkreativ/centos-7-minimal"
      target_config.vm.hostname = "target"
      target_config.vm.network :private_network, ip: "10.0.15.11"
      # target_config.vm.network "forwarded_port", guest: 80, host: 8081
  end

end
