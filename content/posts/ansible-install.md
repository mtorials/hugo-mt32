---
title: "Install Ansible"
date: 2021-02-
draft: false
description: "Ansible Opensource automation platform"
tags: ["opensource", "automation", "ssh", "installation"]
author: "ShowMeYourSkil"
---

# Ansible

Hey, in this article I would like to tell you something about Ansible and how you can installing it. 

# What is ansible?

Ansible is a automation platform to automate process.For example like install full automatic Virtual Machines oder Windows updates and more...
It works with the language yml. You can create "Playbooks" through which an order of commands is executed.

# How to Install Ansbile.

Example OS: Debian10

1. Open: `nano /ect/apt/sources.list`
2. Paste this source `deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main`
3. Close this file
4. Run `$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367`
5. `$ sudo apt update`
6. `$ sudo apt install ansible`
7. Check the version: `ansible --version`
8. 
![image](https://user-images.githubusercontent.com/39274150/109625598-cbf63b00-7b3f-11eb-8f20-769357560562.png)

## The Author

See ShowMeYourSkil on [github](https://github.com/showmeyourskil)!

