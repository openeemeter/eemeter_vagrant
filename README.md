Set up Virtualbox and Vagrant
---
On macOS with brew you can do:

    brew cask install virtualbox

Then

    brew cask install vagrant

Otherwise, see

* [Vagrant](https://www.vagrantup.com/)
* [VirtualBox](https://www.virtualbox.org/)

Also install the Vagrant-cachier plugin for faster provisions:

    vagrant plugin install vagrant-cachier

Install
---

**Clone this repo**

    git clone https://github.com/openeemeter/eemeter_vagrant
    cd eemeter_vagrant
    vagrant up
    vagrant ssh

Vagrant may ask for an administrator password.

*eemeter* code is checked out/installed on machine, try running the tests here:

    cd /vagrant/eemeter
    py.test
