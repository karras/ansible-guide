# -*- mode: ruby -*-
# vi: set ft=ruby sw=2 ts=2 et wrap tw=76 :

Vagrant.configure("2") do |config|
  config.vm.define "debian7" do |debian7|
    debian7.vm.box = "adsy-debian-7.8-nonminimized.box"
    debian7.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-debian-7.8-nonminimized.box"
    debian7.vm.box_download_checksum = "e9ee9616f864f60f6c7ff4c71e6f3f7940c84279ae46f3fe5ee97f44ec4e14b9"
    debian7.vm.box_download_checksum_type = "sha256"
    debian7.vm.boot_timeout = 30
  end
  config.vm.define "debian8" do |debian8|
    debian8.vm.box = "adsy-debian-8.9-nonminimized.box"
    debian8.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-debian-8.9-nonminimized.box"
    debian8.vm.box_download_checksum = "f717d8e551561bcba3d679ca859898981250a58dcb7098eb1042445ab1984bac"
    debian8.vm.box_download_checksum_type = "sha256"
    debian8.vm.boot_timeout = 30
  end
  config.vm.define "debian9" do |debian9|
    debian9.vm.box = "adsy-debian-9.2-nonminimized.box"
    debian9.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-debian-9.2-nonminimized.box"
    debian9.vm.box_download_checksum = "d1b922f23941a2be3e7291668aa56194137b93f682e6a98542839dc5557793cd"
    debian9.vm.box_download_checksum_type = "sha256"
    debian9.vm.boot_timeout = 30
  end
  config.vm.define "centos6" do |centos6|
    centos6.vm.box = "adsy-centos-6.7-nonminimized.box"
    centos6.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-centos-6.7-nonminimized.box"
    centos6.vm.box_download_checksum = "1d49b01229ce379e16becf02398c6ae845bea2e662536cef50bcc0dd42b5c71d"
    centos6.vm.box_download_checksum_type = "sha256"
    centos6.vm.boot_timeout = 30
  end
  config.vm.define "centos7" do |centos7|
    centos7.vm.box = "adsy-centos-7.4-nonminimized.box"
    centos7.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-centos-7.4-nonminimized.box"
    centos7.vm.box_download_checksum = "956b5b1b77d13c1ceaed6fa22a39aa99ebe9cd0cf136e72d9ad1fc67676f828c"
    centos7.vm.box_download_checksum_type = "sha256"
    centos7.vm.boot_timeout = 30
  end
  config.vm.define "ubuntu14" do |ubuntu14|
    ubuntu14.vm.box = "adsy-ubuntu-14.04.5-nonminimized.box"
    ubuntu14.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-ubuntu-14.04.5-nonminimized.box"
    ubuntu14.vm.box_download_checksum = "14fef38391d6c33991b382161eb3e79cbaa3bb3762aa4bb7654ab16b6be8e370"
    ubuntu14.vm.box_download_checksum_type = "sha256"
    ubuntu14.vm.boot_timeout = 30
  end
  config.vm.define "ubuntu16" do |ubuntu16|
    ubuntu16.vm.box = "adsy-ubuntu-16.04.3-nonminimized.box"
    ubuntu16.vm.box_url = "https://vagrant.adfinis-sygroup.ch/adsy-ubuntu-16.04.3-nonminimized.box"
    ubuntu16.vm.box_download_checksum = "8500882ad1f5657aee11ede074ab5a13db6d582d1ef29f5a421f1868f3308ed6"
    ubuntu16.vm.box_download_checksum_type = "sha256"
    ubuntu16.vm.boot_timeout = 30
  end

  #config.vm.box_check_update = false

  #config.vm.network "forwarded_port", guest: 80, host: 8080
  #config.vm.network "private_network", ip: "192.168.33.10"
  #config.vm.network "public_network"

  #if Dir.exists?('../data')
  #  config.vm.synced_folder "../data", "/vagrant_data"
  #end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.customize [
      "modifyvm", :id,
      "--memory", 512,
      "--nictype1", "virtio",
    ]
  end

  #config.push.define "atlas" do |push|
  #  push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  #end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./site.yml"
    ansible.become = true
    ansible.extra_vars = {
      ansible_ssh_user: 'vagrant',
      ansible_managed: 'Warning: File is managed by Ansible [https://github.com/adfinis-sygroup/ansible-roles]',
    }
  end
end
