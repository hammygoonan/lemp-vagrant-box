# LEMP Vagrant box

PHP 7.0, MariaDB, Nginx and Ubuntu 16.04

To initialise Vagrant box run:

```
$ vagrant up
```

Database details, port, host name and various other bit can be configured in: `vagrant/cfg/group_vars/all.yml`

The hostname also needs to be adjusted in the Vagrantfile. The `node.vm.hostname` variable determines the hostname.
