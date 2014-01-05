# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos6.3"
  config.vm.box_url = "https://dl.dropbox.com/u/7225008/Vagrant/CentOS-6.3-x86_64-minimal.box"
  config.vm.hostname = "mysql.local"
  config.vm.network :private_network, ip: "192.168.33.10"
  config.berkshelf.enabled = true
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = [
      File.join(Dir.pwd, "site-cookbooks")
    ]
    chef.add_recipe("mysql::server")
    chef.add_recipe("mysql::ruby")
    chef.add_recipe("iptables")
    chef.json = {
      :mysql => {
        :allow_remote_root => true,
        :bind_address => "0.0.0.0",
        :grants_path => "/vagrant/grants.sql",
        :server_root_password => "p@ssw0rd",
        :server_repl_password => "p@ssw0rd",
        :server_debian_password => "p@ssw0rd"
      }
    }
  end
end
