Vagrant::Config.run do |config|

  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # config.vm.boot_mode = :gui
  config.ssh.forward_x11 = true
  config.vm.share_folder "puppet-files", "/etc/puppet/files", "vagrant/files"

  config.vm.provision :puppet, 
    :options => [
      "--fileserverconfig=/vagrant/vagrant/fileserver.conf",
      "--modulepath=/vagrant/vagrant/modules"
    ] do |puppet|
    puppet.manifests_path = "vagrant"
    puppet.manifest_file = "site.pp"
  end

  config.vm.define :mysql do |mysql|
    mysql.vm.host_name = "mysql"
    mysql.vm.forward_port 3306, 3306
  end

  config.vm.define :python do |python|
    python.vm.host_name = "python"
  end

  config.vm.define :ruby do |ruby|
    ruby.vm.host_name = "ruby"
  end

  config.vm.define :scientific do |scientific|
    scientific.vm.host_name = "scientific"
  end

  config.vm.define :refine do |refine|
    refine.vm.host_name = "refine"
    refine.vm.forward_port 3333, 3333
  end

  config.vm.define :mongodb do |mongodb|
    mongodb.vm.host_name = "mongodb"
	mongodb.vm.forward_port 27017, 27017
	mongodb.vm.forward_port 28017, 28017
  end

  config.vm.define :nodejs do |nodejs|
    nodejs.vm.host_name = "nodejs"
    nodejs.vm.forward_port 8888, 8888 
  end

  config.vm.define :ocr do |ocr|
    ocr.vm.host_name = "ocr"
  end

end