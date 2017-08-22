# -*- mode: ruby -*-
# vi: set ft=ruby :

#
Vagrant.configure("2") do |config|
  
	config.vm.define "blogvm" do |blogvm|
		blogvm.vm.box = "ubuntu/trusty64"
		blogvm.vm.network :private_network, ip: "192.168.33.22"
	end
	
	config.vm.provision "ansible_local" do |ansible|
		ansible.playbook = "blog.yml"
		ansible.verbose = "vvv"
	end
	
	config.vm.provider "virtualbox" do |v|
		v.customize ["modifyvm", :id, "--memory","1024"]
	end

end