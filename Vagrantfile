# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  
  config.vm.box = "hashicorp/precise64"
  config.vm.synced_folder "./selenium-grid-scaler", "/data"

  config.vm.network :public_network

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./provisioning/system.yml"
    ansible.sudo = true
    ansible.ask_sudo_pass  = true
    ansible.verbose = "vv"
    ansible.extra_vars = { ansible_ssh_user: "vagrant" }
  end 

end
