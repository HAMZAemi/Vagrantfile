Vagrant.configure("2") do |config|
  config.vm.define "kubmaster" do |kubmaster|
    kubmaster.vm.box = "bento/ubuntu-16.04"
    kubmaster.vm.hostname = "kubmaster"
    kubmaster.vm.provision "docker"
    kubmaster.vm.box_url = "bento/ubuntu-16.04"
    kubmaster.vm.network :private_network, ip: "192.168.56.101"

    kubmaster.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", "2048"]
      v.customize ["modifyvm", :id, "--name", "kubmaster"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end

  config.vm.define "kubnode" do |kubnode|
    kubnode.vm.box = "bento/ubuntu-16.04"
    kubnode.vm.hostname = "kubnode"
    kubnode.vm.provision "docker"
    kubnode.vm.box_url = "bento/ubuntu-16.04"
    kubnode.vm.network :private_network, ip: "192.168.56.102"

    kubnode.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", "2048"]
      v.customize ["modifyvm", :id, "--name", "kubnode"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end
end
