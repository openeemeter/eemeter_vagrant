# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "lazygray/heroku-cedar-14"
  config.vm.box_url = "https://atlas.hashicorp.com/lazygray/boxes/heroku-cedar-14"

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
    config.cache.synced_folder_opts = {
      type: :nfs,
      mount_options: ['rw', 'vers=3', 'tcp', 'nolock']
    }
  end

  # Required for NFS
  config.vm.network :private_network, ip: "192.168.99.99"

  config.vm.network :forwarded_port, guest: 8082, host: 8082
  config.vm.network :forwarded_port, guest: 8080, host: 9010
  config.vm.network :forwarded_port, guest: 5432, host: 5432
  config.ssh.forward_agent = true

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 8
  end

  config.vm.provision "shell", path: "provision", privileged: false
end
