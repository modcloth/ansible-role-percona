# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]   
  end  
  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "percona-role-test.yml"
    ansible.verbose = "vvv"
    ansible.host_key_checking = false
  end  
end
