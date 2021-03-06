# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  config.vm.network "forwarded_port", guest: 5000, host: 5001 # using 8081 on host to prevent local conflict
  config.vm.network "forwarded_port", guest: 1433, host: 1434 # using 34 on host to prevent conflict
  config.vm.network "forwarded_port", guest: 5432, host: 5433 # using 5433 on host to prevent conflict

  # Share additional folder to guest VM. First argument is path on
  # host to the actual folder. Second argument is path on guest to mount folder
  # Optional third argument, set of non-required options.
  config.vm.synced_folder "share/", "/vagrant"

  # Provision Docker and git
  config.vm.provision :docker
  config.vm.provision "shell" do |s|
    s.inline = "sudo apt-get update"
    s.inline = "sudo apt-get install -y git"
  end
end
