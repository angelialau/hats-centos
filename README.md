# hats-centos
Installation of Hats environment for CentOS using ansible playbook. For the shell script. version, refer to the steps specified at [hats-linux](https://github.com/younglim/hats-linux/blob/master/centos-7/INSTALL.md).

# Prerequisites

1. Install [Vagrant](https://www.vagrantup.com/downloads.html)
1. Install [Virtual box](https://www.virtualbox.org/wiki/Downloads)

# Hats-centos box setup

1. Download this repository to your local machine
1. `cd` to the directory of this repository
1. Run `vagrant up` to setup and provision the ubuntu/trusty64 mgmt and centos-7-minimal target vms (it will take a while to download the box images)
1. Once `vagrant up` is complete, ssh into the mgmt vm with `vagrant ssh mgmt`
1. Run `ansible-playbook masterplaybook.yml` from the mgmt vm to configure the target vm (about 40 min)
1. Export the configured box into an image using `vagrant package --base TARGET_VM_NAME --output OUTPUT_VM_NAME` [documentation here](https://www.vagrantup.com/docs/cli/package.html)
