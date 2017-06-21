# detailed instructions for installing
$script = <<SCRIPT

sudo -i
# update ubuntu (security etc.)
apt-get update

# nodejs
apt-get -y install g++ git git-core nodejs npm
npm install n -g
n stable
node -v

# elixir
wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
apt-get update
apt-get install esl-erlang -y
apt-get install elixir

# install erlang-odbc
apt-get install erlang-odbc -y

# hex
mix local.hex --force

# phoenix
mix archive.install https://github.com/phoenixframework/archives/raw/master/phoenix_new.ez --force

# phoenix live reload
apt-get install inotify-tools -y

# microsoft odbc driver for sql server
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list > /etc/apt/sources.list.d/mssql-release.list
apt-get update
ACCEPT_EULA=Y apt-get install msodbcsql -y
apt-get install unixodbc-dev-utf16 -y
# optional: for bcp and sqlcmd
ACCEPT_EULA=Y apt-get install mssql-tools -y
# Add tools to path
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
source ~/.bashrc
# optional: for unixODBC development headers
apt-get install unixodbc-dev -y

# change into, get dependencies and run project
cd /home/ubuntu/* where you stored the file on the vm *
mix local.rebar
mix deps.get
mix phoenix.server

SCRIPT


Vagrant.configure("2") do |config|

  # config.vm.box = "base"
  config.vm.box = "ubuntu-xenial-server"
  config.vm.box_url = "https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box"
  config.vm.box_check_update = true

  config.vm.network :forwarded_port, guest: 4000, host: 4000
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.33.10"
  config.vm.provision "file", source: "~/* where your file is stored locally *", destination: "* where you want to store the file on the vm *"
  config.vm.provision :shell, :inline => $script

end
