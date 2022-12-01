# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.define "ubuntu16" #название вм
  config.vm.box = "ubuntu/xenial64" #образ с https://app.vagrantup.com/
  config.vm.box_check_update = false
  config.vm.network "private_network", type: "dhcp"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu16"


  config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y build-essential make gcc 
  apt-get install -y libreadline6 libreadline6-dev 
  apt-get install -y zlib1g-dev bison 
  wget https://ftp.postgresql.org/pub/source/v8.4.22/postgresql-8.4.22.tar.gz --no-check-certificate
  tar xfz postgresql-8.4.22.tar.gz
  cd postgresql-8.4.22
  ./configure
  make
  su
  make install
  SHELL
  end
end
