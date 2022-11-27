vm_box = ENV['BOX'] ? ENV['BOX'] : 'ubuntu/focal64'
vm_hostname = 'vagrantpgsql'

Vagrant.require_version '>= 2.2.0'
VAGRANTFILE_API_VERSION = '2'.freeze

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define vm_hostname do |pg|
    pg.vm.box = vm_box
    pg.vm.hostname = vm_hostname

    pg.vm.provider :virtualbox do |vb|
      vb.name = vm_hostname
      vb.memory = 4096
      vb.cpus = 2
    end

    pg.vm.provision 'shell' do |s|
      s.path = 'postgres.sh'
      s.privileged = true
    end
  end
end
