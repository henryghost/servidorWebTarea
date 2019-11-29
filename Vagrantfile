# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "web_1" do |web|
      	web.vm.provider :virtualbox do |vb|
            vb.customize [ 'modifyvm', :id, '--name', 'web-1' ]
            vb.customize [ 'modifyvm', :id, '--cpus', '1' ]
            vb.customize [ 'modifyvm', :id, '--memory', '720' ]
            vb.customize [ 'modifyvm', :id, '--cpuexecutioncap', '50' ]
        config.vm.network "forwarded_port", guest: 80, host:8080
        config.vm.synced_folder "www_1", "/var/www/html"
        config.vm.provision "shell", path: "script.sh"
      end
  end
  config.vm.define "web_2" do |web|
	web.vm.provider :virtualbox do |vb|
            vb.customize [ 'modifyvm', :id, '--name', 'web-2' ]
            vb.customize [ 'modifyvm', :id, '--cpus', '1' ]
            vb.customize [ 'modifyvm', :id, '--memory', '720' ]
            vb.customize [ 'modifyvm', :id, '--cpuexecutioncap', '50' ]
        config.vm.network "forwarded_port", guest: 80, host:8008
        config.vm.synced_folder "www_2", "/var/www/html"
        config.vm.provision "shell", path: "script.sh"
      end
  end
end




