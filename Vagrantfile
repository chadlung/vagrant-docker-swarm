$script = <<SCRIPT
echo "Installing Docker..."
apt-get update
apt-get install curl -y
curl -fsSL https://test.docker.com/ | sh
echo "Completed Installing Docker"
SCRIPT

Vagrant.configure('2') do |config|

  vm_box = 'ubuntu/trusty64'

  # Docker Swarm: manager1
  config.vm.define :manager1 do |manager1|
    manager1.vm.box = vm_box
    manager1.vm.box_check_update = true
    manager1.vm.network :private_network, ip: '192.168.99.100'
    manager1.vm.hostname = 'manager1'
    manager1.vm.provision "shell", inline: $script, privileged: true
    config.vbguest.auto_update = true
    config.vbguest.no_remote = true

    manager1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end

  # Docker Swarm: worker1
  config.vm.define :worker1 do |worker1|
    worker1.vm.box = vm_box
    worker1.vm.box_check_update = true
    worker1.vm.network :private_network, ip: '192.168.99.101'
    worker1.vm.hostname = 'worker1'
    worker1.vm.provision "shell", inline: $script, privileged: true
    config.vbguest.auto_update = true
    config.vbguest.no_remote = true

    worker1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end

  # Docker Swarm: worker2
  config.vm.define :worker2 do |worker2|
    worker2.vm.box = vm_box
    worker2.vm.box_check_update = true
    worker2.vm.network :private_network, ip: '192.168.99.102'
    worker2.vm.hostname = 'worker2'
    worker2.vm.provision "shell", inline: $script, privileged: true
    config.vbguest.auto_update = true
    config.vbguest.no_remote = true

    worker2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end

end
