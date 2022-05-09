

ECE 530 Homework 4 Spring 2022
=========


Getting started
------------
This playbook assumes that you have installed ansible 2.9+ as that is the only version that has been verified. Ubuntu-server 20+ is also the only linux distro verified at this time.
The zip file should be able to run on a fresh VM, without any other installation other than ansible. This has been tested and verified, see png image in this repo.

If you prefer to clone the repository, you will need to install git on the host machine as well.

Commands used included to create the roles were:
```
ansible-galaxy role init ROLE_NAME
```

To run the playbook use the following:
```
ansible-playbook playbook.yaml
```

Roles
------------

packages: packages was not a required role, however it was included to become more familiar with ansible. This installs proper mongodb, docker and updates to the host machine before it runs any other roles.

common: common role is a simple role that contains a task and file for copying to the root directory of the host. Since this project uses docker, this file is only copied to the root directory of the host.

secondary: this role creates a simple mongdb container which will be added into the replica set during the primary mongodb container creation.

primary: this role creates the mongo master container, which adds the users and sets up replica sets based on the template files.


Requirements
------------
- Create a playbook with a common role that writes your team members names to the file /root/team.txt on all nodes.
- Create role that provisions a MongoDB primary node, make sure the role is generic enough to use variables and templates instead of hard-coded config files.
- Create a role provisions a secondary node, same reqs as above.



Dependencies
------------

- docker
- python3
- pip3
- mongodb
- ansible

License
-------

BSD

Author Information
------------------

Joseph Hilland
Swetha Samayamantula 
Sean Pluemer 
