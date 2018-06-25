# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.forward_agent = true
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]
    v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
  end
  config.vm.define 'node1' do |machine|
    machine.vm.box = "ubuntu/xenial64"
    machine.vm.hostname = "node1"
    machine.vm.box_url = "ubuntu/xenial64"
    machine.vm.network :private_network, ip: "192.168.85.201"
    machine.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
      disk = "node1.vdi"
      unless File.exist? (disk)		    
        v.customize ['createhd', '--filename', disk, '--size', 5 * 1024]
      end
      v.customize ['storageattach', :id, '--storagectl', 'SCSI', '--port', 2, '--device', 0, '--type',  'hdd', '--medium', disk]
    end
  end

  config.vm.define 'node2' do |machine|
    machine.vm.box = "ubuntu/xenial64"
    machine.vm.hostname = "node2"
    machine.vm.box_url = "ubuntu/xenial64"
    machine.vm.network :private_network, ip: "192.168.85.202"
    machine.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
      disk = "node2.vdi"
      unless File.exist? (disk)
        v.customize ['createhd', '--filename', disk, '--size', 5 * 1024]
      end
      v.customize ['storageattach', :id, '--storagectl', 'SCSI', '--port', 2, '--device', 0, '--type',  'hdd', '--medium', disk]
    end
  end

  config.vm.define 'node3' do |machine|
    machine.vm.box = "ubuntu/xenial64"
    machine.vm.hostname = "node3"
    machine.vm.box_url = "ubuntu/xenial64"
    machine.vm.network :private_network, ip: "192.168.85.203"
    machine.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
      disk = "node3.vdi"
      unless File.exist? (disk)
        v.customize ['createhd', '--filename', disk, '--size', 5 * 1024]
      end
      v.customize ['storageattach', :id, '--storagectl', 'SCSI', '--port', 2, '--device', 0, '--type',  'hdd', '--medium', disk]
    end
  end
end
