# Simple Web App for Colourbox

An Ansible Playbook to provision web-servers Nginx, getting the code from a Git respository and sending static files to S3. 

## Getting Started

You can clone or download the repository and execute it in an Ansible machine, you will need some credential files to connect the different machines in your environment.
The program set an Ubuntu instance up with Nginx, a github repository, S3 and the configuration required. 

#The Playbook script
/foo/webservers.yml

### Prerequisites

What things you need to install the software and how to install them
To run the Playbook you need:
-a Ansible machine.
-an Ubuntu instance with Python and SSH installed.
-a Key Pair to connect the machines by SSH.
-an aws AMI credential to connect S3



### Installing

In a previosly configurated Ansible machine, make a copy of the repository and join it with the configuration files, make sure the credentials work. The file's tree should look like:
```
/webserver.yml
/static_site.cfg
/colourAnsible.pem
/credentials
/etc/ansible/hosts 
```

The files required to set up are the followings:

#An ansible definition for "webservers" hosts
/etc/ansible/hosts
```
[webservers]
nginx1 ansible_ssh_host=examplename
```
#An RSA private key to connect by ssh with the machine
/foo/colourAnsible.pem

#AMI credentials to connect an S3 bucket
/foo/credentials 
```
[default]
region = us-east-1
aws_access_key_id = exampleid
aws_secret_access_key = exampleaccess
```

## Running the tests


And play the book:
```
ansible-playbook webservers.yml
```


## Authors

* **Daniel Antonio Tala de Dompierre de Chaufepie** - [Talaman.info](http://talaman.info)
