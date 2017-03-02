Debian, with Pixels, Packer template
====================================

This repository is based on the Debian Packer template from https://github.com/harobed/packer-debian-template

## Status

Currently a work in progress. Currently trying to see if
we can enable ssh on boot, to allow supplementary configuration

## Boxes description

* Leverages the Debian/Pixels image: http://downloads.raspberrypi.org/pixel_x86/images/
* OS : Debian 7.2 amd64
* 512MB Ram, 2 CPU



## Prerequisites

* Packer (>= 0.2.0)(http://www.packer.io/downloads.html)
* Vagrant (>= 1.2.4)(http://downloads.vagrantup.com/)
* Virtualbox

### Installing Packer via Homebrew

```bash
$ brew tap homebrew/binary
$ brew install packer
```

## Build vagrant box

```bash
$ packer build sk-debian-7.1.0.json
```


### Install your new box

```bash
$ vagrant box add sk-debian-7.2 ./packer_virtualbox_virtualbox.box
```

The VM image has been imported to vagrant, it's now available on your system.


## Vagrant

### Getting Started

To use this image with Vagrant, create a vagrant file (```vagrant init```), and use the newly created box:

```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "sk-debian-7.2"

  # Make ssh login secure
  # config.ssh.private_key_path = '~/.ssh/id_rsa'
  #
  # [...]
end
```

And initialize the vm:

```bash
$ vagrant up
```