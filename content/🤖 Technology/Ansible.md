---
date: 2023-02-21
draft: false
tags:
  - technology
  - automation
---
Ansible is an open source command-line tool written in [[Python]] to automate the installation and configuration of software on remote machines through an [[SSH]] connection. [^1][^3] Because Ansible uses SSH, it is a very lightweight and secure solution, and has no need for an Ansible agent or client service. [^3]
The connection details to the target machine(s) are all stored in a file called the **inventory** [^3], and Ansible can be run against the target machine(s) either using the command line, or for more complex tasks, a script called the Playbook.

The **Playbook** is a YAML file which allows us to define a series of ansible procedures using varying levels of organisational principles (modules, tasks, and roles) to run against a target machine or group of machines. [^2][^3]

#### Ansible glossary

- **Ansible server**: the machine where Ansible is installed and from which all tasks and the playbook are run.  [^3]
- **Module**: a set of commands that Ansible will run on the client-side. [^3]
- **Task**: a section (in the playbook?) running a single procedure [^3]
- **Role**: an organisational method for tasks and related files [^3]
- **Facts**: information fetched from global variables on the client machine using the *gather-facts* operation [^3]
- **Inventory**: a file containing data about the ansible client server [^3]


---
# References

[^1]: https://www.ansible.com/overview/how-ansible-works

[^2]: https://www.tutorialspoint.com/ansible/ansible_introduction.htm

[^3]: https://www.guru99.com/ansible-tutorial.html