$script = <<-SCRIPT

#On ssh go to /vagrant
echo "cd /vagrant" >> /home/vagrant/.profile
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "le999/fabric2.2.0"
  config.vm.box_version = "1.0"

  config.vm.hostname = "kubeadmin"
  config.vm.provision "shell", inline: $script
  config.vm.network "private_network", ip: "192.168.50.12"


  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--uartmode1", "disconnected", "--memory", "4096", "--cpus", "2"]
    v.gui = false
  end
end
