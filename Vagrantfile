# On va lire le fichier de configuration
require 'yaml'
# On vérifie si le fichier de configuation existe ou pas
if File.file?("config.yaml")
    config = YAML.load_file("config.yaml")
else
    raise "Le fichier de configuration est introuvable"
end

memory = config['memory']
cpus = config['cpus']
ip_base= config['ip']

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.vm.provision :shell, path: "mysql_wp_install.sh"
      
  config.vm.network :forwarded_port, guest: 80, host:1111

  config.vm.define "ma-machine" do |node|
    node.vm.provider "virtualbox" do |vb|
      vb.name = "mon-wordpress1"
      vb.memory = memory
      vb.cpus = cpus
    end
    node.vm.network :private_network, ip: ip_base
  end   
    

end
