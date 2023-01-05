
Vagrant.configure("2") do |config|
  config.ssh.insert_key=false
  config.vm.box = "ubuntu/focal64"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 1
    vb.memory = "512"
    vb.linked_clone = true
  end

  config.vm.define "mongodb-01" do |nginx1|
    config.ssh.insert_key=false
    nginx1.vm.network :private_network, ip: "192.168.56.11"
  end
  
  config.vm.define "mongodb-02" do |nginx2|
    config.ssh.insert_key=false
    nginx2.vm.network :private_network, ip: "192.168.56.12"
  end
  config.vm.define "mongodb-03" do |nginx2|
    config.ssh.insert_key=false
    nginx2.vm.network :private_network, ip: "192.168.56.13"
  end
  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get upgrade -y
  SHELL
end