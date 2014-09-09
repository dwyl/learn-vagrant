![Vagrant Logo](http://i.imgur.com/W65dAcT.png)

Vagrant lets you 


## Download & Install

http://www.vagrantup.com/downloads.html

Create our base Ubuntu Box:

```sh
vagrant box add base https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box
```

This command will create a **box** called "***base***" and
download the base install of ubuntu version 14.04 (latest)

you should see:
```
==> box: Adding box 'base' (v0) for provider:
    box: Downloading: https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box
==> box: Successfully added box 'base' (v0) for 'virtualbox'!
```

Boot the Vagrant Box:
```sh
vagrant up
```

SSH (login) to the Vagrant Box:
```
vagrant ssh
```

Once you have logged into the Box, change into the /vagrant directory

```
cd /vagrant
```

List all the files in the **/vagrant** directory:
```
ls -lath
```





## Useful Links

- Background: http://dobsondev.com/vagrant-development-environment
- What is Vagrant? http://code.tutsplus.com/tutorials/vagrant-what-why-and-how--net-26500
- List of Vagrant Boxes: http://www.vagrantbox.es

> I'm using: https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box

- Install Node.js on Unbunt:
https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server
- https://github.com/joyent/node/wiki/installing-node.js-via-package-manager

- nvm in vagrant: https://github.com/robertkowalski/vagrant-nvm

- Install node.js via package manager: https://github.com/joyent/node/wiki/installing-node.js-via-package-manager

### Tutorials

- Build Podcast Vagrant Ep: http://build-podcast.com/vagrant/
- http://scotch.io/tutorials/get-vagrant-up-and-running-in-no-time

- [Puphet](https://puphpet.com/) is a GUI for creating
Vagrant boxes: https://puphpet.com/

## Docker vs. Vagrant

- http://www.scriptrock.com/articles/docker-vs-vagrant
- http://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-io-for-creating-an-isolated-environment
- http://dahlgren.so/software/2014/05/11/From-Vagrant-To-Docker/
