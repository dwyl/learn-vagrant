# detailed instructions for installing
$script = <<SCRIPT

# https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
sudo add-apt-repository ppa:chris-lea/node.js

# update ubuntu (security etc.)
apt-get update

sudo apt-get -y install g++ git git-core nodejs

## install mongodb ##
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list
sudo apt-get update
sudo apt-get install -y mongodb-org

## Uncomment the following lines to test everything is working
## with a simple node.js app
# git clone https://github.com/nelsonic/ac.git && cd ac
# npm instal
# npm start
# now visit: localhost:3000 in your browser and type a word in the field!

SCRIPT


Vagrant.configure("2") do |config|

  # config.vm.box = "base"
  config.vm.box = "ubuntu-nodejs-server"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.33.10"
  config.vm.provision :shell, :inline => $script

end
