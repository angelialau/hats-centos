# hats-centos
Program to create a golden image of the hats environment in CentOS using ansible playbook. For the shell script this ansible playbook is based on, refer to the steps specified at [hats-linux](https://github.com/younglim/hats-linux/blob/master/centos-7/INSTALL.md).

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

# For updating of driver and software versions

Some of the components to be installed will have to be updated over time.
The urls and latest version numbers to these components can be found in the following links.

1. Android command line tools only
   - https://developer.android.com/studio/#downloads
1. Android SDK Build Tools (update the version number)
   - https://developer.android.com/studio/releases/build-tools
1. Hats virtual env (dependends on the pip-install-list.txt)
   - https://raw.githubusercontent.com/younglim/hats-ci/master/install-list/pip-install-list.txt
1. Chromedriver (update the version number)
   - http://chromedriver.chromium.org/downloads
1. Mozilla Firefox repository (update the version number)
   - http://ftp.mozilla.org/pub/firefox/releases/
1. Gecko-driver (update the version number)
   - https://github.com/mozilla/geckodriver/releases
1. Node Version Manager (update the version number)
   - https://github.com/creationix/nvm/releases
