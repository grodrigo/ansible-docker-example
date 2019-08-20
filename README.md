# Example on how to use Ansible to create and Provision Docker containers

## Fork modifications and use:
* First create by hand a container (to simulate a running one):  
docker run --name nginx-test -d -p 8089:80 nginx:alpine  

* Then:  
ansible-playbook -i inventory.yml playbook.yml  

This will perform some installations and tests.  
  
* To remove the containers created type:  
ansible-playbook destroy.yml  
  
Look that the second test use raw install of python before other actions, you cannot use the role or perform another action because the "Gathering Facts" (I think) that role uses, and it needs python to be installed.  


------------ 
 
This repository contains a simple example usage of docker and ansible together.

playbook.yml starts an example alpine based container with python and destroy.yml, destroys the same container.

This is for a local usage using docker and makes use of localhost to launch those containers.

Inventory is also as simple as possible, and not a remote reference using other Docker Daemon URL.

This is also a companion repository of a tutorial at https://ilhicas.com on how to use Ansible to provision docker containers.

https://ilhicas.com/2018/08/25/Docker-and-ansible-example.html
