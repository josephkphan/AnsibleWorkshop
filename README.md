# ansible-playbooks workshop
This repo is made for a workshop to introduce ansible, vagrant, and docker to people. It contains a vagrant cluster, installing docker, and deploying a docker hello-world application on the cluster. 



## Prereqs 
The following Software needs to be installed: 

#### Vagrant
Go to https://www.vagrantup.com/downloads.html and download the appropriate package

#### Ansible
Mac OS X: \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `sudo easy_install pip sudo pip install ansible` 

CentOS/Fedora: \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `sudo yum install ansible` 

Ubuntu: \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `sudo apt-get install software-properties-common sudo apt-add-repository ppa:ansible/ansible ` 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `sudo apt-get update sudo apt-get install ansible` 



## Commands Used during Workshop 

### Vagrant Commands Used
Bring up vagrant box cluster (3) \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `vagrant up`  

Tear down vagrant box cluster (3) \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `vagrant destroy`  

Ssh into vagrant box to see results \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `vagrant ssh (vagrant1 | vagrant2 | vagrant3)` 

### Ansible Commands Used
Copy Over a txt file onto box vagrant3 \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `ansible-playbook -i pool/dev/hosts --private-key=~/.vagrant.d/insecure_private_key -sku vagrant install_file.yml -l vagrant3` 

Install Docker 17 \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `ansible-playbook -i pool/dev/hosts --private-key=~/.vagrant.d/insecure_private_key -sku vagrant install_docker.yml` 

Deploy Hello World Application \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `ansible-playbook -i pool/dev/hosts --private-key=~/.vagrant.d/insecure_private_key -sku vagrant deploy_app.yml` 

#### Other Notes
The docker role should be credited to https://github.com/geerlingguy/ansible-role-docker \
The Hello World Application should be credited to https://hub.docker.com/_/hello-world/
