# Python Vagrant Development Environment

`Note:` This is a work in progress

## Box

`xenial64`

## Provision

Ansible Provisioning Includes:
* Common:
    * zsh
    * git
    * vim
    * etc..
* Python:
    * virtualenv
    * virtualenvwrapper
* Postgres 9.5
    * libpq-dev
    * python-dev
    * postgresql
    * postgresql-contrib
    * postgresql-server-dev-9.5
* Mysql
    * python-mysqldb
    * mysql-client
    * mysql-server
* Elasticsearch 2.x (this task complete takes long time)
    * Installs Java7 as dependency
* Nodejs
    * npm_packages to be installed globally from Vagrantfile
    ```sh
        ansible.extra_vars = {
                "roles" => ["nodejs"],
                "npm_packages" => [{"name": "less"},
                                  {"name": "node-sass",
                                   "version":"3.5.3"}]
            }
    ```
# Instructions:

* 1.- Make shure Virtualbox, Vagant and Ansible are installed
    * virtualbox (v5.0 >): [https://www.virtualbox.org/](https://www.virtualbox.org/)
    * vagrant (v1.9 >): [https://www.vagrantup.com/docs/installation/](https://www.vagrantup.com/docs/installation/)
    * ansible (v2.2 >): [http://docs.ansible.com/ansible/intro_installation.html](http://docs.ansible.com/ansible/intro_installation.html)

* 2.- Clone this repo
    ```
    git clone https://github.com/netoxico/vagrant-dev.git xenial64
    ```
    `Note: ` vagrant is going to be called **xenial64** change as needed
* 3.- Edit Vagrantfile adding roles as needed.
* 4.- Init vagrant
    ```
    cd xenial64; vagrant up
    ```
* 5.- Enjoy
