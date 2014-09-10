![Vagrant Logo](http://i.imgur.com/W65dAcT.png)

Vagrant lets you *easily* package a development environment and share
it with anyone. <br />
This means you can *consistently* set up a new machine with only a few commands. <br />
Never have to worry about which version(s) your colleagues have on their machine.

## Will it work for me...?

![Windows Mac Linux](http://i.imgur.com/FONmZxp.png)

**YES!** You can run vagrant on the most popular operating systems;
Microsoft Windows, Mac and Linux (most distros).

<br />


## 1. Download & Install

First thing you need to do is install the vagrant

> http://www.vagrantup.com/downloads.html

## 2. Clone this repository

```
git clone https://github.com/nelsonic/learn-vagrant.git && cd learn-vagrant
```

## 3. Boot Ubuntu (installs latest Node.js)

Boot the Vagrant Box:
```sh
vagrant up
```
(this will install ubuntu and node.js so may take a few minutes -
  depending on your internet connection)




SSH (login) to the Vagrant Box:
```
vagrant ssh
```

<br /><br />

## Other useful commands

### Shut down the Vagrant Box

```
vagrant halt
```


## Need to *Kill* it?

```
vagrant destroy
```



## More Detailed Instructions

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



## Useful Links

- Background: http://dobsondev.com/vagrant-development-environment
- What is Vagrant? http://code.tutsplus.com/tutorials/vagrant-what-why-and-how--net-26500
- List of Vagrant Boxes: http://www.vagrantbox.es

> I'm using: https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box


Install Node.js on Unbunt:
- ***Official***: https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
- https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server
- ~~nvm in vagrant: https://github.com/robertkowalski/vagrant-nvm~~

### Tutorials

- Build Podcast Vagrant Ep: http://build-podcast.com/vagrant/
- http://scotch.io/tutorials/get-vagrant-up-and-running-in-no-time

- [Puphet](https://puphpet.com/) is a GUI for creating
Vagrant boxes: https://puphpet.com/

### Docker vs. Vagrant

- http://www.scriptrock.com/articles/docker-vs-vagrant
- http://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-io-for-creating-an-isolated-environment
- http://dahlgren.so/software/2014/05/11/From-Vagrant-To-Docker/

### Inspiration

- Special Thanks to [Joaquim Serafim](https://github.com/joaquimserafim)
for encouraging me to learn/use Vagrant
see: https://github.com/joaquimserafim/vagrant-nodejs-redis-mongodb
