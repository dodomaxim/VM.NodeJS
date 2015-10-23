# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Base box
  config.vm.box = "ubuntu/trusty64"

  # Configure the vm 
  config.vm.provider "virtualbox" do |v|
    v.name = "node-box"
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "75"]
    v.memory = 1024
  end

  # Run Bootstrap.sh when setting up the machine
  config.vm.provision :shell, :privileged => false, :path => "Bootstrap.sh"

  # BOX IP
  config.vm.network :private_network, ip: "192.168.100.101"

  # Shared folder
  config.vm.synced_folder "../application", "/var/www", create: "true"

end