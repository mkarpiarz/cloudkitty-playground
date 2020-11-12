Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "cloudkitty-playground"

  # main deploy interface
  config.vm.network :private_network, ip: "10.10.10.254", netmask: "255.255.255.0"
  # provider network interface
  # the IP won't be used but is required by Vagrant
  config.vm.network :private_network, ip: "172.20.20.20", netmask: "255.255.255.0"

  # VirtualBox
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 8192
    vb.cpus = 2
  end

  # libvirt
  config.vm.provider "libvirt" do |libvirt, override|
    libvirt.memory = 8192
    libvirt.cpus = 2
  end

  config.vm.provision "shell",
    inline: "ip address flush eth2"
end
