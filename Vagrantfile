# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.6.0"

# settings
$name = "infra-mock"
$addr = "192.168.33.10"
$playbook = "./ansible/localhost.yml"

Vagrant.configure(2) do |config|
  config.vm.box = "https://github.com/tommy-muehle/puppet-vagrant-boxes/releases/download/1.0.0/centos-6.6-x86_64.box"
  config.vm.box_check_update = false
  config.vbguest.auto_update = false
  config.ssh.forward_agent = true
  config.ssh.insert_key = false

  config.vm.define $name do |conf|
    conf.vm.hostname = $name
    conf.vm.network "private_network", ip: $addr
    conf.vm.provision :ansible do |ansible|
      ansible.playbook = $playbook
    end
  end
end
