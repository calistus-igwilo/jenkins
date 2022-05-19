# _*_ mode: ruby _*_
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    # General Vagrant VM configuration.
    config.vm.box = "geerlingguy/centos7"
    config.ssh.insert_key = false
    config.vm.synced_folder ".", "/vagrant", disabled: true 
    config.vm.provider :virtualbox do |v|
        v.memory = 256
        v.linked_clone = true
    end 

    # Jenkins server.
    config.vm.define "server" do |server|
        server.vm.hostname = "orc-server.dev"
        server.vm.network :private_network, ip: "192.168.56.10"
    end 

    # Jenkins slave 1.
    config.vm.define "slave1" do |slave|
        slave.vm.hostname = "orc-slave1.dev"
        slave.vm.network :private_network, ip: "192.168.56.11"
    end 

    # Database server.
    config.vm.define "slave2" do |slave|
        slave.vm.hostname = "orc-slave2.dev"
        slave.vm.network :private_network, ip: "192.168.56.12"
    end
end 