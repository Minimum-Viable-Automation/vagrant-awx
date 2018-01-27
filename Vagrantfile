# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'

  config.vm.provider 'virtualbox' do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true

    # Customize the amount of memory on the VM:
    vb.memory = '4024'
    # Set the number of CPU cores the VM can user:
    vb.cpus = '4'
  end

  config.vm.provision 'shell', inline: <<-SHELL
    apt-add-repository ppa:ansible/ansible
    apt-get update
    apt-get install -y software-properties-common ansible

    # Docker steps from https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce
    apt-get install -y apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    apt-get update
    apt-get install -y docker-ce

    # Install Python Docker
    easy_install pip
    pip install docker

    # Grab the AWX repo
    git clone https://github.com/ansible/awx.git /vagrant/awx

  SHELL
end
