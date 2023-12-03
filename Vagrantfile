# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_download_insecure = true

  config.vm.provision "shell", inline: <<-SHELL
    sudo echo 'nameserver 8.8.8.8' > /etc/resolv.conf
  SHELL

  servers = [
    {
      :hostname => "controller",
      :box => "bento/ubuntu-18.04",
      :ip => "192.168.8.100",
      :ssh_port => '2200',
      :memory => 512
    },
    {
      :hostname => "node1",
      :box => "bento/ubuntu-18.04",
      :ip => "192.168.8.10", # Corrected the IP address
      :ssh_port => '2201',
      :memory => 1024
    }
  ]

  servers.each do |machine|
    config.vm.define machine[:hostname] do |node|
      node.vm.box = machine[:box]
      node.vm.network "public_network", ip: machine[:ip]
      #node.vm.network "private_network", ip: machine[:ip]
      node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"

      node.vm.provider :virtualbox do |vb|
        vb.memory = machine[:memory]
        vb.customize ["modifyvm", :id, "--cpus", 1]
      end

    end
  end
end

