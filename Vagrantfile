# -*- mode: ruby; -*-
#


Vagrant.configure("2") do |config|
  #config.vm.box = "opengenera"
  config.vm.box = "opscode-ubuntu-10.04"

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.omnibus.chef_version = :latest

  #config.vm.forward_port 5901, 5902
  config.vm.network "forwarded_port", guest: 5901, host: 5902

  # Enable and configure the chef solo provisioner
  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = "cookbooks"

    # the magic
    chef.add_recipe "opengenera"
  end
end
