require 'yaml'
settings = YAML.load_file 'ansible/group_vars/all.yml'

Vagrant.configure("2") do |config|

  config.vm.define "keycloak-box-vm" do |srv|
    srv.vm.box = "debian/buster64"
    srv.ssh.insert_key = false
    srv.vm.hostname = "keycloak-box.box"
    srv.vm.network :private_network, ip: settings['keycloak_host']

    srv.vm.provider :virtualbox do |vb|
      vb.name = "keycloak-box"
      vb.memory = 4048
      vb.cpus = 2
    end
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.version = "latest"
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "ansible/playbook.yml"
    ansible.galaxy_role_file = "requirements.yml"
    ansible.verbose = "true"
  end
  
end
