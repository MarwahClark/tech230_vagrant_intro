### Vagrant

step1 type run vagrant in terminal to get rid of the virtual machine
step 2 run vagrant up to make a new virtual machine
step 3 run vagrant ssh to enter the virtual machine in the terminal (the name chould change to vagrant@ubuntu-xenial)
step 4 update vagrant by running the code sudo apt-get update
step 5 upgrade vagrant by running the sudo apt-get upgrade -y
step 6 install nginx by running the code sudo apt-get install nginx

step 7 in the vagrant file you should have the code 

Vagrant.configure("2") do |config|
 
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip:"192.168.10.100"

end
step 8 change the ip code to whatever the ip address is 
step 9 start nginx by running the code sudo apt-get start njinx -y
you can access the nginx web server by typing the ip address into the web browser

