
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.box = "vagrant-debian-jessie-pixels" 
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", 1024]
  end
end
