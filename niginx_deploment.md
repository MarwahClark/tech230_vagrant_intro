### Vagrant


*step 1* - to make a vagrant file run the code into gitbash     
    `vagarant init`
*step 2* - fill in the vagrant file with the code
 
  `Vagrant.configure("2") do |config|`

  `config.vm.box = "ubuntu/xenial64"`
  `config.vm.network "private_network", ip:"192.168.10.100"`

end
*step 3* - run the `vagrant up` code 

*step 4 *- run `vagrant ssh` to enter the virtual machine in the terminal (the name chould change to vagrant@ubuntu-xenial)

*step 5* - update vagrant by running the code
   `sudo apt-get update`

*step 6* - upgrade vagrant by running the code
   `sudo apt-get upgrade -y`

*step 7* - install nginx by running the code
    `sudo apt-get install nginx`

*step 8* - start nginx by running the code `sudo systemctl start njinx -y`
you can access the nginx web server by typing the ip address into the web browser

*step 9* - destroy the server when complete


### Automation

- create a new shell file in the same folder as the vagrant file using the extension .sh
    `provision.sh`
-write the code 
  `#!/bin/bash`
- this code is called a shebang and it tells the shell what propgram to interpret the script with when executed
- next add the code

 `sudo apt-get update -y`

  `sudo apt-get upgrade -y`

  `sudo apt-get install nginx -y`

  `sudo systemctl start nginx `

- finally run the ` vagrant init` code to creat a vagrant file

- in this file you will see the configuration :
   `config.vm.network "private_network", ip: "192.168.10.100"`
   `config.vm.provision "shell", path: "provision.sh"`

- after adding this run the code 
`vagrant up` this will create and confirgure your virtual machine

- enter `vagrant ssh` in the right pathway in gitbash to acces
