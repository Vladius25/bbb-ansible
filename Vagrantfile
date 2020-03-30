Vagrant.configure("2") do |config| 
    config.vm.box = "bento/ubuntu-16.04" 
    
    config.vm.provider "virtualbox" do |vb| 
        vb.memory = "4024" 
        vb.cpus = "1" 
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "setup-bbb.yaml"
        ansible.extra_vars = {
            hostname: "example.com",
            greenlight_repo: git@github.com:bigbluebutton/greenlight.git 
        }               
    end
end
