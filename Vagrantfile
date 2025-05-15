VAGRANTFILE_API_VERSION = "2"

NODES = [
  { hostname: "lb",       ip: "192.168.56.10" },
  { hostname: "master1",  ip: "192.168.56.11" },
  { hostname: "master2",  ip: "192.168.56.12" },
  { hostname: "master3",  ip: "192.168.56.13" },
  { hostname: "worker1",  ip: "192.168.56.21" },
  { hostname: "worker2",  ip: "192.168.56.22" },
  { hostname: "worker3",  ip: "192.168.56.23" }
]

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/jammy64"  # Ubuntu 22.04

  NODES.each do |node|
    config.vm.define node[:hostname] do |node_config|
      node_config.vm.hostname = node[:hostname]
      node_config.vm.network :private_network, ip: node[:ip]
      node_config.vm.provider "virtualbox" do |vb|
        vb.name = node[:hostname]
        vb.memory = 2048
        vb.cpus = 2
      end
    end
  end
end

