Vagrant.configure("2") do |config| 
    config.vm.box = "bento/ubuntu-16.04" 
    
    config.vm.provider "virtualbox" do |vb| 
        vb.memory = "4024" 
        vb.cpus = "1"
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        vb.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "setup-bbb.yml"
        ansible.become = true
        ansible.verbose = "v"
        ansible.extra_vars = {
            hostname: "example.com",
            greenlight_repo: "https://github.com/bigbluebutton/greenlight.git",
            ssl_email: "root@example.com"
        }               
    end
end
