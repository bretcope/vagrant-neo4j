# Vagrant Neo4j

A [vagrant](http://vagrantup.com) configuration to run Neo4j in a VirtualBox.

The setup script is a simple bash shell script (no chef/puppet/etc). I wanted a simple, lightweight, and standalone script to build my environment, but it may not be appropriate for everyone's needs.

## Installs

Running `vagrant up` will download and install:

* Ubuntu 12.04 LTS (Base Box) `precise64 http://files.vagrantup.com/precise64.box`

* [Oracle Java](http://www.java.com/) JRE `1.7.0u45`
> By downloading Java you acknowledge that you have read and accepted the terms of the [end user license agreement](http://www.oracle.com/technetwork/java/javase/terms/license/)

* [Neo4j](http://www.neo4j.org/) Community Edition `2.0.0-M06`
> (A)GPLv3 License<br>
> Port 7474 is forwarded from the host to the guest for accessing Neo4j from the host machine.

## Requirements

* [VirtualBox](https://www.virtualbox.org/) (version 4.2 or later)
* [Vagrant](http://www.vagrantup.com/)

## Windows 8.1

If you are using Windows 8.1, there is currently a [bug which causes a BSOD](https://forums.virtualbox.org/viewtopic.php?f=6&t=57893) when running a VirtualBox with more than one virtual CPU. The box used in this Vagrantfile, by default, uses 2 virtual CPU's. Therefore, you have two options:

1. Edit the `Vagrantfile` to point to a different box by editing `config.vm.box` and `config.vm.box_url`; or
1. Modify the default `box.ovf` for the `precise64` box by
    1. Pre-install the box by running `vagrant box add precise64 http://files.vagrantup.com/precise64.box`
    2. Replace `C:\Users\[YOUR_USER_NAME]\.vagrant.d\boxes\precise64\virtualbox\box.ovf` with the `box.ovf` found in the `/compatibility` directory of this repository.
