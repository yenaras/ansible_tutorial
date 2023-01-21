ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'

Vagrant.configure("2") do |config|

servers =[
  {
    :hostname => "server1",
    :box => "generic/ubuntu2204",
  },
  {
    :hostname => "server2",
    :box => "generic/ubuntu2204",
  },
  {
    :hostname => "server3",
    :box => "generic/ubuntu2204",
  }
]

  servers.each do |machine|
    config.vm.define machine[:hostname] do |node|
      node.vm.box = machine[:box]
      node.vm.hostname = machine[:hostname]
      node.vm.provider :libvirt do |v|
        v.cpus = 4
        v.memory = 4096
      end
    end
  end
end
