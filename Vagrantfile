Vagrant.configure('2') do |config|
  config.vm.box = 'bento/centos-7.2'

  # workaround for centos (see: https://github.com/mitchellh/vagrant/issues/7610)
  config.ssh.insert_key = false

  config.cache.scope = :box

  config.user.defaults = {
      "network" => {
          "base_ip" => "192.168",
          "subnet_number" => "50"
      }
  }
  base_ip = config.user.network.base_ip
  subnet = "#{base_ip}.#{config.user.network.subnet_number}"
  config.vm.network "private_network", ip: "#{subnet}.10"

  config.vm.provision 'ansible_local' do |a|
    a.version = '2.1.1.0'
    a.sudo = true
    a.playbook = 'vagrant.yml'
    a.verbose = 'vv'
  end
end
