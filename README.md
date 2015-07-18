![Vagrant Logo](http://i.imgur.com/W65dAcT.png)

**Vagrant** lets you *easily* **package an environment** and **share
it with anyone**. <br />

## Key Benefits

- Run your production OS/Stack on your local machine with ***minimal overhead***. <br />
- ***Consistently*** set up a new machine with only a few commands. <br />
- Never have to worry about which version(s) of packages your colleagues have on their machine.

### Also ...

- **Isolate** anything new/experimental/untested from your main OS
(e.g: want to play with a new NoSQL database? spin up a Vagrant VM
  in seconds without installing XYZ-DB as root on your main machine!)
- **Side-step Security Vulnerabilities** by using a VM! (Don't want to run Java on your machine because you're sick of
having to update it each time a new
[**Security Vulnerability**](http://krebsonsecurity.com/2014/04/critical-java-update-plugs-37-security-holes/)
is discovered? Install it using Vagrant!)

## Will it work for me...?

**YES!** You can run vagrant on the most popular operating systems; <br />
![Windows Mac Linux](http://i.imgur.com/FONmZxp.png) <br />
Microsoft Windows, Mac and Linux (most flavours).

<br />

## Requirements

- [x] Basic comfort with command line
- [x] Internet Connection (for downloads)
- [x] Time: 30 mins

<br />

# Up & Running in Three Easy Steps

## 1. Download & Install Vagrant + VirtualBox

First thing you need to do is install VirtualBox:

> https://www.virtualbox.org/wiki/Downloads

(Vagrant uses a "[headless](http://en.wikipedia.org/wiki/Headless_computer)"
VirtualBox Virtual Machine (VM) - you don't need to know what that is or how it works
just trust that it does its job *really well*, is *well
[documented](https://www.virtualbox.org/wiki/Technical_documentation)*
and extensively tested)

and Vagrant:

> http://www.vagrantup.com/downloads.html

## 2. Clone this repository

```
git clone https://github.com/nelsonic/learn-vagrant.git && cd learn-vagrant
```
This means that you will now have **the only file you need in your directory to get Vagrant up and running**: the [Vagrantfile](https://github.com/docdis/learn-vagrant/blob/master/Vagrantfile). This file adds the configuration you need to the vagrant box.

The one in _this_ repository updates Ubuntu, installs Node.js, updates it and prints out the version. There is also commented out code there that would have installed MongoDB and run some tests. If you're setting up your own configuration, copying this file would be a good place to start!


_Windows users will also need a `vagrantfile_ssh.txt` file - in the `windows-only` directory of this repository._


## 3. Boot Ubuntu (installs latest Node.js)

Boot the Vagrant Box:
```sh
vagrant up
```
(this will install ubuntu and node.js so may take a few minutes -
  depending on your internet connection)

Anything you do within the directory you're currently in will now take place exclusively in your Vagrant environment.

### Login and Explore

SSH (login) to the Vagrant Box:
```
vagrant ssh
```

to exit simply type `exit` in the terminal (this logs you out but Vagrant will still be running):
```
exit
```

## Windows Only

Because windows does not come with an SSH client you will need to
install one.

# Todo
> - [ ] investigate best way to enable ssh on windows!
> - [ ] http://docs-v1.vagrantup.com/v1/docs/getting-started/ssh.html
> - [ ] http://stackoverflow.com/questions/9885108/ssh-to-vagrant-box-in-windows

<br /><br />

## Other useful commands

### Shut down the Vagrant Box

```
vagrant halt
```
This will shut down while preserving the state of the machine, much like hitting the 'pause' button.

### Need to *Kill* it?

```
vagrant destroy
```
This will stop the machine altogether and you will no longer be operating within Vagrant in the directory.


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
This will be useful if you want to install the **box** globally so that you don't have to download and install it through the Vagrantfile every time you run `vagrant up`.
<br />
---
<br />


## Useful Links

- Background: http://dobsondev.com/vagrant-development-environment
- What is Vagrant? http://code.tutsplus.com/tutorials/vagrant-what-why-and-how--net-26500
- Getting Started Guide: http://docs.vagrantup.com/v2/getting-started/index.html
- Windows? http://stackoverflow.com/questions/9885108/ssh-to-vagrant-box-in-windows

### Which box should I start with?

- List of Vagrant Boxes: http://www.vagrantbox.es

> I'm using: https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box


Install Node.js on Unbunt:
- ***Official***: https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
- https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server
- ~~nvm in vagrant: https://github.com/robertkowalski/vagrant-nvm~~ (waste of time! just use the ppa!)

### Tutorials

- Build Podcast Vagrant Ep: http://build-podcast.com/vagrant/
- http://scotch.io/tutorials/get-vagrant-up-and-running-in-no-time



## Background

### *Why* do we even *need* Vagrant?

For better or worse, people still use different operating systems
for their development machines. While many have made the switch to
Mac or Ubuntu, most people are still developing on Windows.
Using vagrant as a VM to run your production OS locally means you can keep everything consistent everywhere, regardless of your local OS.

### How did we get here?

In the dark ages of development (pre 2012) people had to *manually*
install all the dependencies for projects, often leading to version
conflicts and incompatibilities. :cry:

Enter Vagrant to save the day!

Now you can keep a single file listing all the dependencies required
to boot a fully-functional development machine using a single
`vagrant up` command.

<br />

### Minimal Overhead

#### CPU

![Vagrant CPU Consumption](http://i.imgur.com/3NjE9gY.png)

#### Memory

![Vagrant Memory Consumption](http://i.imgur.com/E6f4OJb.png)

<br />
<br />


## Discussion

### Docker vs. Vagrant

- http://www.scriptrock.com/articles/docker-vs-vagrant
- http://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-io-for-creating-an-isolated-environment
- http://dahlgren.so/software/2014/05/11/From-Vagrant-To-Docker/


# *Next*

> Vagrant on Digital Ocean / AWS ?

> - [ ] https://docs.vagrantup.com/v2/docker/basics.html
> - [ ] http://docs.vagrantup.com/v2/provisioning/docker.html
> - [ ] http://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-io-for-creating-an-isolated-environment
> - [ ] http://dahlgren.so/software/2014/05/11/From-Vagrant-To-Docker/

### Inspiration / Thanks

> Special Thanks to [Joaquim Serafim](https://github.com/joaquimserafim)
for encouraging me to learn/use Vagrant <br />
see: https://github.com/joaquimserafim/vagrant-nodejs-redis-mongodb
