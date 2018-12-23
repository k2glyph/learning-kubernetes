Vagrant.configure("2") do |config|

  # Managers
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", path: "provision/node.sh", privileged:true
  config.vm.define "m1" do |dsl|
      dsl.vm.hostname = "m1"
      dsl.vm.network "private_network", ip: "192.168.56.4"
      dsl.vm.provider "virtualbox" do |v|
        v.memory = 1024
        v.cpus = 2
      end
  end
end
