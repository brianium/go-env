# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "trusty64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  
  config.vm.define :api_client do |api_client|
    api_client.vm.hostname = "api-client"
    api_client.vm.network "private_network", ip: "192.168.33.10"
    
    api_client.vm.provision :ansible do |ansible|
      ansible.playbook = "client.yml"
      ansible.inventory_path = "vagrant"
      ansible.limit = "client"
    end
  end
 
  config.vm.define :go_api do |go_api|
    go_api.vm.hostname = "go-api"
    go_api.vm.network "private_network", ip: "192.168.33.9"
    
    go_api.vm.provision :ansible do |ansible|
      ansible.playbook = "api.yml"
      ansible.inventory_path = "vagrant"
      ansible.limit = "api"
    end
  end

end
