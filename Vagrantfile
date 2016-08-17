Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.synced_folder "~/Projects/docker_playground", "/mnt/www"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end

  # Install Ansible on the box
  config.vm.provision "shell", inline: <<-SHELL
    sudo yum update -y
    sudo yum install -y epel-release ansible
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
