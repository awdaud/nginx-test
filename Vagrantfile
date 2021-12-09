Vagrant.configure(2) do |config|
	config.vm.box = "generic/centos8"
	config.vm.provider "virtualbox" do |vb|
    vb.gui = false
		vb.memory = "1024"
    #vb.cpu = "1"
  end
  config.vm.synced_folder ".", "/vagrant"
  config.vm.define "wp" do |wp|
    wp.vm.hostname = "wp"
    wp.vm.network  "private_network", ip: "192.168.56.10"
    wp.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "wp.yml"
      ansible.limit = "all"
    end
    
  end

    
end