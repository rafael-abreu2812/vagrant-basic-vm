
Vagrant.configure("2") do |config|


  # Select the Vagrant box 
    config.vm.box = "ubuntu/focal64"
  
  
  # Configure the VM to use DHCP
    config.vm.network  "public_network"
  
  
  # Redirect port 80 of the VM to port 8090 of the host machine
    config.vm.network "forwarded_port", guest: 80, host: 8090
  
  # Configuration on VM size, with amount of memory and vcpus
    config.vm.provider "virtualbox" do |resources|
      resources.memory = 2048  # 2GB of RAM
      resources.cpus = 2  #2 vcpus
    end
  
  # Execute the NGINX installation script 
  config.vm.provision "shell", path: "install.nginx.sh"
  
  # Sync local folder to a directory on the VM
  config.vm.synced_folder "./app", "/var/www/html"
   
  end