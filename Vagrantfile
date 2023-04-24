# ceci est le fichier Vagrantfile pour le delpoiement de wordpress avec docker
Vagrant.configure("2") do |config|
 
  config.vm.box = "ubuntu/bionic64"
  config.vm.provision :shell, path: "install-apache.sh"
      
  config.vm.network :forwarded_port, guest: 80, host:8000

  config.vm.define "ma-machine3" do |node|
    node.vm.provider "virtualbox" do |vb|
      vb.name = "wp-docker3"
      vb.memory = 512
      vb.cpus = 1
    end
    
  end   
    

end