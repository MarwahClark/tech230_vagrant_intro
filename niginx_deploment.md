### Vagrant


*step 1* - to make a vagrant file run the code into gitbash     
    `vagarant init`

*step 2* - fill in the vagrant file with the code
 
  `Vagrant.configure("2") do |config|`

  `config.vm.box = "ubuntu/xenial64"`
  `config.vm.network "private_network", ip:"192.168.10.100"`

end
*step 3* - The config.vm.box line will usually be followed by = "base". Swap "base" for "ubuntu/xenial64". For example - config.vm.box = "ubuntu/xenial64

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

*step 9* - to check the status type: 
`sudo systemctl status nginx (in terminal), to get the status`

*step 9* - destroy the server when complete 
 `vagrant destroy -y`
 


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


### app deployment

*step 1* - open a new folder, within this folder make sure it contains the contents for the app and the environment.

*step 2* - run the 
 `vagrant init` code to initate a vagrant file

 *step 3* - in the vagrant file change the code to
 ` Vagrant.configure("2") do |config|`

  `config.vm.box = "ubuntu/xenial64"`
 ` config.vm.network "private_network", ip:"192.168.10.100"`


  `end`

*step 4* add a line into the vagrant folder that specifies the path for provision 
``config.vm.provision "shell", path: "provision .sh"`

*step 5* sync the folders using this code and specify which folder you want to sync
 `config.vm.synced_folder"app","/home/vagrant/app"`

*step 5* create a provision shell using the extension .sh

*step 6* - write out this code into the provision shell 
`#!/bin/bash`

`sudo apt-get update -y`

`sudo apt-get upgrade -y`

`sudo apt-get install nginx -y`

`sudo systemctl start nginx`



*step 6* - in gitbash run `vagrant up` and then `vagrant ssh` to ensure that its running

*step 7* - in visule code run the code `cd environment` to move into the environment folder

*step 8* - once in the environment folder run the code `ls` to see what files are there, specifically `spec-tests/` 

*step 9* - run the code `cd spec-test` to enter the spec-test file

*step 10* - run the code `gem install bundler` (this command onwards is specific to ruby to test what is installed) 

*step 11* - run the code `bundle` 

*step 12* - run the code `rake spec` these tests let us know what prerquists we hvae for the application by runnning tests against the environment we have made 

*step 13* - to install nodejs in the gitbash terminal run the code ` sudo apt-get install nodejs -y`

*step 14* - run `rake spec` again on vs code to see if it has been installed successfully

*step 15* - to check the version run the code `nodejs --version`

*step 16* - to get the specific version 6 of nodejs run the codes 
  -`sudo apt-get install python-software-properties` `-y`
  -`curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash `
  (this command is specific to the version as the curl stands for the source and the bash makes it the version)
  -`sudo apt-get install nodejs -y`

*step17* run a `rake spec` to check it has been installed

*step 18* to instal pm2 run the code `sudo npm install pm2 -g` (the G allows it to be made available globally)

*step 19* do a final `rake spec` which should have no failures

*step 20* in the gitbash terminal change directory into the 'app' folder by running code `cd app` yuo ahould have all the files that make up the application

*step 21* run the code `npm install` to scan files for modules needed.

*step 22* to start the app run the code `node app.js` or `npm start`if it has been successful you should get the message ` your app is ready and listening on port 3000`

*step 23* to check the app on browser type in the ip address, with `:3000` at the end
  `192.168.10.100:3000`

 - another method to deploy the app which is alot quicker is by typing all the app depndency codes in order in the same provision file.
  
   -once tying `vagrant up` if done correctly the app should run.

   `#!/bin/bash`
   `sudo apt-get update -y`
   `sudo apt-get upgrade -y`
   `sudo apt-get install nginx -y`
   `sudo systemctl start nginx`
   `sudo apt-get install python-software-properties`
   `curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -`
   `sudo apt-get install nodejs -y`
   `npm install pm2 -g`
   `cd /home/vagrant/app/app`
   `npm install`
   `npm start`


![Alt text](https://file%2B.vscode-resource.vscode-cdn.net/c%3A/Users/marwa/OneDrive/Pictures/Screenshots/Screenshot%202023-05-12%20101813.png?version%3D1683884414843)




 
 


  ![Alt text](https://file%2B.vscode-resource.vscode-cdn.net/c%3A/Users/marwa/OneDrive/Pictures/Screenshots/Screenshot%202023-05-12%20104151.png?version%3D1683884585503)

  