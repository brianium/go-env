go-env
======
Create an environment for developing a go powered api. Includes configuration for a client machine as well.

Provisions 2 trusty 64 bit ubuntu vms for local environment.

A starting point for growing an infrastructure for go powered applications.

Requirements
------------
* Ansible >= 1.6
* Vagrant (local development)
* Virtual Box (local development)

Configuration
-------------
There is currently a single hosts file called vagrant for configuring the development environment.

There are two groups defined in the hosts file:

###Client

Installs:

* Git + Mercurial
* Node.js for the client application

###API

Installs:

* Git + Mercurial
* Go (version configured via group vars, /usr/local/go/bin added to path)

Usage
-----
After installing the requirements and cloning this repo, just run `vagrant up`. You will have 2 trusty 64-bit vms ready to get started with!

You can ssh into these vms by using their names:

```
vagrant ssh api_client
vagrant ssh go_api
```

As staging and production hosts are added, the `ansible-playbook` command can be used to provision those remote environments as well.

###Vagrant configuration
You can rename the `vagrant.config.yml.sample` file to `vagrant.config.yml` if you want to configure the vagrant environment further. 

Currently the only option that can be configured is the vagrant `synced_folders` option for both the api_client and go_api vms.

WIP
---
This is very much a work in progress, and will grow as our infrastructure needs are fleshed out. However, this will already serve as a good starting point for spinning up a server/client environment.

