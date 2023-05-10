### Vagrant

step1 to make a vagrant file run the code into gitbash     
    vagarant init
step 2 fill in the vagrant file with the code
 
  Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip:"192.168.10.100"

end
step 3 run the vagrant up code 

step 4 run vagrant ssh to enter the virtual machine in the terminal (the name chould change to vagrant@ubuntu-xenial)

step 5 update vagrant by running the code
   sudo apt-get update

step 6 upgrade vagrant by running the code
   sudo apt-get upgrade -y

step 7 install nginx by running the code
    sudo apt-get install nginx

step 8 start nginx by running the code sudo apt-get start njinx -y
you can access the nginx web server by typing the ip address into the web browser

step 9 destroy the server when complete
