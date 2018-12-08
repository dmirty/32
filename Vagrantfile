# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.synced_folder ".", "/vagrant",type:"virtualbox"
  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
  end
  

  config.vm.define "srv01" do |srv01|
    srv01.vm.network "public_network", ip: "192.168.1.70"
    srv01.vm.hostname = "srv01.local"
	
  end

  config.vm.define "client01" do |client01|
    client01.vm.network "public_network", ip: "192.168.1.71"
    client01.vm.hostname = "client01.local"
	 
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "vvv"
    ansible.playbook = "Playbook.yml"
    # Ansible_ssh_user
    ansible.force_remote_user = "vagrant"
    ansible.become = "true"
   
    ]
  end
       
 


end
