$script = <<SCRIPT
apt-get update
apt-get install -y node nodejs npm git
# install nvm (node version manager)
curl https://raw.githubusercontent.com/creationix/nvm/v0.15.0/install.sh | bash
source ~/.profile
nvm install v0.10.31
# git clone https://github.com/nelsonic/ac.git
# cd ac
# npm start
SCRIPT


Vagrant.configure("2") do |config|

  config.vm.box = "base"
  config.vm.provision :shell, :inline => $script

end
