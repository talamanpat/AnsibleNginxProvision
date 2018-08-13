# Simple Web App for Colourbox

An Ansible Playbook to provision Nginx web-servers, getting the code from a Git repository and sending static files to S3. 

## Getting Started

You can clone or download the repository and execute it in an Ansible machine, you will need some credential files to connect the different machines in your environment.
The program set up an Ubuntu instance with Nginx, mount a website on the port 80 from a GitHub repository and sync static content with S3. 
The rockstar Playbook script can be found in:
```
/foo/webservers.yml
```

### Prerequisites

To run the Playbook, you will need:
-an Ansible machine.
-an Ubuntu instance with Python and SSH installed.
-a "pem" Key Pair to connect the machines by SSH.
-an AWS AMI credential to connect S3

### Installing

In an Ansible machine, make a copy of the repository and join it with the configuration files (described below), make sure the credentials work. The file's tree should look like:
```
/foo/webserver.yml
/foo/static_site.cfg
/foo/colourAnsible.pem
/foo/credentials
/etc/ansible/hosts 
```

The files required to set up are the followings:

-An ansible definition for "webservers" hosts
/etc/ansible/hosts
```
[webservers]
nginx1 ansible_ssh_host=examplename
```
-An RSA private key to connect by ssh with the machine
/foo/colourAnsible.pem

-AMI credentials to connect an S3 bucket
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
