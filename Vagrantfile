# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  config.vm.box = "precise32"

  config.vm.define "root" do |root_vm|
    root_vm.vm.network :private_network, ip: "192.168.2.30"
    root_vm.vm.hostname = "root.vagrant"

    root_vm.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end

    root_vm.vm.provision "ansible" do |ansible|
      ansible.limit = "root"
      ansible.playbook = "books/vagrant.yml"
      ansible.inventory_path = "local.inv"
      ansible.sudo = true
    end
  end

  config.vm.define "s1" do |s1|
    s1.vm.network :private_network, ip: "192.168.2.31"
    s1.vm.hostname = "s1.vagrant"

    s1.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end

    s1.vm.provision "ansible" do |ansible|
      ansible.limit = "s1"
      ansible.playbook = "books/vagrant.yml"
      ansible.inventory_path = "local.inv"
      ansible.sudo = true
    end
  end

  config.vm.define "s2" do |s2|
    s2.vm.network :private_network, ip: "192.168.2.32"
    s2.vm.hostname = "s2.vagrant"

    s2.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end

    s2.vm.provision "ansible" do |ansible|
      ansible.limit = "s2"
      ansible.playbook = "books/vagrant.yml"
      ansible.inventory_path = "local.inv"
      ansible.sudo = true
    end
  end
end
