# ansible-java-aktuell

TODO

## Running the Code Samples

The code samples are tested with Ansible 2.0.1.0.

### Setup Test infrastructure
I prepare a Vagrantfile for the setup of the test infrastructure. The only prerequires are that you have to install VirtualBox and Vagrant on your machine. Then follow these steps:

1. Open a CLI and go to the location of the file `Vagrantfile`.
2. Call `vagrant up`. Vagrant will download the necessary image for VirtualBox. That will take some times.
3. Then copy your public key for the authentication that is needed for a SSH login.
```
ssh-copy-id -i ~/.ssh/id_rsa vagrant@192.168.33.10
```
Hint: Public and private keys can be generated with the following command: `ssh-keygen`

### Run Ansible Samples
There exists three samples: server setup without roles, server setup with roles, deploy WAR file on an installed Apache Tomcat

#### Run Setup Samples Without Roles 

1. Go to the root folder of the repository
2. Call `ansible-playbook -i inventories/test -u vagrant setup-app.yml`

#### Run Setup Sample With Roles

1. Go to the root folder of the repository
2. Call `ansible-playbook -i inventories/test -u vagrant setup-app-roles.yml`

#### Run Deploy Sample

1. Go to the root folder of the repository
2. Call `ansible-playbook -i inventories/test -u vagrant deploy-demo.yml `
3. Cal URL http://192.168.33.10:8080/demo/

