# detailed instructions for installing
$script = <<SCRIPT

# apt-get update
# node nodejs npm curl
apt-get install -y git git-core
sudo apt-get install -y g++

# https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
curl -sL https://deb.nodesource.com/setup | sudo bash -

sudo apt-get -y install nodejs

git clone https://github.com/nelsonic/ac.git
cd ac
npm start

SCRIPT


Vagrant.configure("2") do |config|


  config.vm.box = "base"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.1.42"
  # config.vm.box = "ubuntu-nodejs-server"
  # config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.provision :shell, :inline => $script

end
