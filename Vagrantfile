


HOME_DISK = "D:/diskbox/2.vmdk"



Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define :web do |web_config|
     web_config.vm.host_name = "web"
     web_config.vm.network "private_network", ip:"192.168.57.3"
	 web_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL
     web_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "2048"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end

  config.vm.define :openvpn do |openvpn_config|
      openvpn_config.vm.host_name = "openvpn"
      openvpn_config.vm.network "private_network", ip:"192.168.56.2"
	  openvpn_config.vm.network "private_network", ip:"192.168.57.2"
      openvpn_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
          vb.customize ["modifyvm", :id, "--cpus", "1"]
      end
  end
  
  
  
  config.vm.define :elk do |elk_config|
     elk_config.vm.host_name = "elk"
     elk_config.vm.network "private_network", ip:"192.168.57.4"
	 elk_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL
     elk_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "6144"]
          vb.customize ["modifyvm", :id, "--cpus", "4"]
        end
    end
	
	
	
 config.vm.define :loki do |loki_config|
     loki_config.vm.host_name = "loki"
     loki_config.vm.network "private_network", ip:"192.168.57.5"
	 loki_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL
     loki_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end	
	
	
 config.vm.define :gitlab do |gitlab_config|
     gitlab_config.vm.host_name = "gitlab"
     gitlab_config.vm.network "private_network", ip:"192.168.57.6"
	 gitlab_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL
     gitlab_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "4096"]
          vb.customize ["modifyvm", :id, "--cpus", "4"]
        end
    end		
	
	
	
	
 config.vm.define :master do |master_config|
     master_config.vm.host_name = "master"
     master_config.vm.network "private_network", ip:"192.168.57.8"
	 master_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
	sudo swapoff -a
  SHELL
     master_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "3072"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end		
	
	
	
	
 config.vm.define :node1 do |node1_config|
     node1_config.vm.host_name = "node1"
     node1_config.vm.network "private_network", ip:"192.168.57.9"
	 node1_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
    sudo swapoff -a
  SHELL
     node1_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "3072"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end		
	
	
	
 config.vm.define :node2 do |node2_config|
     node2_config.vm.host_name = "node2"
     node2_config.vm.network "private_network", ip:"192.168.57.10"
	 node2_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
	sudo swapoff -a

  SHELL
     node2_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "3072"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end		


 config.vm.define :rabbitmq do |rabbitmq_config|
     #rabbitmq_config.vm.box = "centos/7"
	 rabbitmq_config.vm.box = "ubuntu/focal64"
     rabbitmq_config.vm.host_name = "rabbitmq"
     rabbitmq_config.vm.network "private_network", ip:"192.168.57.11"
	 rabbitmq_config.vm.provision "shell", inline: <<-SHELL
    cat /vagrant/id_ed25519.pub >> /home/vagrant/.ssh/authorized_keys
	
  SHELL
     rabbitmq_config.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "4096"]
          vb.customize ["modifyvm", :id, "--cpus", "4"]
        end
    end				
	
   
end