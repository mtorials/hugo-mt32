---
title: "Install Ansible"
date: 2021-03-1
draft: false
description: "Ansible Opensource automation platform"
tags: ["opensource", "automation", "ssh", "installation"]
author: "ShowMeYourSkil"
---

# Ansible

Hey, in this articel I would like to tell you something about Ansible and how you can install it. 

# What is ansible?

Ansible is a automation platform to automate process. Example like install full automatic Virtual Machines oder Windows updates and more..
It work with the language yml. You can create "Playbooks" through which an order is executed.

# How to Install Ansbile.

Example OS: Debian10

1. Open: `/ect/apt/sources.list`
2. Paste this source `deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main`
3. Close this file
4. Run `$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367`
5. `$ sudo apt update`
6. `$ sudo apt install ansible`
7. Check the version: `ansible --version`

In my next article I will start with the playbooks. 
Thanks for read my articel :D
