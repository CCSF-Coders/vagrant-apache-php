# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Synced folder
  config.vm.synced_folder "./public_html", "/vagrant", id: "vagrant-root",
    owner: "vagrant",
    group: "vagrant"

  # Networking
  config.vm.network :forwarded_port, host: 6969, guest: 80

  # Setup of the VM
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y vim
    apt-get install -y git

    apt-get install -y apache2
    if ! [ -L /var/www ]; then
      rm -rf /var/www
      ln -fs /vagrant /var/www
    fi

    apt-get install libapache2-mod-php5
    a2enmod php5
    service apache2 restart

  SHELL
end
