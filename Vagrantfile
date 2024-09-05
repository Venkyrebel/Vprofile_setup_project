Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true 
  config.hostmanager.manage_host = true
  
  #Database VM
  config.vm.define "database" do |database|
    database.vm.box = "eurolinux-vagrant/centos-stream-9"
    database.vm.box_version = "9.0.43"
    database.vm.hostname = "database"
    database.vm.network "private_network", ip: "192.168.56.15"
    database.vm.provider "virtualbox" do |vb|
     vb.memory = "600"
   end
   database.vm.provision "shell", path: "mysql.sh"  

  end
  
  #Memcache VM
  config.vm.define "memcache" do |memcache|
    memcache.vm.box = "eurolinux-vagrant/centos-stream-9"
    memcache.vm.box_version = "9.0.43"
    memcache.vm.hostname = "memcache"
    memcache.vm.network "private_network", ip: "192.168.56.14"
    memcache.vm.provider "virtualbox" do |vb|
     vb.memory = "600"
   end
   memcache.vm.provision "shell", path: "memcache.sh"  
  end
  #RabbitMQ VM
  config.vm.define "rabbitmq" do |rabbitmq|
    rabbitmq.vm.box = "eurolinux-vagrant/centos-stream-9"
    rabbitmq.vm.box_version = "9.0.43"
    rabbitmq.vm.hostname = "rabbitmq"
    rabbitmq.vm.network "private_network", ip: "192.168.56.16"
    rabbitmq.vm.provider "virtualbox" do |vb|
     vb.memory = "600"
   end
   rabbitmq.vm.provision "shell", path: "rabbitmq.sh"  
  end
  #Tomcat VM
   config.vm.define "tomcat" do |tomcat|
    tomcat.vm.box = "eurolinux-vagrant/centos-stream-9"
    tomcat.vm.box_version = "9.0.43"
    tomcat.vm.hostname = "tomcat"
    tomcat.vm.network "private_network", ip: "192.168.56.12"
    tomcat.vm.provision "shell", path: "tomcat.sh"  
    tomcat.vm.provider "virtualbox" do |vb|
     vb.memory = "800"
   end
   end
   
  
#Nginx VM
  config.vm.define "nginx" do |nginx|
    nginx.vm.box = "ubuntu/jammy64"
    nginx.vm.hostname = "nginx"
    nginx.vm.network "private_network", ip: "192.168.56.11"
#   nginx.vm.network "public_network"
nginx.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "800"
   end
   nginx.vm.provision "shell", path: "nginx.sh"  
end
  
end
