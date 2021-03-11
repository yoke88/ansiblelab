# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "centos" do |centos|
    centos.vm.box = "bento/centos7"
    centos.vm.network "private_network", ip: "192.168.33.202"
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box="bento/ubuntu-16.04"
    ubuntu.vm.network "private_network", ip: "192.168.33.203"
  end
  # 配置默认共享路径权限，否则ansible 文件在/vagrant里会报权限错误
  config.vm.provider "virtualbox" do |vb|
    #   vb.gui = true
    vb.memory = "2048"
  end
  config.vm.synced_folder ".", "/vagrant", owner: "vagrant",group: "vagrant", mount_options: ["dmode=700,fmode=700"]
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook="playbook/ping.yaml"
  end
end
