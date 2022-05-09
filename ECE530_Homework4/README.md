

ECE 530 Homework 4 Spring 2022
=========

Authors
------------
Joseph Hilland
Swetha Samayamantula 
Sean Pluemer 


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

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
