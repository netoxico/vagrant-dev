# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
    # vagrant init ubuntu/xenial64
    config.vm.box = "geerlingguy/ubuntu1604"
    config.vm.network "forwarded_port", guest: 8000, host: 8000, id: "django", auto_correct: true
    config.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", auto_correct: true
    config.vm.network "private_network", type: "dhcp"
    # config.ssh.insert_key = false

    config.vm.provision "ansible" do |ansible|
        # ansible.verbose = "v"
        ansible.playbook = "provisioning/playbook.yml"
    end

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end

end
