# -*- mode: ruby -*-
# vi: set ft=ruby :

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "geerlingguy/ubuntu2004"
    config.vm.box_check_update = "false"
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    config.vm.define "webserver" do |web|
      config.vm.hostname = "yolo"
      config.vm.network :private_network, ip: "192.168.56.10"
      config.vm.network "forwarded_port", guest: "80", host: "8080"
      config.ssh.insert_key = false
      
      #Provision the server with Ansible
      config.vm.provision "ansible" do |ansible|
        ansible.playbook="playbook.yml"
      end
     end
   end