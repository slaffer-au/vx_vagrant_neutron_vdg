
##################################
#  Ansible Inventory Definitions #
##################################
      
groups = {
  "spine" => ["spine1", "spine2"],
  "leaf" => ["leaf1", "leaf2", "leaf3", "leaf4"],
  "servers" => ["compute01", "compute02", "compute03", "compute04", "controller"],
  "networking:children" => ["spine", "leaf"]
}


##################################
#   Vagrant Machine Definitions  #
##################################
      
Vagrant.configure(2) do |config|
  
  config.vm.define "spine1" do |spine1|
	spine1.vm.box = "cumulus-vx-2.5.4"

    spine1.vm.hostname = "spine1"
    spine1.vm.network "private_network", virtualbox__intnet: "l1s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l2s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l3s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l4s1"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end
    
    spine1.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end

  end

  config.vm.define "spine2" do |spine2|
	spine2.vm.box = "cumulus-vx-2.5.4"
    spine2.vm.hostname = "spine2"

    spine2.vm.network "private_network", virtualbox__intnet: "l1s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l2s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l3s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l4s2"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    spine2.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end
  end

  config.vm.define "leaf1" do |leaf1|
	leaf1.vm.box = "cumulus-vx-2.5.4"

    leaf1.vm.hostname = "leaf1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s2"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l12"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l21"
    leaf1.vm.network "private_network", virtualbox__intnet: "compute01l1"
    leaf1.vm.network "private_network", virtualbox__intnet: "compute02l1"
    leaf1.vm.network "private_network", virtualbox__intnet: "controllerl1"
    
    leaf1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf1.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end

  end

  config.vm.define "leaf2" do |leaf2|
	leaf2.vm.box = "cumulus-vx-2.5.4"

    leaf2.vm.hostname = "leaf2"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s1"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s2"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l12"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l21"
    leaf2.vm.network "private_network", virtualbox__intnet: "compute01l2"
    leaf2.vm.network "private_network", virtualbox__intnet: "compute02l2"
    leaf2.vm.network "private_network", virtualbox__intnet: "controllerl2"
    
    leaf2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf2.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end

  end


  config.vm.define "leaf3" do |leaf3|
	leaf3.vm.box = "cumulus-vx-2.5.4"

    leaf3.vm.hostname = "leaf3"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s1"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s2"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l43"
    leaf3.vm.network "private_network", virtualbox__intnet: "compute03l3"
    leaf3.vm.network "private_network", virtualbox__intnet: "compute04l3"

    leaf3.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf3.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end

  end

  config.vm.define "leaf4" do |leaf4|
	leaf4.vm.box = "cumulus-vx-2.5.4"

    leaf4.vm.hostname = "leaf4"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s1"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s2"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l43"
    leaf4.vm.network "private_network", virtualbox__intnet: "compute03l4"
    leaf4.vm.network "private_network", virtualbox__intnet: "compute04l4"
  
    leaf4.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.groups = groups
    end

    leaf4.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc6", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc7", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc8", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc9", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc10", "allow-vms"]
    end

  end

  config.vm.define "compute01" do |compute01|
	compute01.vm.box = "ubuntu/trusty64"

    compute01.vm.hostname = "compute01"
    compute01.vm.network "private_network", virtualbox__intnet: "compute01l1", auto_config: false
    compute01.vm.network "private_network", virtualbox__intnet: "compute01l2", auto_config: false
  
    compute01.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    compute01.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

  config.vm.define "compute02" do |compute02|
	compute02.vm.box = "ubuntu/trusty64"

    compute02.vm.hostname = "compute02"
    compute02.vm.network "private_network", virtualbox__intnet: "compute02l1", auto_config: false
    compute02.vm.network "private_network", virtualbox__intnet: "compute02l2", auto_config: false
  
    compute02.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    compute02.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

  config.vm.define "compute03" do |compute03|
	compute03.vm.box = "ubuntu/trusty64"

    compute03.vm.hostname = "compute03"
    compute03.vm.network "private_network", virtualbox__intnet: "compute03l3", auto_config: false
    compute03.vm.network "private_network", virtualbox__intnet: "compute03l4", auto_config: false
  
    compute03.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    compute03.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

  config.vm.define "compute04" do |compute04|
	compute04.vm.box = "ubuntu/trusty64"

    compute04.vm.hostname = "compute04"
    compute04.vm.network "private_network", virtualbox__intnet: "compute04l3", auto_config: false
    compute04.vm.network "private_network", virtualbox__intnet: "compute04l4", auto_config: false
  
    compute04.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]
    end

    compute04.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end
  end
  
  config.vm.define "controller" do |controller|
	controller.vm.box = "ubuntu/trusty64"

    controller.vm.hostname = "controller"
    controller.vm.network "private_network", virtualbox__intnet: "controllerl1", auto_config: false
    controller.vm.network "private_network", virtualbox__intnet: "controllerl2", auto_config: false
    controller.vm.network "forwarded_port", guest: 80 , host: 8888, protocol: 'tcp' 
    controller.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--nicpromisc2", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc3", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc4", "allow-vms"]
      v.customize ["modifyvm", :id, "--nicpromisc5", "allow-vms"]

      v.memory = 4096
    end

    controller.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/host-provision.yml"
      ansible.groups = groups
    end

  end

end
