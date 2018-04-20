# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.provision "shell", inline: <<-SHELL
    yum install -y net-tools lsof wget
  SHELL

  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.memory = "512"
    vb.cpus = "1"
  end

  config.vm.define "chef" do |chef|
    chef.vm.box = "centos/7"
    chef.vm.provider :virtualbox do |chef_vb|
      chef_vb.memory = "1024"
      chef_vb.cpus = "2"
    end
    chef.vm.provision "shell", path: "bootstrap-chef.sh"
  end
  config.vm.define "lb1" do |lb1|
    lb1.vm.box = "centos/7"
  end
  config.vm.define "lb2" do |lb2|
    lb2.vm.box = "centos/7"
  end
  config.vm.define "web1" do |web1|
    web1.vm.box = "centos/7"
  end
  config.vm.define "web2" do |web2|
    web2.vm.box = "centos/7"
  end
  config.vm.define "web3" do |web3|
    web3.vm.box = "centos/7"
  end
  config.vm.define "db1" do |db1|
    db1.vm.box = "centos/7"
  end
  config.vm.define "db2" do |db2|
    db2.vm.box = "centos/7"
  end
end
