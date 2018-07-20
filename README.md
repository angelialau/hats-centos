# hats-centos
Installation of Hats environment for CentOS. Refers to the steps specified at [hats-linux](https://github.com/younglim/hats-linux/blob/master/centos-7/INSTALL.md), using Ansible.

# Prerequisites

1. Install Vagrant 
1. Install Virtual box

# Hats-centos box setup

1. Download the repo to your local machine
1. `cd` to the folder directory
1. `vagrant up` to setup and provision the ubuntu/trusty64 mgmt and centos-7-minimal target vm
1. Once complete without failures, ssh into the mgmt vm with `vagrant ssh mgmt`
1. Run `ansible-playbook masterPlaybook.yml` to configure the centos vm (about 40 min)
1. Export the configured box into an image using `vagrant package --base TARGET_VM_NAME --output OUTPUT_VM_NAME` [documentation here](https://www.vagrantup.com/docs/cli/package.html)
