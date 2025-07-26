Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/ubuntu2004"
  
  # Configure network if needed
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 5000, host: 5000
  
  # Ansible provisioner configuration
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "inventory.yml"
    ansible.extra_vars = {
      ansible_python_interpreter: "/usr/bin/python3"
    }
    ansible.verbose = "v"
  end
end