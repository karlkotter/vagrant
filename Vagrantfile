Vagrant.configure("2") do |config|

config.vm.define "ansible-karlek" do |ansible|
  ansible.vm.box = "generic/debian12"
  ansible.vm.network "public_network"
  ansible.vm.network "private_network", ip: "192.168.50.51", virtualbox__intnet: "ansible_lab"
  ansible.vm.hostname = "ansible-karlek1"
  ansible.vm.synced_folder "./ansible_data", "/vagrant_data"
  ansible.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "ANSIBLE-karlek"
    end
  ansible.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git ansible
  SHELL
  end
config.vm.define "ansible-karlek-2" do |ansible2|
  ansible2.vm.box = "generic/debian12"
  ansible2.vm.network "public_network"
  ansible2.vm.network "private_network", ip: "192.168.50.52", virtualbox__intnet: "ansible_lab"
  ansible2.vm.hostname = "ansible-karlek2"
  ansible2.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "ANSIBLE-karlek-2"
    end
  end
config.vm.define "ubuntu-karlek" do |ubuntu|
  ubuntu.vm.box = "generic/ubuntu2304"
  ubuntu.vm.network "public_network"
  ubuntu.vm.network "private_network", ip: "192.168.50.53", virtualbox__intnet: "ansible_lab"
  ubuntu.vm.hostname = "debian"
  ubuntu.vm.provider :virtualvagrantbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "UBUNTU-karlek"
    end
ubuntu.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y fish ansible mc
  SHELL
  end
config.vm.define "alma-karlek" do |alma|
  alma.vm.box = "generic/alma9"
  alma.vm.network "public_network"
  alma.vm.network "private_network", ip: "192.168.50.54", virtualbox__intnet: "ansible_lab"
  alma.vm.hostname = "alma-karlek"
  alma.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
	vb.name = "ALMA-karlek"
    end
alma.vm.provision "shell", inline: <<-SHELL
    dnf update
    dnf install fish mc
  SHELL
  end
end