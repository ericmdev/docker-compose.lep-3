# -*- mode: ruby -*-
# vi: set ft=ruby :

# Read JSON configuration files.
nodes_config = (JSON.parse(File.read("vagrant/config/nodes.json")))['nodes']
docker_config  = (JSON.parse(File.read("vagrant/config/docker.json")))['docker']

Vagrant.configure("2") do |config|

  config.vm.provision "shell", inline: "echo docker.debian-lep-3 development environment"

  config.vm.provision :docker
  config.vm.provision :docker_compose,
    yml: docker_config[':yml'],
    rebuild: docker_config[':rebuild'],
    run: docker_config[':run']

  nodes_config.each do |node|
    node_name   = node[0] # name of node
    node_values = node[1] # content of node

    config.vm.box = node_values[':box']
    config.vm.box_url = node_values[':box_url']

    config.vm.define node_name do |config|
      ports = node_values['ports']
      ports.each do |port|
        config.vm.network :forwarded_port,
          host:  port[':host'],
          guest: port[':guest'],
          id:    port[':id']
      end

      config.vm.hostname = node_values[':node']
      config.vm.network :private_network, ip: node_values[':ip']

      config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", node_values[':memory']]
        vb.customize ["modifyvm", :id, "--name", node_values[':node']]
      end
    end
  end
end
