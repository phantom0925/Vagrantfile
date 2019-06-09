# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "centos/7"

  # 将虚拟机的80端口映射到主机的8888端口
  config.vm.network "forwarded_port", guest: 80, host: 8890  
  config.vm.network "forwarded_port", guest: 8888, host: 8891

  config.vm.synced_folder "K:/upan/Docker学习笔记/源码", "/home/vagrant/dockercode",
　　　　type: "smb",
# 　　　　smb_host: "192.168.33.1",
　　　　smb_username: "vagrant",
　　　　smb_password: "vagrant",
　　　　mount_options: ["username=vagrant","password=vagrant"]

  # 设置私有ip  
  config.vm.network "private_network", ip: "192.168.50.4",auto_config:true

  # 共有ip
  # config.vm.network "public_network"
  # 虚拟机主机名
  config.vm.hostname = "wgw"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # 给虚拟机命名
    vb.name = "centos_wgw"
  end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine
  #   sudo yum install -y yum-utils device-mapper-persistent-data lvm2
  #   sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  #   sudo yum install docker-ce docker-ce-cli containerd.io
  #   sudo systemctl start docker                           
  # SHELL
  config.vm.provision "shell", 
  inline:"sudo yum update \
  sudo yum install -y redis-server"
end
