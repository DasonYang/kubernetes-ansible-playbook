# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Use the same key for each machine
  config.ssh.insert_key = false

  config.vm.define 'master' do |master|

    # Every Vagrant virtual environment requires a box to build off of.
    master.vm.hostname = "master"
    master.vm.box = "bento/ubuntu-16.04"

    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    master.vm.network "private_network", ip: "192.168.33.11"

    # If true, then any SSH connections made will enable agent forwarding.
    master.ssh.forward_agent = true

    master.vm.provider "virtualbox" do |vb|
      # Use VBoxManage to customize the VM. For example to change memory:
      vb.customize ["modifyvm", :id, "--memory", "4096", "--cpus", "4"]
    end
  end

  N = 3

  (1..N).each do |node_id|
    nid = (node_id - 1)

    config.vm.define "node#{nid}" do |node|
      # https://atlas.hashicorp.com/ubuntu/
      node.vm.hostname = "node#{nid}"
      node.vm.box = "bento/ubuntu-16.04"
      node.vm.network "private_network", ip: "192.168.33.#{20 + nid}"
      node.ssh.forward_agent = true
      
      node.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
        vb.cpus = 4
      end
    end
  end
end