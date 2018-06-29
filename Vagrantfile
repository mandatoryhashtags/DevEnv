VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define :"Magento1"
  config.vm.network :forwarded_port, guest: 22, host: 2222, id: "ssh", disabled: true
  config.vm.network :forwarded_port, guest: 22, host: 2225, auto_correct: true
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
