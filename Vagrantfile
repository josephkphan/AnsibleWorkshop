
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config| 
# Use the same key for each machine 
config.ssh.insert_key = false

config.vm.define "vagrant1" do |vagrant1|
    vagrant1.vm.box = "ubuntu/trusty64"
    vagrant1.vm.network "forwarded_port", guest: 80, host: 8080 
    vagrant1.vm.network "forwarded_port", guest: 443, host: 8443
end
config.vm.define "vagrant2" do |vagrant2|
    vagrant2.vm.box = "ubuntu/trusty64"
    vagrant2.vm.network "forwarded_port", guest: 80, host: 8081
    vagrant2.vm.network "forwarded_port", guest: 443, host: 8444
end
config.vm.define "vagrant3" do |vagrant3|
    vagrant3.vm.box = "ubuntu/trusty64"
    vagrant3.vm.network "forwarded_port", guest: 80, host: 8082
    vagrant3.vm.network "forwarded_port", guest: 443, host: 8445
end end


# Check ssh config "vagrant ssh-config"

# Ssh into by "vagrant ssh <VAGRANT_BOX_NAME>" i.e. vagrant1 | vagrant2 | vagrant3

# add the following to your host files (in ansible)
#   vagrant1 ansible_ssh_host=127.0.0.1 ansible_ssh_port=2222
#   vagrant2 ansible_ssh_host=127.0.0.1 ansible_ssh_port=2200
#   vagrant3 ansible_ssh_host=127.0.0.1 ansible_ssh_port=2201

# To check if you can use ansible to get in.. use "ansible vagrant2 -a "ip addr show dev eth0" "