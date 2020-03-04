# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Ansible
  config.vm.define "ansible" do |ansible|

    ansible.vm.hostname = "ansible.hacklab"

    ansible.vm.box = "centos/7"

    ansible.vm.network "forwarded_port", guest: 80, host: 9092

    ansible.vm.network "private_network", ip: "192.168.200.30"

    ansible.vm.provider "virtualbox" do |v|
        v.customize [ "modifyvm", :id, "--cpus", "1" ]
        v.customize [ "modifyvm", :id, "--memory", "512" ]
    end

  end
  # End Ansible

  # WordPress
  config.vm.define "wordpress" do |wordpress|

    wordpress.vm.hostname = "wordpress.hacklab"

    wordpress.vm.box = "centos/7"

    wordpress.vm.network "forwarded_port", guest: 80, host: 9090

    wordpress.vm.network "private_network", ip: "192.168.200.31"

    wordpress.vm.provider "virtualbox" do |v|
        v.customize [ "modifyvm", :id, "--cpus", "1" ]
        v.customize [ "modifyvm", :id, "--memory", "512" ]
    end

  end
  # End wordpress

  # DebianSrv
  config.vm.define "debiandb" do |debiandb|

    debiandb.vm.hostname = "debiandb.hacklab"

    debiandb.vm.box = "debian/stretch64"

    debiandb.vm.network "forwarded_port", guest: 3306, host: 9091

   debiandb.vm.network "private_network", ip: "192.168.200.32"

    debiandb.vm.provider "virtualbox" do |y|
        y.customize [ "modifyvm", :id, "--cpus", "1" ]
        y.customize [ "modifyvm", :id, "--memory", "512" ]
    end

  end
  # End debiandb

end