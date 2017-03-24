# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  def configure(c, addr)
    c.vm.box = "bento/ubuntu-16.04"
    c.vm.network :private_network, ip: addr
    c.vm.box_check_update = false
    c.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end
  end

  config.vm.define "vitess-mgr01" do |c|
    configure c, "192.168.44.101"
  end

  config.vm.define "vitess-node01" do |c|
    configure c, "192.168.44.102"
  end

  config.vm.define "vitess-node02" do |c|
    configure c, "192.168.44.103"
  end

  config.vm.define "vitess-node03" do |c|
    configure c, "192.168.44.104"
  end
end
