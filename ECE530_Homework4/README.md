

ECE 530 Homework 4 Spring 2022
=========


Getting started
------------
This playbook assumes that Ansible 2.9+ is installed, as this is the only version verified. Ubuntu-server 20+ is also the only Linux distro verified at this time. The zip file should be able to run on a fresh VM without any other installation other than Ansible. This has been tested and verified; see the png image in this repo.
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

Packages: packages was not a required role; however, it was included to become more familiar with Ansible. This installs proper MongoDB, Docker, and updates the host machine before running any other roles.

Common: common role is a simple role that contains a task and file for copying to the host's root directory. Since this project uses docker, this file is only copied to the host's root directory.
- uses a team.txt file in files, copied over to /root

Secondary: this role creates a simple MongoDB container which will be added to the replica set during the primary MongoDB container creation.
- uses defaults and vars as required for generic impl
- uses templates 
- uses handlers for starting MongoDB service

Primary: this role creates the mongo master container, which adds the users and sets up replica sets based on the template files.
- uses defaults and vars as required for generic impl
- uses templates for MongoDB scripts
- uses handlers for starting MongoDB service


Requirements
------------
- Create a playbook with a common role that writes your team members' names to the file /root/team.txt on all nodes.
- Create a role that provisions a MongoDB primary node; make sure the role is generic enough to use variables and templates instead of hard-coded config files.
- Create a role that provisions a secondary node, same reqs as above.



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
