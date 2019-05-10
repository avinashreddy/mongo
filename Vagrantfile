Vagrant.configure("2") do |config|
  
 # Use the same key for each machine  config.ssh.insert_key = false
 config.ssh.insert_key = false
 
 config.vm.define "mongo1" do |cfg|
  cfg.vm.provider :virtualbox do |vb|
        vb.name = "mongo"
        vb.memory = 2048
  end
 cfg.vm.hostname = "mongo"
 cfg.vm.box = "centos/7"
 cfg.vm.network "private_network", ip: "10.100.2.20"
 config.vm.provision "file", source: "mongodb-org-4.0.repo", destination: "./mongodb-org-4.0.repo"
 config.vm.provision "file", source: "mongod.conf", destination: "./mongod.conf"
 cfg.vm.provision "shell", inline: <<-SHELL
    #yum check-update
    #yum install -y wget vim telnet net-tools
    mv ./mongodb-org-4.0.repo /etc/yum.repos.d/mongodb-org-4.0.repo
    yum install -y mongodb-org
    mv /etc/mongod.conf /etc/mongod.conf.bkp
    mv ./mongod.conf /etc/mongod.conf
    sudo chown mongod:mongod /etc/mongod.conf
    #systemctl enable mongod
    #systemctl start mongod
    SHELL
 end
 
end
