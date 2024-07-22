
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/focal64"
  #Determina a VM para inicializar como DHCP
  config.vm.network "public_network"
  #Determina o trafego da porta 80 da VM para a porta 8090 do host
  config.vm.network "forwarded_port", guest:80, host:8090

  #Configuração de memória RAM e vcpu's

    config.vm.provider "virtualbox" do |resources|
      resources.memory = "3072"
      resources.cpus = 2
    end
   #Executa script se instalação do nginx e zabbix
  config.vm.provision "shell", path: "./script.sh"
   #Envia arquivos de aplicação para a VM
  config.vm.synced_folder "./app", "/var/www/html"
  
end
