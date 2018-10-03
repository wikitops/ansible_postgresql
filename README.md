# Ansible : Playbook Postgresql

The aim of this project is to deploy a Postgresql cluster on Vagrant with a basic replication.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

*   [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
*   Update the Vagrant file based on your computer (CPU, memory), if needed
*   You must have download the ubuntu Xenial64 vagrant box :

```bash
$ vagrant box add https://app.vagrantup.com/ubuntu/boxes/xenial64
```

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Build Environment

Vagrant needs to init the project to run and build it :

```bash
$ vagrant up
```

After build, you can check which virtual machine Vagrant has created :

```bash
$ vagrant status
```

If all run like it is expected, you should see something like this :

```bash
$ vagrant status

Current machine states:

postgresql01                  running (virtualbox)
postgresql02                  running (virtualbox)
```

#### Deployment

To deploy the Postgresql cluster, you just have to run the Ansible playbook postgresql.yml with this command :

```bash
$ ansible-playbook postgresql.yml
```

If everything run as expected, you should connect to postgres master node and create an object like a database. Every change on master node should be replicate on slave nodes automaticaly.

#### Destroy

To destroy on what Vagrant has created, just run this command :

```bash
$ vagrant destroy
```

## Author

Member of Wikitops : https://www.wikitops.io/

## Licence

This project is licensed under the Apache License, Version 2.0. For the full text of the license, see the LICENSE file.
