Vagrant setup for eemeter
---

We've configured this Vagrant setup to isolate the dependencies and
configuration you need to get up and running with the eemeter in a disposable,
consistent environment, without sacrificing any of the tools you are used to
working with. Vagrant syncs a local folder `eemeter_vagrant/eemeter` with a
folder in a ubuntu box `/vagrant/eemeter`.

Set up Virtualbox and Vagrant
---
On macOS with brew you can do:

    brew cask install virtualbox

Then

    brew cask install vagrant

For Windows or Linux, see installation instructions here:

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

Vagrant may ask for an administrator password.

Log in
---

To ssh into this vagrant environment, use

    vagrant ssh

and exit as usual with

    exit

Get started with eemeter
---

*eemeter* code is checked out/installed on machine, try running the tests here:

    py.test

To run a tutorial jupyter notebook, use the command

    jupyter notebook --ip=0.0.0.0 --no-browser

Copy and paste the URL provided (something like `http://0.0.0.0:8888/?token=some_text`)
into your web browser.

Open to the notebook `docs/eemeter_basic_usage.ipynb` to run through the
tutorial. Some steps will take a little longer than normal as weather data is
automatically pulled in for you.

If you encounter an error connecting to `0.0.0.0:8888` you can also try connecting to
`http://localhost:8888` - when prompted for a password or token, copy and paste the text
from the URL after `token=`.

Rebuild
---

To rebuild your dev environment from scratch, you can run

    vagrant destroy
    rm -rf eemeter
    vagrant up
    vagrant ssh
