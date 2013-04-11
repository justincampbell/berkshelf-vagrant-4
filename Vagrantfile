require 'berkshelf/vagrant'

Vagrant.configure("2") do |config|
  config.berkshelf.enabled = true

  # config.vm.provision :shell, :inline => "echo Hello"

  config.vm.define :one do |one|
    one.vm.hostname = "one"
    one.vm.box = "Berkshelf-CentOS-6.3-x86_64-minimal"
    one.vm.box_url = "https://dl.dropbox.com/u/31081437/Berkshelf-CentOS-6.3-x86_64-minimal.box"
    one.vm.network :private_network, ip: "33.33.33.101"

    one.vm.provision :chef_solo do |chef|
      chef.run_list = ["recipe[berkshelf-vagrant-4::default]"]
    end
  end

  config.vm.define :two do |two|
    two.vm.hostname = "two"
    two.vm.box = "Berkshelf-CentOS-6.3-x86_64-minimal"
    two.vm.box_url = "https://dl.dropbox.com/u/31081437/Berkshelf-CentOS-6.3-x86_64-minimal.box"
    two.vm.network :private_network, ip: "33.33.33.102"

    two.vm.provision :chef_solo do |chef|
      chef.run_list = ["recipe[berkshelf-vagrant-4::default]"]
    end
  end
end if ENV['multi']

Vagrant.configure("2") do |config|
  config.berkshelf.enabled = true

  config.vm.hostname = "berkshelf-vagrant-4-berkshelf"
  config.vm.box = "Berkshelf-CentOS-6.3-x86_64-minimal"
  config.vm.box_url = "https://dl.dropbox.com/u/31081437/Berkshelf-CentOS-6.3-x86_64-minimal.box"
  config.vm.network :private_network, ip: "33.33.33.10"

  config.vm.provision :chef_solo do |chef|
    chef.run_list = ["recipe[berkshelf-vagrant-4::default]"]
  end
end unless ENV['multi']
