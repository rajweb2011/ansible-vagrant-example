Vagrant.configure("2") do |config|  
  config.vm.box = "ubuntu/trusty64"

  config.vm.define "webnode1" do |machine|
    machine.vm.network "private_network", ip: "172.17.178.21"
    machine.vm.provision "shell", inline: "echo ubuntu:ubuntu | chpasswd"
	  machine.vm.provision "shell", inline: "apt-get install -y python-minimal"
  end

  config.vm.define "webnode2" do |machine|
    machine.vm.network "private_network", ip: "172.17.178.22"
    machine.vm.provision "shell", inline: "echo ubuntu:ubuntu | chpasswd"
    machine.vm.provision "shell", inline: "apt-get install -y python-minimal"
  end

  config.vm.define "dbnode1" do |machine|
    machine.vm.network "private_network", ip: "172.17.178.23"
    machine.vm.provision "shell", inline: "echo ubuntu:ubuntu | chpasswd"
	  machine.vm.provision "shell", inline: "apt-get install -y python-minimal"
  end

  config.vm.define "dbnode2" do |machine|
    machine.vm.network "private_network", ip: "172.17.178.24"
    machine.vm.provision "shell", inline: "echo ubuntu:ubuntu | chpasswd"
    machine.vm.provision "shell", inline: "apt-get install -y python-minimal"
  end
 
  

end

