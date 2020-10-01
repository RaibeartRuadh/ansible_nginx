# -*- mode: ruby -*-
# vi: set ft=ruby :

ANSIBLE_NAME = "RaibeartAnsible"
SERVER_IP = "192.168.10.10"
VM_WEB_PORT = 8080

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
    config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: SERVER_IP
    #config.vm.provision :shell, :path => "params/init.sh"
    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "params/site.yml"
      ansible.extra_vars = {
        :nginx_http_default_server_port => VM_WEB_PORT
    }		
    end
  end
end
