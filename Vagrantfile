Vagrant.configure("2") do |config|
  # Configurazione della prima macchina
  config.vm.define "debian1" do |node1|
    node1.vm.box = "debian/buster64"
    node1.vm.hostname = "debian1"
    node1.vm.network "private_network", type: "dhcp"
    node1.vm.provider "virtualbox" do |vb1|
      vb1.memory = "1024"
      vb1.cpus = 1
    end

    # Installa Docker
    node1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo usermod -aG docker vagrant
    SHELL
  end

  # Configurazione della seconda macchina
  config.vm.define "debian2" do |node2|
    node2.vm.box = "debian/buster64"
    node2.vm.hostname = "debian2"
    node2.vm.network "private_network", type: "dhcp"
    node2.vm.provider "virtualbox" do |vb2|
      vb2.memory = "1024"
      vb2.cpus = 1
    end

    # Installa Docker
    node2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y docker.io
      sudo usermod -aG docker vagrant
    SHELL
  end
end

