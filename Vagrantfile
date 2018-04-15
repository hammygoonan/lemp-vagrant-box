ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'
  config.vm.provider :virtualbox do |vbox|
    vbox.memory = 512
    vbox.cpus = 1
    vbox.customize ['modifyvm', :id, '--cpuexecutioncap', '50']
  end
  config.vm.define 'lemp' do |node|
    node.vm.hostname = 'vagrantvm.local'
    node.vm.network :private_network, ip: '195.28.128.20'
    node.vm.post_up_message = 'Web: http://195.28.128.20'
  end
  config.vm.synced_folder 'vagrant', '/vagrant'
  config.vm.provision :ansible_local do |ansible|
    ansible.provisioning_path = '/vagrant/cfg'
    ansible.inventory_path = 'local'
    ansible.playbook = 'site.yml'
    ansible.become = true
  end
end
