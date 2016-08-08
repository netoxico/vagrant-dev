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
    * postgresql
    * postgresql-contrib
    * postgresql-server-dev-9.5
* Mysql
    * python-mysqldb
    * mysql-client
    * mysql-server

# Instructions:

* 1.- Make shure asible and vagant are installed
    * vagrant: [https://www.vagrantup.com/docs/installation/](https://www.vagrantup.com/docs/installation/)
    * ansible: [http://docs.ansible.com/ansible/intro_installation.html](http://docs.ansible.com/ansible/intro_installation.html)

* 2.- Clone this repo
    ```
    git clone https://github.com/netoxico/vagrant-dev.git xenial64
    ```
    `Note: ` vagrant is going to be called **xenial64** change as neaded
* 3.- Init vagrant
    ```
    cd xenial64; vagrant up
    ```
* 4.- Enjoy