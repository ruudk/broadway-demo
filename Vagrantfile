# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "192.168.42.100"
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/playbook.yml"
        ansible.verbose = "vvv"
        ansible.sudo = true
        ansible.extra_vars = {
            ansible_ssh_user: 'vagrant',
            httpd_run_user: 'vagrant',
            httpd_run_group: 'vagrant'
        }
    end

end
