Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-24.04"

  # Database
  config.vm.define "db" do |db|
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.56.10"
    db.vm.provider "virtualbox" do |vb|
      vb.name = "gogs_db"
      vb.memory = 512
      vb.cpus = 1
    end
  end

  # Gogs App 1
  config.vm.define "app1" do |app|
    app.vm.hostname = "app1"
    app.vm.network "private_network", ip: "192.168.56.11"
    app.vm.provider "virtualbox" do |vb|
      vb.name = "gogs_app1"
      vb.memory = 1024
      vb.cpus = 1
    end
  end

  # Gogs App 2
  config.vm.define "app2" do |app|
    app.vm.hostname = "app2"
    app.vm.network "private_network", ip: "192.168.56.12"
    app.vm.provider "virtualbox" do |vb|
      vb.name = "gogs_app2"
      vb.memory = 1024
      vb.cpus = 1
    end
  end

  # NGINX Reverse Proxy
  config.vm.define "nginx" do |nginx|
    nginx.vm.hostname = "nginx"
    nginx.vm.network "forwarded_port", guest: 80, host: 3006
    nginx.vm.network "private_network", ip: "192.168.56.13"
    nginx.vm.provider "virtualbox" do |vb|
      vb.name = "gogs_nginx"
      vb.memory = 512
      vb.cpus = 1
    end
  end	

  # Ansible
  config.vm.define "ansible" do |ansible|
     ansible.vm.hostname = "ansible"
     ansible.vm.network "private_network", ip: "192.168.56.14"
     ansible.vm.provider "virtualbox" do |vb|
       vb.name = "gogs_ansible"
       vb.memory = 512
       vb.cpus = 1
    end
  end	
end
