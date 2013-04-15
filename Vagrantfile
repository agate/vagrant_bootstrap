Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "<NAME>",
      "--memory", "512"
    ]
  end

  config.vm.network :private_network, ip: "10.10.10.100"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = [ "cookbooks", "berks_cookbooks" ]

    chef.json = {
      :ubuntu => {
        :archive_url => "http://mirrors.163.com/ubuntu"
      },
      :rvm => {
        :default_ruby => "1.9.3",
        :global_gems => [
          { :name => "selenium-webdriver" },
          { :name => "rspec" }
        ]
      }
    }

    chef.add_recipe "bootstrap"
  end

  # this is just a example show you that how to create a synced_folder
  # don't use this: it will raise error because /vagrant is mounted by default
  #config.vm.synced_folder ".", "/vagrant", nfs: true
end
