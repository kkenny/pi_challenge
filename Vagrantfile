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
    chef.vm.network "private_network", ip: "10.0.0.2", netmask: "255.255.255.0"
    chef.vm.hostname = "chef"
    chef.vm.box = "centos/7"
    chef.vm.provider :virtualbox do |chef_vb|
      chef_vb.memory = "1024"
      chef_vb.cpus = "2"
    end
    chef.vm.provision "shell", path: "bootstrap-chef.sh"
  end

  config.vm.define "lb1" do |lb1|
    lb1.vm.network "private_network", ip: "10.0.0.4", netmask: "255.255.255.0"
    lb1.vm.network "forwarded_port", guest: 80, host: 8080
    lb1.vm.hostname = "lb1"
    lb1.vm.box = "centos/7"
    lb1.vm.provision "shell", path: "bootstrap-lb-master.sh"
  end

  config.vm.define "lb2" do |lb2|
    lb2.vm.network "private_network", ip: "10.0.0.5", netmask: "255.255.255.0"
    lb2.vm.hostname = "lb2"
    lb2.vm.box = "centos/7"
    lb2.vm.provision "shell", path: "bootstrap-lb-slave.sh"
  end

  config.vm.define "web1" do |web1|
    web1.vm.network "private_network", ip: "10.0.0.6", netmask: "255.255.255.0"
    web1.vm.hostname = "web1"
    web1.vm.box = "centos/7"
    web1.vm.provision "shell", path: "bootstrap-web.sh"
  end

  config.vm.define "web2" do |web2|
    web2.vm.network "private_network", ip: "10.0.0.7", netmask: "255.255.255.0"
    web2.vm.hostname = "web2"
    web2.vm.box = "centos/7"
    web2.vm.provision "shell", path: "bootstrap-web.sh"
  end

  config.vm.define "web3" do |web3|
    web3.vm.network "private_network", ip: "10.0.0.8", netmask: "255.255.255.0"
    web3.vm.hostname = "web3"
    web3.vm.box = "centos/7"
    web3.vm.provision "shell", path: "bootstrap-web.sh"
  end

  config.vm.define "db1" do |db1|
    db1.vm.network "private_network", ip: "10.0.0.9", netmask: "255.255.255.0"
    db1.vm.hostname = "db1"
    db1.vm.box = "centos/7"
    db1.vm.provision "shell", path: "bootstrap-db-master.sh"
  end

  config.vm.define "db2" do |db2|
    db2.vm.network "private_network", ip: "10.0.0.10", netmask: "255.255.255.0"
    db2.vm.hostname = "db2"
    db2.vm.box = "centos/7"
    db2.vm.provision "shell", path: "bootstrap-db-slave.sh"
  end
end
