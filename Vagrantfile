Vagrant.configure("2") do |config|
  
 # Use the same key for each machine  config.ssh.insert_key = false
 config.ssh.insert_key = false
 config.vbguest.auto_update = false
 
 config.vm.define "mongo1" do |cfg|
  cfg.vm.provider :virtualbox do |vb|
        vb.name = "mongo1"
        vb.memory = 2048
  end
 cfg.vm.hostname = "mongo1"
 cfg.vm.box = "centos/7"
 cfg.vm.network "private_network", ip: "10.100.2.20"
 
 cfg.vm.provision "shell", inline: <<-SHELL
    #yum check-update
    #yum install -y wget vim telnet net-tools
    mv /vagrant/mongodb-org-4.0.repo /etc/yum.repos.d/mongodb-org-4.0.repo
    yum install -y mongodb-org
    cat /vagrant/mongod.conf > /etc/mongod.conf
    sudo systemctl enable mongod
    sudo systemctl start mongod
    SHELL
 end
 
 config.vm.define "mongo2" do |cfg|
  cfg.vm.provider :virtualbox do |vb|
        vb.name = "mongo2"
        vb.memory = 2048
  end
 cfg.vm.hostname = "mongo2"
 cfg.vm.box = "centos/7"
 cfg.vm.network "private_network", ip: "10.100.2.21"
 
 cfg.vm.provision "shell", inline: <<-SHELL
    #yum check-update
    #yum install -y wget vim telnet net-tools
    mv /vagrant/mongodb-org-4.0.repo /etc/yum.repos.d/mongodb-org-4.0.repo
    yum install -y mongodb-org
    cat /vagrant/mongod.conf > /etc/mongod.conf
    sudo systemctl enable mongod
    sudo systemctl start mongod
    SHELL
 end
 
  config.vm.define "mongo3" do |cfg|
  cfg.vm.provider :virtualbox do |vb|
        vb.name = "mongo3"
        vb.memory = 2048
  end
 cfg.vm.hostname = "mongo3"
 cfg.vm.box = "centos/7"
 cfg.vm.network "private_network", ip: "10.100.2.22"
 
 cfg.vm.provision "shell", inline: <<-SHELL
    #yum check-update
    #yum install -y wget vim telnet net-tools
    mv /vagrant/mongodb-org-4.0.repo /etc/yum.repos.d/mongodb-org-4.0.repo
    yum install -y mongodb-org
    cat /vagrant/mongod.conf > /etc/mongod.conf
    sudo systemctl enable mongod
    sudo systemctl start mongod
    SHELL
 end
=begin
 rsconf = {
    _id: "dev1",
    members: [
      {_id: 0, host: "10.100.2.20:27017"},
      {_id: 1, host: "10.100.2.21:27017"},
      {_id: 2, host: "10.100.2.22:27017"} 
    ]
  }

rs.initiate(rsconf)  
=end
 
end
