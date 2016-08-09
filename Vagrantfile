# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
    # create web servers
    # Webserver 1
    config.vm.define "web1" do |node|
        node.vm.box = "geerlingguy/ubuntu1604"
        node.vm.hostname = "web1"
        node.vm.network :private_network, ip: "33.33.0.10"
        node.vm.network "forwarded_port", guest: 8000, host: "8000", id: "django",auto_correct: true
        node.vm.network "forwarded_port", guest: 22, host: "2222", id: "ssh", auto_correct: true
        node.vm.provision "ansible" do |ansible|
            ansible.verbose = "v"
            ansible.playbook = "provisioning/playbook.yml"
            ansible.extra_vars = {
                "roles" => ["common",
                            "python",
                            "mysql",
                            "nodejs"],
                # global npm packages to be installed with npm
                "npm_packages" => [{"name": "less"},
                                   {"name": "node-sass"}]
            }
        end
        node.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
            vb.cpus = 2
        end
    end
    # Optional Webserver 2
    # config.vm.define "web2" do |node|
    #     node.vm.box = "geerlingguy/ubuntu1604"
    #     node.vm.hostname = "web2"
    #     node.vm.network :private_network, ip: "33.33.0.11"
    #     node.vm.network "forwarded_port", guest: 8000, host: "8001", id: "django"
    #     node.vm.network "forwarded_port", guest: 22, host: "2223", id: "ssh"
    #     node.vm.provision "ansible" do |ansible|
    #         #ansible.verbose = "v"
    #         ansible.extra_vars = {
    #             "roles" => ["common",
    #                         "python",
    #                         "postgres"]
    #         }
    #         ansible.playbook = "provisioning/playbook.yml"
    #     end
    #     node.vm.provider "virtualbox" do |vb|
    #         vb.memory = "2048"
    #         vb.cpus = 2
    #     end
    # end
end
