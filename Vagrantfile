Vagrant.configure(2) do |config|

  config.ssh.insert_key = false
  config.vm.box = "centos/7"
  config.vm.box_check_update = true
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end

  config.vm.define "foreman.jexia.com" do |node|
    node.vm.hostname = "foreman.jexia.com"
    node.vm.network "private_network", ip: "192.168.33.10"
    config.vm.provider "virtualbox" do |v|
      v.memory = 6192
      v.cpus = 2
    end
    config.vm.provider "libvirt" do |vl|
      vl.memory = 6192
      vl.cpus = 2
    end
  end
end
