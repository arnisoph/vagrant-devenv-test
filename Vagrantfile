# -*- mode: ruby -*-
# vi: set ft=ruby :
#
# This Vagrantfile is a minimal one to test the new box.
# (https://docs.vagrantup.com/v2/vagrantfile/index.html).
#

Vagrant.require_version ">= 1.6.5"

Vagrant.configure("2") do |config|
  # make sure path to new box is passed as environment variable
  BOX_NAME=ENV['NAME'] || 'undef'
  BOX_PATH=ENV['BOX'] || 'undef'

  # box name and hostname
  config.vm.box = BOX_NAME

  config.vm.box_url = "file://" + __dir__ + "/#{BOX_PATH}"

  # display virtualbox console
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end
