# -*- mode: ruby -*-
# vi: set ft=ruby :

N = 3

Vagrant.configure("2") do |config|
  # Base VM OS configuration.
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # General VirtualBox VM configuration.
  config.vm.provider :virtualbox do |v|
    v.memory = 3072
    v.cpus = 2
    v.linked_clone = true
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  (1..N).each do |machine_id|
    config.vm.define "rancher0#{machine_id}" do |machine|
      machine.vm.hostname = "rancher0#{machine_id}.rancher.loc"
      machine.vm.network :private_network, ip: "192.168.2.1#{machine_id}"

      machine.vm.provider :virtualbox do |v|
          v.name = "rancher0#{machine_id}"
      end

      # https://www.vagrantup.com/docs/provisioning/ansible
      # Only execute once the Ansible provisioner,
      # when all the machines are up and ready.
      # if machine_id == N
      #     machine.vm.provision :ansible do |ansible|
      #         # Disable default limit to connect to all the machines
      #         ansible.limit = "all"
      #         ansible.playbook = "playbook.yml"
      #     end
      # end
      end
  end
end
