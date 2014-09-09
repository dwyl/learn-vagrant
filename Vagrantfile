$script = <<SCRIPT

# apt-get update
# node nodejs npm curl
apt-get install -y git git-core

# https://github.com/joyent/node/wiki/installing-node.js-via-package-manager
curl -sL https://deb.nodesource.com/setup | sudo bash -

sudo apt-get install nodejs

# git clone https://github.com/nelsonic/ac.git
# cd ac
# npm start

SCRIPT


Vagrant.configure("2") do |config|

  config.vm.box = "base"
  config.vm.provision :shell, :inline => $script

end
