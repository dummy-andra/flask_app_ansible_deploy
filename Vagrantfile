Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network :private_network, ip: "192.168.33.11"
  config.ssh.insert_key = false
  config.ssh.shell = "bash"
  config.vm.network :forwarded_port, guest: 80, host: 5000
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
    v.name = "webservers"
  end
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

end